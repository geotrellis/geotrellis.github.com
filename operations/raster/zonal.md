---
layout: operations
title: Zonal Operations

tutorial: operations
num: 5
sub: true
---

#### Zonal operations
Raster operations that work on areas of cells that share the same value in an input raster. Located in [geotrellis.raster.op.zonal.](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.ZonalHistogram" target="_blank">zonal.ZonalHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a raster, return a histogram summary of the cells within each zone.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>ZonalHistorgram does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.Histogram" target="_blank">zonal.summary.Histogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates a histogram all raster cells within a geometry.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.Max" target="_blank">zonal.summary.Max</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.This operation is for integer typed Rasters. If you want the Max for double type rasters (TypeFloat,TypeDouble) use MaxDouble</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.MaxDouble" target="_blank">zonal.summary.MaxDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.Min" target="_blank">zonal.summary.Min</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the min of all raster cells within a geometry. This operation is for integer typed Rasters. If you want the Min for double type rasters (TypeFloat,TypeDouble) use MinDouble</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.MinDouble" target="_blank">zonal.summary.MinDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the min of all raster cells within a geometry.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.Sum" target="_blank">zonal.summary.Sum</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the sum of all raster cells within a geometry. This operation is for integer typed Rasters. If you want the Sum for double type rasters (TypeFloat,TypeDouble) use SumDouble</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.zonal.summary.SumDouble" target="_blank">zonal.summary.SumDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a zonal summary that calculates the sum of all raster cells within a geometry.</p></div></div></td></tr>
    
</tbody>
</table>
