---
layout: glossary
title: Glossary
---
<div class="filterbar">
  <span class="title">Look up a term</span>
  <input class="field" id="filter" type="text" />
  <span id="filter-count"></span>
</div>






* #### Akka


* #### ARG - Azavea Raster Grid


* #### ASCII GRID - A text-based file format for encoding RASTER data.  Originally developed by Esri, the file format is an open, non-proprietary format.  See also http://en.wikipedia.org/wiki/Esri_grid
http://docs.codehaus.org/display/GEOTOOLS/ArcInfo+ASCII+Grid+format#ASCIIGrid


* #### Aspect - The direction in which land surface faces. The data is usually represented as an integer value expressed as the number of degrees offset from north.


* #### Cartographic Modeling - see [map algebra](#map_algebra)


* #### Cell - The smallest square in a grid.  A cell is the fundamental unit of a [raster](#raster) data set and is sometimes used interchangably with the term [pixel](#pixel).  Usually, it represents a rectangular area organized into an array of data values.


* #### Cell Size - The linear size in map units of the smallest area (the [cell](#cell) or [pixel](#pixel)) in a [raster](#raster) data set.  For example, most land cover data derived from the Landsat satellite is usually published with a 30 meter cell size.


* #### Cellular Automata


* #### Convolution - A type of [Focal](#focal_operations) operation in which a numerical weight is applied to each cell in the neighborhood (or "kernel").  [Kernel Density](#kernel_density_estimation) (KDE) is an example of a convolution, but they can be used for many purposes.  In Map Algebra terms, a convolution is a FocalDistribution operation.
GeoTrellis Docs - Convolve Operation - http://azavea.github.com/geotrellis/latest/api/#geotrellis.raster.op.focal.Convolve


* #### Coordinate System - A fixed reference frame superimposed on the surface of the earth (or other planet) in order to designation the location of a point.  The EPSG Geodetic Parameter Registry (http://www.epsg-registry.org/) is a list of standard coordinate systems and their geodetic parameters used for representing the Earth's surface.  It is maintained by the Geomatics Committee of the International Association of Oil and Gas Producers (OGP).


* #### Cost Distance - A class of [Focal operations](#focal_operations) in which distance from each cell to the nearest "source" or "target" is computed.  Rather than the linear or "Euclidean" distance, the distance is computed by accumulating a "cost" (sometimes referred to as "friction") to travel from one cell to another.  The cost is usually represented by a second [raster](#raster) data set in which the cost is a numerical value associated with each cell.  In addition to a cost factor, some GIS systems support the addition of vertical and horizontal restrictions on movement in order to better model dispersion and flow in certain kinds of systems.  For example, more gas is required to drive a car uphill than downhill or to drive against he wind, so there is not only a friction component but the direction of travel affects the cost.

See also: 
EUCLIDEAN DISTANCE
ArcGIS Resource Center - Understanding Cost Distance Analysis - http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//009z000000z5000000.htm
ArcGIS Resource Center - Understanding Path Distance Analysis - 
http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_path_distance_analysis/009z00000022000000/


* #### DEM - Digital Elevation Model - A digital representation of elevation on a land surface.  A DEM is mostly commonly a raster data structure, though triangulated irregular networks (TIN) and contour lines can also be generated from a DEM.  The US Geological Survey has also defined an open elevation file format commonly referred to as USGS DEM. (http://en.wikipedia.org/wiki/USGS_DEM)



* #### Euclidean Distance - A class of [Focal operations](#focal_operations) in which linear (straight-line or "Euclidean") distance from each cell to the nearest "source" or "target" is computed.  Usually, this is done from cell center to cell center.  In addition to distance, separate operations are usually provided for determining Direction to the source and allocating a unique identifier for the nearest source.

See also: 
COST DISTANCE
ArcGIS Resource Center - Understanding Euclidean Distance Analysis - http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_Euclidean_distance_analysis/009z0000001t000000/


* #### Focal Operations - A class of [Map Alebra](#map_algebra) operations in which a data set is transformed based on the cells around each cell.  The cells that define "neighborhood" can take many forms, including rectangular, circular, donuts or wedges and more complex operations can be defined by using neighborhoods in which cell has an additional weight defined.   Focal operations are sometimes organized into those in which only the immediate neighborhood is considered and those that include an extended neighborhood.  [Cost Distance](#cost_distance) and [Euclidean Distance](#euclidean_distance) operations are usually considered part of the exended neighborhood group.


* #### GeoTIFF - An extension of the Tag Image File Format (TIFF) [raster](#raster) file format developed to include additional metadata required for storing geospatial data.  The TIFF file was original developed by Aldus Corporation.


* #### Geoprocessing - The process of transforming one or more geospatial data structures into others.  Often, this involves the application of one or more OPERATIONS performed on data using GIS software.  A geoprocessing operation typically (1) ingests a spatial data set, (2) transforms the data or uses the data to compute a new value, and (3) outputs a new spatial dataset. Geoprocessing operations can be automated and shared through the creation of tools in scripting languages, and can be combined and sequenced to create geoprocessing models.


* #### GDAL - Geospatial Data Abstraction Library - http://www.gdal.org/ - An open source software project that provides raster data format translation capabilities.  The GDAL project has both command line utilities and services as a key raster I/O library for many commercial and open source projects.


