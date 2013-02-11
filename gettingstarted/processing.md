---
layout: gettingstarted
title: Processing Data

tutorial: gettingstarted
num: 5
outof: 9
---

#### Operations

All GeoTrellis computations run in an operation context. To actually
evaluate a result you must execute the operation with
[*server.run*]({{site.baseurl}}/latest/api/#geotrellis.process.Server).

An up to date list of operations can be found on the
[operations]({{site.baseurl}}/operations/rasterops.html) page.

#### Examples

##### Weighted Overlay

    val rasters = List("raster1", "raster2", "raster3")
    val weights = List(1,2,3)

    // Load the rasters
    val rasterOps:List[Op[Raster]] =
    for( raster <- rasters) yield io.LoadRaster(raster)

    // Multiply each raster by the weight
    val multRasterOps:List[Op[Raster]] =
        for( (raster, weight) <- rasters.zip(weights))
            yield local.Multiply(raster, weight)

    // Add all the rasters together
    val rasterSum:Op[Raster] = local.Add(multRasterOps:_*)

    val weightSum = weights.reduceLeft(_ + _)
    val overlayOp:Op[Raster] = local.Divide(rasterSum, weightSum)

    // Run
    val s = process.Server("exec","/path/to/catalog.json")
    val overlay:Raster = s.run(overlayOp)

##### Reclassify Raster

    val rasterOp:Op[Raster] = io.LoadRaster("land-use")

    // The land use raster has the following values:
    // 1- Water
    // 2- Farm
    // 3- Industrial
    // 4- Commercial
    / 5- Residential

    val landAreas:Op[Raster] = logic.DoCell(rasterOp) { cell =>
       if (cell > 1) 1
       else NODATA
    }
