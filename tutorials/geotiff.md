---
layout: tutorials
title: GeoTiff Conversion

tutorial: tutorials
num: 3
---

In this tutorial we'll go over working with and viewing GeoTIFF data in GeoTrellis. The code that goes along with this code can be [found here](https://github.com/lossyrob/gt-ned-tutorial).

#### The Data

The data we will be working with is [National Elevation Dataset 10 Meter 7.5x7.5 minute quadrangle for Pennsylvania](http://www.pasda.psu.edu/uci/MetadataDisplay.aspx?entry=PASDA&file=ned_10meter_quads.xml&dataset=10). The data is archived at [this ftp site](ftp://www.pasda.psu.edu/pub/pasda/ned/10meter_quads/) in many seperate archived GeoTiffs. 

The first thing we're going to do is download on of the archives and see what it looks like. Download one of the areas (for example [Philadelphia](ftp://www.pasda.psu.edu/pub/pasda/ned/10meter_quads/ned10m_PHILADELPHIA_PA_39075h2.zip)). In the extracted data, we'll find a .tif file. This is the GeoTiff file we'll be working with.

#### Converting to ARG format

To be able to work with Rasters in GeoTrellis, they need to be in the [ARG file format](https://github.com/geotrellis/geotrellis/wiki/ARG-Specification). The way we can do this is using the gt-tool script. You can download the gt-tool script from the [GeoTrellis scripts folder](https://raw.github.com/geotrellis/geotrellis/master/scripts/gt-tool), or in the root folder of the code for this tutorial. We can convert our GeoTIFF to an ARG using the geotiff_convert subcommand:

    gt-tool geotiff_convert -i ned10m39075h2.tif -o philly_ned.arg -n philly_ned
    
This will produce two files: the philly_ned.arg data file and philly_ned.json metadata file. We need to drop this in a folder that is stated in our GeoTrellis catalog. In the code for this tutorial, the catalog is located in the ```data``` folder, and points to the ```data/ned```, which does not exist in the repository initially. Create that folder and drop the ARG files in. 

#### First Viewing

Run the GeoTrellis server by running the ```./sbt run``` command in the root directory of the code project. You'll then be able to go to http://localhost:8880/admin to see the Philadelphia NED data using the GeoTrellis admin tool. You should see something like this:

<img src="/images/tutorials/geotiff-preproj.png" style="width: 600px;"></img>

You might be able to recognize the shape of Philadelphia, but the raster is clearly in the wrong spot. This is because the GeoTrellis admin tool displays the rasters in the Web Mercator (ESPG:3857) projection. If the raster is not in this projection, you will still be able to see the raster, but it won't be placed correctly. However, if we want to view the raster properly on the map, we can use GDAL to reproject the raster into Web Mercator.

#### Reprojecting with gdal_warp

This step requires that you have [GDAL](http://www.gdal.org/) installed. For a script to build and install gdal on Ubuntu, see [this gist](https://gist.github.com/lossyrob/4348503).

To reproject the original GeoTIFF raster, we run the gdal_warp on our raster:

    gdalwarp -t_srs EPSG:3857 ned10m39075h2.tif wm-ned10m39075h2.tif
    
This will reproject the raster to the proper projection. We can now use gt-tool to convert the GeoTIFF into ARG format, and view it through GeoTrellis on the proper part of the map.

#### Getting more data

Included in the codebase is a python script that will download all the data available for Pennsylvania NED data. Running it will populate the catalog with a set of rasters that gives the elevation of various points in PA. It simply downloads the archive, reprojects the GeoTIFF file, and converts it to an ARG file.