* #### GRID (Esri GRID) - A proprietary raster data storge format developed by Esri. Like most raster data storage formats, GRIDs represent continuous, field-based attributes (such as elevation, temperature or land cover) by organizing geographic space into an array of square cells. A GRID is stored in a separate directory with associated tables and files containing information about that GRID's geography, attributes and processing history.  The Esri GRID data structure is very common, but GeoTrellis cannot use it directly and we recommend using GDAL, ArcGIS or other software to convert to GeoTIFF.  You can also use a recent build of GDAL to convert directly to the ARG file format used internally by GeoTrellis.  See also 
http://en.wikipedia.org/wiki/Esri_grid
http://support.esri.com/en/knowledgebase/techarticles/detail/30616


* #### Hillshade - A raster data set in which each pixel has a gray-scale value representing "shadows" in order to simulate the effect of the sun's light on a land surface.  A hillshade effect can be achieved by assigning an integer value based on an azimuth and altitude parameter for the sun.  In Map Algebra terms, Hillshade is a FOCAL operation because it uses the elevation, aspect and slope values around each cell in order to compute the illumination value.


* #### Image Classification - The process whereby features are identified from images captured by satellite or aerial photography by grouping pixels with similar characteristics.


* #### Interpolation - A set of techniques for estimating missing values in a continuous surface based on a smaller number of known values.  


* #### JTS - Java Topology Suite - An open source Java library for manipulating [vector](#vector) geospatil data through a set of planar geometry functions.  The JTS library is a foundation library for many open source and commercial software pacs.  It is licensed under the LGPL (http://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License).  JTS has been ported to C++ as the GEOS library (http://trac.osgeo.org/geos/) and to .Net as the Net Topology Suite.  GeoTrellis uses JTS to provide some of its [vector](#vector) spatial operations.


* #### Kernel


* #### Kernel Density Estimation
See also:
Wikipedia: Kernel Density Estimation - http://en.wikipedia.org/wiki/Kernel_density_estimation
ArcGIS Resource Center - Understanding Density Analysis
http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_density_analysis/009z0000000w000000/
ArcGIS Resource Center - How Kernel Density Works
http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html# Analysis/How_Kernel_Density_works/009z00000011000000/
GeoTrellis Docs - KernelDensity operation - http://azavea.github.com/geotrellis/latest/api/#geotrellis.raster.op.focal.KernelDensity
Applying Map Algebra – Part 1
http://www.azavea.com/blogs/atlas/2013/01/applying-map-algebra-part-1/


* #### Kriging - An [interpolation](#interpolation) technique in which measurement of spatial variation between the known points is used to estimate the unknown values being interpolated.


* #### Local Operations


* #### Map Algebra - A formal system describing various functions and processes that can be used to manipulate geospatial data.  Originally developed by C. Dana Tomlin, Map Algebra is both a computation language and a general system for combining and transforming geospatial data by decomposing data and data processing into basic building blocks that can be recomposed with great flexibility.  Map Algebra operations are usually organized into [Local](#local_operations), [Focal](#focal_operations) and [Zonal](#zonal_operations) operations.  While not explicitly limited to [raster](#raster) data, it is most commonly associated with manipulation of [raster](#raster) data sets.  Map Algebra was first published as Tomlin's PhD thesis and then as Geographic Information Systems and Cartographic Modeling, a Prentice-Hall book published in 1990.  A revised version of the book, GIS and Cartographic Modeling was released by Esri Press in 2012.  


* #### Manhattan Distance - The distance between two points as measured by the number of grid cells in each direction


* #### Multi-Band Raster - A single raster data file that incorporates multiple raster data sets by including, for example, visible and infrared wavelengths as two different bands.


* #### Multi-Spectral Data - Satellite or aerial photography collected in two or more wavebands.


* #### Neighborhood Operations - See [Focal Operations](#focal_operations)


* #### Operations


* #### Pixel - Short for "pixel element", colloquially, a pixel refers to the smallest element of a display device.  In remote sensing, it also refers to the fundamental unit of data in a [raster](#raster) data set and is used interchangably with the term [cell](#cell).  Usually, it is a rectangular cell organized into an array of data values.


* #### Projection or Map Projection - A mechanism by which the curved surface of the Earth (or other planet) is represented on a flat surface.  The map projection is key parameter of the [coordinate systems](#coordinate_systems) used to encode geospatial data sets.


* #### Raster Data - A geospatial data structure that organizes numeric values into a rectangular array of equal-sized cells (or pixels). Unlike a [vector](#vector) data sets, which stores coordinates explicitly, raster coordinates are implicity in the ordering of the matrix. Groups of cells that share the same value represent the same type of geographic feature.


* #### Scala


* #### Supervised Classification


* #### Unsupervised Classification


* #### Vector Data - A geospatial data structure in which the location of features or objects is represented by one or more coordinate pairs, usually based on a Cartesian coordinate system.  Two-dimensional vector data usualy consist of points, lines or polygons.  Each point feature is represented as a single coordinate pair, while line and polygon features are represented as ordered lists of vertices. Multiple attributes can be associated with each vector feature.


* #### Zonal Operations


