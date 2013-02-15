---
layout: gettingstarted
title: Loading Your Data

tutorial: gettingstarted
num: 4
outof: 9
---

#### Azavea Raster Grid Format

GeoTrellis uses the ARG data format for all raster calculations. The
spec can be found at
[https://github.com/geotrellis/geotrellis/wiki/ARG-Specification](https://github.com/geotrellis/geotrellis/wiki/ARG-Specification).

The recommended way to convert raster data into the ARG format is by using a command line tool we provide to 
convert GeoTiff raster files.  To install the command line tool (gt-tool), you should first installation program called conscript, following
[the instructions on the Conscript page][csrm]. 

Once conscript is installed, run the following at a command prompt to install gt-tool:

    cs geotrellis/geotrellis

Once installed, you can convert a GeoTiff with a command like the following:

    gt-tool import -d /var/geotrellis/data -i /tmp/input.tif -n name_of_raster

Note that you will need to replace "/var/geotrellis/data" with the directory you wish to use to store data, "/tmp/input.tif"
replaced with the name of the file to import, and "name_of_raster" with the name you wish to give the output raster.

For more information, run: 

    gt-tool --help 

If your data is not in the GeoTiff format, we recommend using the excellent [GDAL project](http://www.gdal.org/) for data conversion.
In the upcoming 0.10 release of GDAL, there is direct support for converting files into the ARG format, but because of some common
complexities that arise when using GDAL directly, we advise converting to GeoTiff and using our command line tool.  

(If you do wish to use GDAL, you will need to understand some technical details: Byte in GDAL is unsigned, whereas Byte in GeoTrellis and the JVM is 
signed.  Also be aware that ARG has fixed NoData values that are not currently handled correctly in all cases in GDAL.)
 

#### Loading Directly from the File System

GeoTrellis can load ARG files directly with the [*io.LoadFile*](http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadFile)
operation.

     val raster:Op[Raster] = io.LoadFile("/path/to/raster.arg")


#### Using a catalog file

A more common way to load files is to use a "catalog" file. Catalog
files are json files with a format like:


     {
      "catalog": "my-catalog",
      "stores": [
       {
        "store": "data:fs",
        "params": {
          "type": "fs",
          "path": "/var/rasters/"
        }
       }
      ]
     }

Where the *path* element is a path to a directory of rasters.

The *data:fs* type assumes that all .json files in the *path* directory
are arg files. This means that you must not store the catalog file in
the same directory.

To get rasters that are based on a catalog you can use the
[*io.LoadRaster*](http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadRaster) operation. In addition, you need to tell your execution server where the catalog file is.

     // Bind our catalog to the server
     val server = Server("exec", "/path/to/catalog.josn")

     // Load the entire raster
     val rasterOp:Op[Raster] = io.LoadRaster("land_use_5m")

     // Execute the operation
     val raster:Raster = server.run(rasterOp)

Operations for loading and writing data can be found in the
[*geotrellis.io* package](http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.package)

#### Creating New Rasters

You can create raster data directly in GeoTrellis as well. Rasters are
generally backed by arrays so creating a new raster is as simple as
wrapping an *ArrayRasterData* with a *Raster*.

    // Compute the distance from (x,y) to each point in this raster

    // Creates an extent around the Philly area
    val extent = Extent(-8507622, 4804712,
                        -8342022, 4996142)

    val cols = 5520
    val rows = 6381
    val resolution = 30.0
    val rasterExtent = RasterExtent(
        extent, resolutions, resolutions, 5520, 6381)

    val x = -8421501.0
    val y = 4854122.0

    // Convert x,y into grid coords
    val (xg,yg) = maptoGrid(x,y)

    // Create a new wrapped array
    val arrayData:DoubleArrayRasterData =
        DoubleArrayRasterData.empty(cols, rows)

    for(col <- 0 until cols ;
        row <- 0 until row) {
        val dist = math.sqrt((xg - col) * (xg - col) + 
                             (yg - row) * (yg - row))
        arrayData.setDouble(col, row, resolution * dist)
    }

    // Create the new raster
    val r: Raster = new Raster(arrayData, rasterExtent)


#### Vector Data

While GeoTrellis doesn't bundle any vector reading tools by default we
recommend using [GeoSlick](https://github.com/ahinz/GeoSlick) to talk to
a PostGIS database.

    import geoslick.PostgisDriver.simple._
    import Database.threadLocalSession

    object Country
       extends Table[(Int,String,Geometry)]("county")
       with Postgis {

      def id = column[Int]("id", O.PrimaryKey, O.AutoInc)
      def name = column[String]("name")
      def continent = column[String]("continent")
      def geom = geoColumn[Polygon]("geom", 3857)

      def * = id ~ name ~ continent ~ geom
    }

    val europeanCountriesQuery = for {
        c <- Country if c.continent === 'europe'
    } yield (name, geom)

    val europeanCounties:List[(String,Geometry)] =
        europeanCountriesQuery.toList

    // Convert these to geotrellis 'features'
    val euFeatures:Seq[Polygon[String]] =
       for( (country, geom) <- europeanCounties )
           yield feature.Polygon(geom, country)

    // Represents a raster of carbon produced
    // around the world (each cell is lbs of carbon)
    val carbonRaster:Op[Raster] =
        io.LoadRaster("carbon-produced-world")

    val euCarbonSums:Seq[Op[Long]] =
        for( polygon <- euFeatures)
            yield (polygon.data,
                   zonal.Sum(carbonRaster, polygon, Map.empty()))

    val euCarbonSumsOp:Op[Seq[Long]] =
        logic.Collect(euCarbonSums)

    val server = Server("exec","/path/to/catalog.json")
    val actualSums:Seq[Long] = server.run(euCarbonSumsOp)

    val dict: Map[String,Long] = Map(
        euFeatures.map(_.data).zip(actualSums):_*)



#### Tiles

If you have a really large data set that doesn't easily fit into memory
you can create tiled rasters. 


[csrm]: https://github.com/n8han/conscript#readme
