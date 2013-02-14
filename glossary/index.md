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
[Akka](http://akka.io/) is a framework developed using the Scala language to support development of concurrent, fault-tolerant and scalable applications.  Akka uses teh Actor Model of distributed processing.  In order to support fault tolerance, it adopts the "Let it crash" model in order to build applications that have greater self-healing characteristics.


* #### ARG (Azavea Raster Grid)
A [raster](#Raster_Data) file format developed to support distributed, high performance data processing in the GeoTrellis framework.


* #### ASCII GRID
A text-based file format for encoding [raster](#Raster_Data) data.  Originally developed by Esri, the file format is an open, non-proprietary format.   
See also:
   - [Wikipedia: Esri GRID](http://en.wikipedia.org/wiki/Esri_grid)
   - [GeoTools docs about ASCII GRID](http://docs.codehaus.org/display/GEOTOOLS/ArcInfo+ASCII+Grid+format#ASCIIGrid)


* #### Aspect
The direction in which land surface faces. The data is usually represented as an integer value expressed as the number of degrees offset from north.


* #### Cartographic Modeling
see [Map Algebra](#Map_Algebra)


* #### Cell
The smallest square in a grid.  A cell is the fundamental unit of a [raster](#Raster_Data) data set and is sometimes used interchangably with the term [pixel](#Pixel).  Usually, it represents a rectangular area organized into an array of data values.


* #### Cell Size
The linear size in map units of the smallest area (the [cell](#Cell) or [pixel](#Pixel) ) in a [raster](#Raster_Data) data set.  For example, most land cover data derived from the Landsat satellite is usually published with a 30 meter cell size.


* #### Convolution
A type of [Focal](#Focal_Operations) operation in which a numerical weight is applied to each cell in the neighborhood (or "kernel").  [Kernel Density](#Kernel_Density_Estimation) (KDE) is an example of a convolution, but they can be used for many purposes.  In Map Algebra terms, a convolution is a FocalDistribution operation.   
See also:
   - [GeoTrellis Docs - Convolve Operation](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Convolve)


* #### Coordinate System
A fixed reference frame superimposed on the surface of the earth (or other planet) in order to designation the location of a point.  The [EPSG Geodetic Parameter Registry](http://www.epsg-registry.org/) is a list of standard coordinate systems and their geodetic parameters used for representing the Earth's surface.  It is maintained by the Geomatics Committee of the International Association of Oil and Gas Producers (OGP).


* #### Cost Distance
A class of [Focal operations](#Focal_Operations) in which distance from each cell to the nearest "source" or "target" is computed.  Rather than the linear or "Euclidean" distance, the distance is computed by accumulating a "cost" (sometimes referred to as "friction") to travel from one cell to another.  The cost is usually represented by a second [raster](#Raster_Data) data set in which the cost is a numerical value associated with each cell.  In addition to a cost factor, some GIS systems support the addition of vertical and horizontal restrictions on movement in order to better model dispersion and flow in certain kinds of systems.  For example, more gas is required to drive a car uphill than downhill or to drive against he wind, so there is not only a friction component but the direction of travel affects the cost.   
See also: 
   - [Euclidean Distance](#Euclidean_Distance)
   - [ArcGIS Resource Center - Understanding Cost Distance Analysis](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//009z000000z5000000.htm)
   - [ArcGIS Resource Center - Understanding Path Distance Analysis](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_path_distance_analysis/009z00000022000000/)


* #### DEM (Digital Elevation Model)
A digital representation of elevation on a land surface.  A DEM is mostly commonly a raster data structure, though triangulated irregular networks (TIN) and contour lines can also be generated from a DEM.  The US Geological Survey has also defined an open elevation file format commonly referred to as [USGS DEM](http://en.wikipedia.org/wiki/USGS_DEM).


* #### Euclidean Distance
A class of [Focal operations](#Focal_Operations) in which linear (straight-line or "Euclidean") distance from each cell to the nearest "source" or "target" is computed.  Usually, this is done from cell center to cell center.  In addition to distance, separate operations are usually provided for determining Direction to the source and allocating a unique identifier for the nearest source.
See also: 
   - [Cost Distance](#Cost_Distance)
   - [ArcGIS Resource Center - Understanding Euclidean Distance Analysis](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_Euclidean_distance_analysis/009z0000001t000000/)


* #### Focal Operations
A class of [Map Algebra](#Map_Algebra) operations in which a data set is transformed based on the cells around each cell.  The cells that define "neighborhood" can take many forms, including rectangular, circular, donuts or wedges and more complex operations can be defined by using neighborhoods in which cell has an additional weight defined.   Focal operations are sometimes organized into those in which only the immediate neighborhood is considered and those that include an extended neighborhood.  [Cost Distance](#Cost_Distance) and [Euclidean Distance](#Euclidean_Distance) operations are usually considered part of the exended neighborhood group.


* #### GeoTIFF
An extension of the Tag Image File Format (TIFF) [raster](#Raster_Data) file format developed to include additional metadata required for storing geospatial data.  The TIFF file was original developed by Aldus Corporation.


* #### Geoprocessing
The process of transforming one or more geospatial data structures into others.  Often, this involves the application of one or more processing directives (operations) performed on data using GIS software.  A geoprocessing operation typically (1) ingests a spatial data set, (2) transforms the data or uses the data to compute a new value, and (3) outputs a new spatial dataset. Geoprocessing operations can be automated and shared through the creation of tools in scripting languages, and can be combined and sequenced to create geoprocessing models.


* #### GDAL (Geospatial Data Abstraction Library)
[GDAL](http://www.gdal.org/) is an open source software project that provides raster data format translation capabilities.  The GDAL project has both command line utilities and services as a key raster I/O library for many commercial and open source projects.


* #### GRID (Esri GRID)
A proprietary raster data storge format developed by Esri. Like most raster data storage formats, GRIDs represent continuous, field-based attributes (such as elevation, temperature or land cover) by organizing geographic space into an array of square cells. A GRID is stored in a separate directory with associated tables and files containing information about that GRID's geography, attributes and processing history.  The Esri GRID data structure is very common, but GeoTrellis cannot use it directly and we recommend using GDAL, ArcGIS or other software to convert to GeoTIFF.  You can also use a recent build of GDAL to convert directly to the ARG file format used internally by GeoTrellis   
See also 
   - [Wikipedia: Esri GRID](http://en.wikipedia.org/wiki/Esri_grid)
   - [Esri Knowledge Base - What is the file structure of an Esri GRID?](http://support.esri.com/en/knowledgebase/techarticles/detail/30616)


* #### Hillshade
A raster data set in which each pixel has a gray-scale value representing "shadows" in order to simulate the effect of the sun's light on a land surface.  A hillshade effect can be achieved by assigning an integer value based on an azimuth and altitude parameter for the sun.  In Map Algebra terms, Hillshade is a FOCAL operation because it uses the elevation, aspect and slope values around each cell in order to compute the illumination value.


* #### Image Classification
The process whereby features are identified from images captured by satellite or aerial photography by grouping pixels with similar characteristics.


* #### Interpolation
A set of techniques for estimating missing values in a continuous surface based on a smaller number of known values.  


* #### JTS (Java Topology Suite)
An open source Java library for manipulating [vector](#Vector_Data) geospatial data through a set of planar geometry functions.  The JTS library is a foundation library for many open source and commercial software pacs.  It is licensed under the [LGPL](http://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License) license.  JTS has been ported to C++ as the [GEOS library](http://trac.osgeo.org/geos/) and to .Net as the [Net Topology Suite](http://code.google.com/p/nettopologysuite/).  GeoTrellis uses JTS to provide some of its [vector](#vector) spatial operations.


* #### Kernel
Another name for a neighborhood used in a [Focal operation](#Focal_Operations).

* #### Kernel Density Estimation
A measurement of density per unit area from one or more point or polyline features using a kernel function to fit a smoothly tapered surface to each point or polyline.  The result is sometimes known as a "heat map" that shows concentrations of the features.   
See also:
   - [Wikipedia: Kernel Density Estimation](http://en.wikipedia.org/wiki/Kernel_density_estimation)
   - [ArcGIS Resource Center - Understanding Density Analysis](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/Understanding_density_analysis/009z0000000w000000/)
   - [ArcGIS Resource Center - How Kernel Density Works](http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#/How_Kernel_Density_works/009z00000011000000/)
   - [GeoTrellis Docs - KernelDensity operation](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.KernelDensity)
   - [Applying Map Algebra – Part 1](http://www.azavea.com/blogs/atlas/2013/01/applying-map-algebra-part-1/)


* #### Kriging
An [interpolation](#Interpolation) technique in which measurement of spatial variation between the known points is used to estimate the unknown values being interpolated.


* #### Local Operations
A class of [Map Algebra](#Map_Algebra) operations in which two or more data sets are combined on a cell-by-cell basis, applying a mathematical function to generate a new map layer.


* #### Map Algebra
A formal system describing various functions and processes that can be used to manipulate geospatial data.  Originally developed by C. Dana Tomlin, Map Algebra is both a computation language and a general system for combining and transforming geospatial data by decomposing data and data processing into basic building blocks that can be recomposed with great flexibility.  Map Algebra operations are usually organized into [Local](#Local_Operations), [Focal](#Focal_Operations) and [Zonal](#Zonal_Operations) operations.  While not explicitly limited to [raster](#Raster_Data) data, it is most commonly associated with manipulation of [raster](#Raster_Data) data sets.  Map Algebra was first published as Tomlin's PhD thesis and then as [Geographic Information Systems and Cartographic Modeling](http://www.amazon.com/Geographic-Information-Systems-Cartographic-Modeling/dp/0133509273), a Prentice-Hall book published in 1990.  A revised version of the book, [GIS and Cartographic Modeling](http://www.amazon.com/GIS-Cartographic-Modeling-Dana-Tomlin/dp/158948309X/) was released by Esri Press in 2012.  


* #### Manhattan Distance
The distance between two points as measured by the number of grid cells in each direction


* #### Multi-Band Raster
A single raster data file that incorporates multiple raster data sets by including, for example, visible and infrared wavelengths as two different bands.


* #### Multi-Spectral Data
Satellite or aerial photography collected in two or more wavebands.


* #### Neighborhood Operations
See [Focal Operations](#Focal_Operations)


* #### Operations
Operations are transformations of data that result in new data.


* #### Pixel
Short for "pixel element", colloquially, a pixel refers to the smallest element of a display device.  In remote sensing, it also refers to the fundamental unit of data in a [raster](#Raster_Data) data set and is used interchangably with the term [cell](#Cell).  Usually, it is a rectangular cell organized into an array of data values.


* #### Projection or Map Projection
A mechanism by which the curved surface of the Earth (or other planet) is represented on a flat surface.  The map projection is key parameter of the [coordinate systems](#Coordinate_Systems) used to encode geospatial data sets.


* #### Raster Data
A geospatial data structure that organizes numeric values into a rectangular array of equal-sized cells (or pixels). Unlike a [vector](#vector) data sets, which stores coordinates explicitly, raster coordinates are implicity in the ordering of the matrix. Groups of cells that share the same value represent the same type of geographic feature.


* #### Scala
[Scala](http://www.scala-lang.org/) is a general purpose programming language designed to express common programming patterns in a concise, elegant, and type-safe way. Scala integrates features of object-oriented and functional languages.  Scala compiles to byte code that execute using the Java Runtime Environment.   
See also:  
   -  [Scala Language Reference](http://www.scala-lang.org/)


* #### Vector Data
A geospatial data structure in which the location of features or objects is represented by one or more coordinate pairs, usually based on a Cartesian coordinate system.  Two-dimensional vector data usualy consist of points, lines or polygons.  Each point feature is represented as a single coordinate pair, while line and polygon features are represented as ordered lists of vertices. Multiple attributes can be associated with each vector feature.


* #### Zonal Operations
A class of [Map Algebra](#Map_Algebra) operations in which a data set is summarized based on the values of all cells sharing a common value (a single zone).
