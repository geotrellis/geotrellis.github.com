---
layout: overviews
title: The Catalog

tutorial: overviews
num: 2
---

    {
      "catalog": "Catalog of Test Data",
      "stores": [
      {
        "store": "test:fs",
        "params": {
          "type": "fs",
          "path": "src/test/resources/data",
          "cacheAll": "no"
        }
      }
      ]
    }
    
GeoTrellis needs to know where to find data in order to perform it's magic. One way you can tell GeoTrellis where to find rasters is to use the [io.LoadFile operation](http://geotrellis.github.io/scaladocs/0.8/#geotrellis.io.LoadFile). Another way is to create a .json file called a *catalog*. This file tells the GeoTrellis system how to find Rasters that are referred to by name. The raster's name is declared in the [.json metadata file for the ARG as the 'layer' attribute](https://github.com/geotrellis/geotrellis/blob/0.8.1/src/test/resources/sbn/SBN_co_phila.json#L7). Any arg file that is contained in a Data Store declared by the catalog is available to be loaded by GeoTrellis through the [io.LoadRaster](http://geotrellis.github.io/scaladocs/0.8/#geotrellis.io.LoadRaster) operation. 

To let the GeoTrellis server know where to find the catalog, set the ```geotrellis.catalog``` setting in the application.conf

#### Why use a Catalog?

Using the Raster's name to load it into GeoTrellis allows for flexibility in the file storage of your raster data. Code that can run on one set of data can be moved to work with another set, just by changing where the catalog is pointing. Also, using a simple name to refer to raster layers allows for REST calls to include the layer name in query parameters. This lets the client be able to easily declare what server side data to operate on. If you're making a web map that has multiple raster layers, you can dynamically make calls out to GeoTrellis on any one or all the layers by passing through the name of the rasters. For an example of this, see the [admin tool's WMS call](https://github.com/geotrellis/geotrellis/blob/0.8.1/server/src/main/scala/geotrellis/admin/services/Layer.scala#L44).
