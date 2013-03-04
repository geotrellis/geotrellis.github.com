---
layout: tutorials
title: Web Service Tutorial

tutorial: tutorials
num: 3
---

In this tutorial we will walk through building web services 
using Jetty and GeoTrellis from scratch.

#### Setting up the project

We'll be using [sbt](http://www.scala-sbt.org/) as our build tool. The GeoTrellis code base
comes with an sbt launching script that will download the appropriate version of sbt
and run it; however for the purpose of this tutorial I will assume you have sbt
already installed on your system (see [the sbt installation documentation](http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html#installing-sbt) for help).

First, we need to set up the folder structure of our project. We will follow the 
[recommended directory structure](http://www.scala-sbt.org/release/docs/Getting-Started/Directories.html)
for a simple sbt project:

`src`<br/>
&nbsp;&nbsp;`└── main`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`├── resources`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`└── scala`<br/>

Now we need to create a `build.sbt` file in the root folder to tell sbt how we're going to build our project, 
and what dependencies we'll use. This will pull in the GeoTrellis library, as well as other necessary jars:

    name := "GeoTrellis Tutorial Project"

    scalaVersion := "2.10.0"

    libraryDependencies ++= Seq(
        "com.azavea.geotrellis" %% "geotrellis" % "0.8.0"
    )

#### HTTP Server Setup

GeoTrellis provides a class called [WebRunner](https://github.com/geotrellis/geotrellis/blob/0.8/src/main/scala/geotrellis/rest/WebRunner.scala)
that makes it very simple to start a Jetty runtime to provide endpoints for services.

We'll create our first source file, `src/main/scala/Main.scala`, with a main method that will
simply start the WebRunner:

    package tutorial

    import geotrellis.rest.WebRunner

    object Main {
      def main(args: Array[String]) = WebRunner.main(args)
    }

At this point we can run the project through sbt. Launch into the sbt prompt by issuing the `sbt` command in the project's root directory.
At the prompt, issue the `run` command. The result will be a server that is listening to port 8000. However, we haven't defined any services,
so if you try to access that port with your browser, you will get a `HTTP: 500` error.

Let's take a moment to look at how the `WebRunner` is configured. The `WebRunner` uses configuration settings to find the service classes. Here is
an example configuration, used as a default in the GeoTrellis [reference.conf](https://github.com/geotrellis/geotrellis/blob/0.8/src/main/resources/reference.conf):

    geotrellis.host = "0.0.0.0"
    geotrellis.port = 8000
    geotrellis.rest-package = "demo"

This configuration tells the ```WebRunner``` to by default use localhost, start on port 8000, and to search
the ```demo``` package for service objects. These configuration settings can be overridden by
your own scala application by overwriting these settings in  `application.conf`. To learn more 
about setting up TypeSafe configuration files, see [the project's documentation.](https://github.com/typesafehub/config)

Let's create `src/main/resources/application.conf` and modify some of these settings:

    geotrellis.port = 8888
    geotrellis.rest-package = "tutorial"
    
Now the WebRunner will start on port 8888, and look at the `tutorial` package for web services.

On to writing services.

#### Hello World

Let's start with a very basic web service. This service doesn't actually
use any GeoTrellis functionality, but will it will get us started.

Create the file `src/main/scala/Hello.scala` and add the following:

    package tutorial

    import javax.servlet.http.HttpServletRequest
    import javax.ws.rs.{GET, Path}
    import javax.ws.rs.core.{Response,Context}

    @Path("/")
    class Hello {
      @GET
      def get(@Context req:HttpServletRequest) = {
        val message = "Hello World!"
        Response.ok(message)
                .`type`("text/plain")
                .build()
      }
    }
    
Now if we issue the `run` command in sbt and send our browser to `http://localhost:8888/`,
we should see a friendly greeting.

Let's look at the different components that make this service work. First, that the object is declared
in `package tutorial` means that it is going to be found by the WebRunner, since we set the `tutorial`
package to be searched in the last step. The `@Path("/")` annotation tells Jetty that requests
sent to the root path of the server should be routed to this class. The `@GET` annotation
on the `get` method tells Jetty that a GET request to the root path should be handled by this method.
The method takes in an `HttpServletRequest` parameter marked with the `@Context` annotation, which
we do not use here. We simply use the `Response.ok` method to build a response that has the
data set to our message, and the MIME type set to `text/plain`. We return the built response,
which Jetty then marshals back to the client. 

#### The GeoTrellis Server

Throughout the rest of the tutorial, we will be using GeoTrellis operations to 
service the requests. GeoTrellis defines [operations](http://localhost:4000/operations/) 
that work with vector and raster geospatial data, as well as more simple types such as strings and integers.
An operation is constructed in code before it is actually executed. This allows
operations to be composed in a way where their execution happens only when needed.
This also allows for optimization and parrallization to occur in the execution
of composed operations.

The way to execute operations is to run them with a GeoTrellis `Server` object.
This server is a different concept then the Jetty server we are running to 
service the HTTP requests. It is an object that we construct, that knows about
where data lives, how to run operations in parrallel, and how to handle 
operation errors.

So, in order for our services to run operations, we need to construct a Server object.
To do so, we'll instantiate one inside the `Main` object in `src/main/scala/Main.scala`:

    package tutorial

    import geotrellis.rest.WebRunner
    import goetrellis.process.{Server,Catalog}

    object Main {
      val server = Server("tutorial-server", 
                          Catalog.fromPath("data/catalog.json"))
    
      def main(args: Array[String]) = WebRunner.main(args)
    }
    
Here we create a Server called "Tutorial Server", that uses a catalog defined by the file "data/catalog.json".

A `Catalog` is what a GeoTrellis server uses to define the data that can be used in the system.
It is defined with a JSON file that describes where the data is held. Let's define our
data now by creating a directory in the root direcotry called `data` and create the file `data/catalog.json`:

    {
     "catalog": "Catalog of Tutorial Data",
     "stores": [
      {
       "store": "tutoral:fs",
       "params": {
         "type": "fs",
         "path": "data/arg",
         "cacheAll": "no"
        }
      }
     ]
    }
    
This catalog defines one data store, which is the directory `data/arg`. This means any raster in ARG format 
found in that directory will be available to the Server. Note that a data store cannot be the same directory
as the catalog.json lives, because the Server will consider any JSON file in a data store directory to be a
layer definition for an ARG file.

We will put data to use in the data directory in a minute; for now, we can just create the `data/arg` directory and
leave it empty.

#### Adder

With that out of the way, here's a REST service that actually uses some simple GeoTrellis operations:
it treats the final part of the URL as a number, adds one to it, and returns
that number as plaintext. 

Create a new file `src/main/scala/AddOne.scala`:

    package tutorial
    
    import javax.servlet.http.HttpServletRequest
    import javax.ws.rs.{GET, Path, PathParam}
    import javax.ws.rs.core.{Response,Context}
    
    import geotrellis.Op
    import geotrellis.rest.op.string.ParseInt
    import geotrellis.Implicits._

    @Path("/addone/")
    class AddOne {
        @GET
        @Path("/{x}")
        def get(@PathParam("x") s:String,
                @Context req:HttpServletRequest) = {
            // parse the given integer
            val opX:Op[Int] = ParseInt(s)
    
            // add one
            val opY:Op[Int] = opX + 1
    
            // run the operation
            val message:String = try {
                val y:Int = Main.server.run(opY)
                s"The result is: $y"
            } catch {
                case e:Throwable => s"Error: $e"
            }
    
            Response.ok(message)
                  .`type`("text/plain")
                  .build()
        }
    }

After restarting the server, you can hit this endpoint at `http://localhost:8888/adder/127`.

Here we see a new Annotation with the `@Path("/{x}")`. What this means is that
a request with the path `/addone/{x}` will be routed to the method, where `{x}`
represents a parameter of the method. This parameter is marked as such with the
`@PathParam("x")` annotation.

The GeoTrellis operations that are in use in this example
are `ParseInt` and `local.Add`. While you don't see the latter one in code, it
is what the statement `opX + 1` implicitly converts to; `opX + 1` could have
been written as `geotrellis.raster.op.local.Add(opX,1)` with the same result.

An important thing to see here is that `ParseInt` doesn't actually do any
work at the time it is constructed. It creates an operation which when run will parse an input `String` and
return an `Int`. But running operations isn't the only thing you can do. In our
case, `opX + 1` actually builds us a new operation, which evaluates `opX` and
then adds one to it. If there is an exception (i.e. the parameter is not a
valid number) it will only occur when `Main.server.run` is called.

This means that instead of sprinkling error-handling code through your handler,
you only need to guard your calls to `Main.server.run`. Combining operations allows
the web service author to focus on correctly encoding application logic without
having to handle errors at every possible point.

Calling `Main.server.run` returns an integer value which can be used in a message
that completes the request.

#### Bounding Box Union

This example uses `geotrellis.Extent`, an object which represents a geographical 
bounding box. The service uses two extents, each encoded in a string as
`xmin,ymin,xmax,ymax`. For example, using the Web Mercator coordinate system a
bounding box around Philadelphia might be encoded as:

`-8475497.88486,4825540.69147,-8317922.88486,4954765.69147`

Create `src/main/scala/BoundingBox.scala` and add the following:

    package tutorial

    import javax.servlet.http.HttpServletRequest
    import javax.ws.rs.{GET, Path, PathParam}
    import javax.ws.rs.core.{Response,Context}
    
    import geotrellis._
    import geotrellis.rest.op.string.ParseExtent
    import geotrellis.raster.op.extent
    
    @Path("/bbox/")
    class BoundingBox {
        @GET
        @Path("/{extent1}/union/{extent2}")
        def get(@PathParam("extent1") s1:String,
                @PathParam("extent2") s2:String,
                @Context req:HttpServletRequest) = {
          // parse the given extents
          val e1:Op[Extent] = ParseExtent(s1)
          val e2:Op[Extent] = ParseExtent(s2)
    
          // combine the extents
          val op:Op[Extent] = extent.CombineExtents(e1, e2)
    
          // run the operation
          val message = try {
            val extent:Extent = Main.server.run(op)
            s"The Extent of the union is: $extent"
          } catch {
            case e:Throwable => s"Error: e"
          }
    
          Response.ok(message)
                  .`type`("text/plain")
                  .build()
        }
    }

This service takes two such extents and combines them, returning the smallest
extent that contains both of them. For instance, the request:

`http://localhost:8888/bbox/0,0,10,10/union/5,-10,15,0`

will result in `0,-10,15,10`.

#### Raster time

It's now time to work with some raster data. Download the 
[sample data set]({{ site.baseurl }}/data/tutorial.tar.gz)
and extract it's contents into the `data/arg` folder. Now when we restart
the tutorial server, the Main.server will have access to a raster named
`philly_inc_percap`. This a byte-valued raster containing data values representing
income per capita for the city of Philadelphia. This raster is in 
ARG format, as required by GeoTrellis.

ARG files are the format of rasters that can be read by GeoTrellis. The ARG format has been designed to give
maximum I/O performance. The ARG format has two files per raster: an .arg file, which contains the actual data, 
and a .json file, which has the metadata. Inside this metadata file, there is a field named "layer". This is the 
raster layer name. Naming the rasters allows us to refer to the data in web requests without actually knowing 
anything about where they are stored and what type of datastore the server is using. You can read more about
the ARG format [in the ARG specification document.](https://github.com/geotrellis/geotrellis/wiki/ARG-Specification)

#### Draw Raster - The Simple Version

Now that we have a raster, we will actually do some raster processing!
This example uses the simplified PNG API and color palettes that are 
newly included with GeoTrellis 0.8. 

Create the file `src/main/scala/DrawSimpleRaster.scala`:

    package tutorial

    import javax.servlet.http.HttpServletRequest
    import javax.ws.rs.{GET, Path, PathParam}
    import javax.ws.rs.core.{Response,Context}
    
    import geotrellis._
    import geotrellis.data.ColorRamps._
    
    @Path("/simpleDraw")
    class SimpleDrawRaster {
      @GET
      def get(@Context req:HttpServletRequest) = {
        val rasterOp:Op[Raster] = 
            io.LoadRaster("philly_inc_percap")
        val pngOp:Op[Array[Byte]] = 
            io.SimpleRenderPng(rasterOp, BlueToRed)
    
        try {
          val img:Array[Byte] = Main.server.run(pngOp)
          Response.ok(img)
                  .`type`("image/png")
                  .build()
        } catch {
          case e:Throwable => 
            Response.ok(s"Error: $e")
                    .`type`("text/plain")
                    .build()
        }
      }
    }

Now restart the server, and see the raster:

`http://localhost:8888/simpleDraw`

Given a `name`, the `io.LoadRaster` operation will return a `geotrellis.Raster`
instance containing the raster data who's layer name is the parameter. The server
can find this raster by name because of the setup with the Catalog we did earlier.

`SimpleRenderPng` takes in a raster and a color ramp. Color ramps have been
chosen by the designers at Azavea to handle representing common raster visualization 
use cases in an esteticly pleasing and informative way. You can see the different color ramps available in our 
[Color Documentation]( {{ site.baseurl }}/overviews/rendering.html).
The `SimpleRenderPng` operation returns a Byte Array which contains the raw PNG file. To return
this to the browser, we just return the data with the MIME type `image/png`.

#### Draw Raster - Choose Your Own Colors

Though using `SimpleRenderPng` makes it easy to color rasters and convert them
to PNGs, you might want more control over how your raster will look.
This example shows how to load raster data, create a palette of colors, 
assign those colors to value ranges (classes) in the raster, and create a 
PNG to send to the user.

    package tutorial

    import javax.servlet.http.HttpServletRequest
    import javax.ws.rs.{GET, Path, PathParam}
    import javax.ws.rs.core.{Response,Context}

    import geotrellis._
    import geotrellis.statistics.op._
    import geotrellis.rest.op.string.{SplitOnComma,ParseColor,
                                      ParseInt}
    
    @Path("/draw/")
    class DrawRaster {
      @GET
      @Path("/palette/{palette}/shades/{shades}")
      def get(@PathParam("palette") palette:String,
              @PathParam("shades") shades:String,
              @Context req:HttpServletRequest) = {
    
        // load the raster
        val rasterOp = io.LoadRaster("philly_inc_percap")
    
        // find the colors to use
        val paletteOp =
          logic.ForEach(SplitOnComma(palette))(ParseColor(_))
        val numOp = ParseInt(shades)
        val colorsOp = stat.GetColorsFromPalette(paletteOp, numOp)
    
        // find the appropriate quantile class breaks to use
        val histogramOp = stat.GetHistogram(rasterOp)
        val breaksOp = stat.GetColorBreaks(histogramOp, colorsOp)
    
        // render the png
        val pngOp = 
          io.RenderPng(rasterOp, breaksOp, histogramOp, 0)
    
        // run the operation
        try {
          val img:Array[Byte] = Main.server.run(pngOp)
          Response.ok(img)
                  .`type`("image/png")
                  .build()
        } catch {
          case e:Throwable => 
            Response.ok(s"Error: $e")
                    .`type`("text/plain")
                    .build()
        }
      }
    }


The `palette` and `shades` arguments are used to construct the color palette to
use. For example:

`http://localhost:8888/draw/palette/ff0000,0000ff/shades/5`

specifies that the palette should be a gradient from red (`ff0000`) to blue
(`0000ff`) containing 5 colors. The colors chosen in this case would be:

 * red (`ff0000`)
 * reddish-purple (`bf003f`)
 * purple (`7f007f`)
 * bluish-purple (`3f00bf`)
 * blue (`0000ff`)

The rest of the code builds a `geotrellis.statistics.Histogram` object (using
`GetHistogram`) to determine what value ranges should map to which colors
(using `GetColorsBreaks` to create a `geotrellis.data.ColorBreaks`). The idea is to try to 
find ranges of equal size in the raster, so that the 5
colors are evenly used. Thus, assuming our values ranged from 0-100, we might
create the following ranges (also know as "breaks"): 

 * 0-12: red
 * 13-30: reddish-purple
 * 31-36: purple
 * 37-60: bluish-purple
 * 61-100: blue

Finally, we render the PNG using the raster and color breaks we found.

Again, remember that none of this work is happening until after the "run the
operation" comment. This means that any errors (e.g. invalid colors, invalid
raster, other problems) won't happen until that point. It also means that we
could perform as many raster transformations as we want without needing to modify any
of the rendering code, or the error-handling.   

One thing to note is that this code is not doing any kind of resampling or
resizing. In your own code, you will usually want to load raster data for a
particular extent (e.g. a tile) at a particular resolution (e.g. 256x256). This
services loads and renders the entire raster at its underlying resolution,
which can have performance implications.    

#### Conclusion

I hope this walkthrough of building web services with GeoTrellis has
provided some insight. If you have questions or comments, drop us a 
line on the [mailing list](https://groups.google.com/group/geotrellis-user) or on 
the #geotrellis IRC channel on freenode. You can also check out the 
[demo project]({{ site.baseurl }}/tutorials/demo.html) for more examples.

All code in this tutorial can be found at [https://github.com/lossyrob/gt-tutorial](https://github.com/lossyrob/gt-tutorial)
