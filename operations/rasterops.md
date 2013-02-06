---
layout: operations
title: Raster

tutorial: operations
num: 2
---

#### Raster operations

Manipulation and processing of raster data is a large part of the GeoTrellis library. The approach taken to the organization of raster operations is in line with C. Dana Tomlin's Map Algebra, as detailed in the book [GIS and Cartographic Modeling](http://www.amazon.com/GIS-Cartographic-Modeling-Dana-Tomlin/dp/158948309X). Map Algebra breaks focal operations into three main categories:

- [**Local Operations**](operations/raster/local.html): Local operations calculate resulting raster cell values based on the value at the same cell location in one or more input rasters.
- [**Focal Operations**](operations/raster/focal.html): Focal operations calculate resulting raster cell values based on the values in a defined in a neighborhood around the same cell location in one or more input rasters.
- [**Zonal Operations**](operations/raster/zonal.html): Zonal operations calcuate resulting raster cell values based on the values associated with that cell's zone in one or more input rasters.

Along with raster operations that perform Map Algebra-based processing, there are operations which deal with the [**Tiling**](operations/raster/tiling.html) of rasters, as well as others, a partial listing of which is below:

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code>CreateRaster</code></td><td>Creates an empty raster object with a given raster extent.</td></tr>
<tr><td><code>VerticalFlip</code></td><td>Flips the data for a raster along the X-axis.</td></tr>
<tr><td><code>transform.Crop</code></td><td>Creates a new raster from a sub-extent of an existing raster.</td></tr>
<tr><td><code>transform.ResampleRaster</code></td><td>Uses a nearest-neighbor algorithm to resample a raster.</td></tr>
</tbody>
</table>

