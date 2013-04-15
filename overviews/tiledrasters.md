---
layout: overviews
title: Tiled Rasters

tutorial: overviews
num: 7
---

To understand the importance of tiled rasters in GeoTrellis, it's helpful
to think about the difference between task parallelism and data parallelism.
Task parallelism involves taking a single piece of work and dividing it up
into different kinds of tasks, and then, where possible, performing some of 
those tasks at the same time.  In GeoTrellis, each operation is a single
unit of work and it is usually the case that compound geoprocessing operations (made out of individual operations) have chains of operations that can be
executed at the same time.   Data parallelism, on the other hand, involves
executing the same work on different data at the same time. 

In most real world problems that benefit from distributed or parallel 
computing, both task and data parallelism are useful.  In GeoTrellis, the
primary method of data parallelism (with raster data) is executing operations 
on tiled rasters, which are individual raster layers that have been
divided into regular grids of smaller rasters.  For example, a 10k by 10k cell
raster could be divided into 100 smaller rasters that are 1k by 1k cells each.
You can think about a tiled raster as a distributed data source, as we cannot
assume we can load the entire dataset in memory at any one time.

At the current stage of development, using tiled rasters in GeoTrellis does
unfortunately require specialized data processing and programming.  One reason
this is the case it is far faster to operate on arrays in memory when possible.
As we approach GeoTrellis 1.0, we hope to make the process more transparent for 
simple models.  But while there is still much work to be done, there is useful
infrastructure in place for developing services that operate on tiled raster
sets.  As this functinality is still a work in progress, I'll mention plans
for future development alongside the current functionality.

## The tiled ARG format 

On disk, a tiled ARG is a directory full of individual ARG files (each with their own json metadata) with a single master metadata file.  If a tile is entirely
NoData (every cell has no value), there will be no data file for that tile.  In the future, we will support this same functionality for tiles with a
single value.  The filename of each tile has a suffix with the row and column of the tile.  Each
tile has the same width in pixels and the same height in pixels: for example,
a common tile size is 512 by 512 or 1024 by 1024.

## Creating a Tiled Raster 

You will need to use the command line gt-tool to create a tiled raster.  See
the getting started guide for more detalis about installing gt-tool.

At the current time, creating a tiled raster from a source raster that is 
larger than 2.3 GB requires GDAL 1.10 to be installed on your system.  (In
the future, this will not be necessary.)  

You will need to decide what size tiles to create.  The ideal size will vary
based on your specific application: you may wish to create several tilesets and
test the performance of each.  Generally speaking, 512x512 may be a good choice
to start with.  It is important to keep in mind that every tile is the same
size regardless of the source data.  If your source raster is 5500x5500 and
you create 1000x1000 tiles, the tiles on the right and bottom edge will have
500 extra NoData cells, which can create extra work for your service.

For creating the tile, you should use the "import-tile" gt-tool task.

The options for gt-tool are:
  -i  Path of the input raster file (which can be geotiff, ARG, or another GDAL supported raster format)
  -d  Output directory for tiles
  -n  Name of the output raster
  -cols  Pixel columns (pixel width) per tile
  -rows  Pixel rows (pixel height) per tile

For example, a sample usage could look like:

    gt-tool import-tile -i /var/geotrellis/input/mydata.tif -d /var/geotrellis/data/mydata/ -n mydata -cols 512 -rows 512 

There is also a gt-tool task called "import" that will create a tiled raster
directly from an ARG file that doesn't depend on GDAL, but can only process
raster files smaller than 2.3 GB.

## Loading a Tiled Raster

The operation io.LoadTileSet will load a tiled raster into memory given a path
to a tile directory.  

Raster.loadUncachedTileSet() will load an uncached tileset into memory, which
creates a Raster object for transformation that loads individual tiles from 
disk when necessary.

In the future, this functionality will be expanded to allow tiled rasters to be
included in the GeoTrellis catalog, as well as to provide a third alternative that
temporarily caches tiles for efficient focal operations on tiled rasters on disk 
(see raster.TileNeighborhood). 

## Treating an untiled raster as a tiled raster

If you have an untiled raster, but you want to treat it as a tiled raster for parallelization purposes, 
you can either create a tiled raster in memory or you can simulate one by using the LazyTiledWrapper 
and TiledLayout classes directly (at a performance cost).  In the future, there will be operations
to implement these transformations.

    def buildTiledRaster(r:Raster, pixelCols:Int, pixelRows:Int) = 
      Tiler.createTiledRaster(src, pixelCols, pixelRows)
    
    def untiledRasterAsTiledRaster(r:Raster, pixelCols:Int, pixelRows:Int):Raster = {
      val tileLayout = Tiler.buildTileLayout(r.rasterExtent, pixelCols, pixelRows)
      Raster(LazyTiledWrapper(r.data, tileLayout), r.rasterExtent) 
    }


# Operations on Tiled Rasters

While in the future we hope to unify all operations to seamlessly operate on tiled and
untiled rasters, at the moment it is necessary to know whether individual operations
have been implemented to handle tiled rasters.  

## Map/Reduce style Summary operations

As designed, a core function of tiled rasters is to allow operations on rasters too large to fit in memory.
The logic.TileReducer class be extended to create operations that perform an operation on each individual
tile (the mapper) and then perform an operation to combine the results of those operations (the reducer).
Examples of operations that implement this interface are stats.Min and stats.GetHistogram.

## Local operations

By default, local operations on tiled rasters are lazy -- chained local operations are combined into 
a single compound operation that is only run when necessary.  Because of this, it is safe to use
local operations as part of your tiled raster operations.  However, you should not *only* use local
operations on a tiled raster as you cannot assume that the raster can fit into memory on a single
machine to produce a result.  For example, you might summarize the results of your raster transformed
by local operations. 

### Focal operations

Most focal operations can be used on tiled raster data, through the use of the "TileFocalOp" operation.
Instead of specifying the raster as an argument to the operation, use an underscore like in the following 
example:

      val tileFocalOp = TileFocalOp(tiledR, Min(_, Square(1)))
 
In the future, we hope to eliminate the TileFocalOp operation and allow focal operations to work
directly with tiled rasters.

## Polygonal/Zonal Summary

The zonal summary (with polygonal area) operations takes advantage of tiled rasters by allowing
the service builder to cache intermediate results by tile.  For example, the following example
creates a map of intermediate results by tile (finding the minimum value in each tile). 

    object MinService {
      // create the result cache once when loading this class
      val tileMins = zonal.summary.Min.createTileResults(rData, rasterExtent)
    }

    class MinService {
      // use result cache when creating this operation with specific raster & polygons
      def minOperation(raster:Raster, zone:Polygon[_]) = zonal.summary.Min(raster, zone, tileMins)
    }
