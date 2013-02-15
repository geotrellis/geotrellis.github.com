---
layout: gettingstarted
title: Rendering and Output

tutorial: gettingstarted
num: 6
outof: 9
---

#### Getting Your Data Out

#### Statistics

GeoTrellis has a suite of statistics operations that can be run on
rasters. Most of the simple statistic operations are in the
[*statistics* package](http://geotrellis.github.com/scaladocs/latest/api/#geotrellis.statistics.op.stat.package).

To get a histogram, for example, you can use the
[*stat.GetHistogram* operation](http://geotrellis.github.com/scaladocs/latest/api/#geotrellis.statistics.op.stat.GetHistogram$).

There are two types of histograms in GeoTrellis. One that uses a
hashtable to store the values and another that uses an array. The
array-based one is much faster but requires an array with a length equal
to the largest value in the raster.

    val rasterOp:Op[Raster] = // get a raster from somewhere

    val mapBasedHistOp:Op[Histogram] = stat.GetHistogram(rasterOp)

    // If we know the maximum value in our raster we can gain
    // a huge speed boost by providing that as an input to GetHistogram
    val arrayBasedHistOp:Op[Histogram] = 
        stat.GetHistogram(rasterOp,1000)


The Image Rendering APIs are covered in the
[Rendering Images]({{site.baseurl}}/gettingstarted/rendering.html) section.

#### Images

One way to visualize raster data is to render it to an image. GeoTrellis
supports rendering directly to PNG.

    val rasterOp:Op[Raster] = // get a raster from somewhere
    val pngOp:Op[Array[Byte]] = io.SimpleRenderPng(rasterOp)

#### REST

GeoTrellis is generally meant to be used with REST to implement
real-time processing. By default GeoTrellis includes *jax-rs* web
services.

    import javax.ws.rs.{Path,GET,Response}

    object App { val server = process.Server("exec") }

    @Path("/heatmap")
    class SomeResource {
      def extentFromPoint(p: Point[_]) =
          Extent(p.geom.x, p.geom.y,
                 p.geom.x, p.geom.y)

      @GET
      def heatmap() = {
         val pts:Seq[Point[Int]] = // get points from somewhere

         // Create an extent from the points
         val extent = pts.map { p => extentFromPoint(p) }
                         .reduceLeft { (e1,e2) => e1.combine(e2) }

         // Wrap this in a raster extent
         val width = 500
         val height = 500

         val rasterExtent = 
             new extent.GetRasterExtent(extent, width, height)

         // Transformation on vector types
         // In this case we have Points containing integers (type of
         // Point[Int]) and we want to use that value as the seed
         // value for the heatmap so we use an identity transform
         val tx = (a: Int) => a

         // Here we're using a Gaussian kernel
         val kernel:Op[Kernel] = 
             focal.CreateGaussianRaster(40,1,1,15,100)

         // A heatmap is just a kernel density operation
         val heatmapOp:Op[Raster] =
             focal.KernelDensity(pts, tx, kernel, rasterExtent)

         Response.ok(data).`type`("image/png").build()
      }
    }

#### File System

If you're doing static raster analysis and you want to save your
intermediate products you can write your arg files to disk.

    val rasterOp:Op[Raster] = // get a raster from somewhere

    val server = process.Server("exec")
    val raster:Raster = server.run(rasterOp)

    val data:RasterData = raster.data
    val path = "/path/to/write/raster/"

    // It is possible we're working with tiled data,
    // in which case we can't just use the default 
    // writer to write out the tiles.
    val writer:Option[Writer] =
         data.asArray map { arrayRasterData =>
              new ArgWriter(arrayRasterData.getType)
              // Could also return an AsciiWriter:
              // AsciiWriter
          }

    writer match {
         case Some(writer) => 
             writer.write(path, raster, "raster name")
         case None => 
             sys.error("Could not write non-array backed raster")
    }
