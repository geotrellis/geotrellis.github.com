---
layout: operations
title: Focal Operations

tutorial: operations
num: 4
sub: true
---

#### Focal operations
Raster operations that work on raster cells and their neighbors. Located in [geotrellis.raster.op.focal.](http://azavea.github.com/geotrellis/latest/api/#geotrellis.raster.op.focal.package)

#### Neighborhoods
Neighborhoods define a region around a cell location in which the values (and possibly positions) will be used as input to a focal operation's calculation at that location.


<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code>focal.Rescale</code></td><td>Rescale values between new min and max value.</td></tr>
<tr><td><code>focal.Hillshade</code></td><td>Create a three dimensional appearance from an elevation raster.</td></tr>
<tr><td><code>focal.KernelDensity</code></td><td>Compute the kernel density of a set of points onto a raster.</td></tr>
<tr><td><code>focal.MoransI</code></td><td>Compute the Morans I of the input raster.</td></tr>
<tr><td><code>focal.LocalMoransI</code></td><td>Set all cells to Local Morans I.</td></tr>
<tr><td><code><i>focal.Aspect</i></code></td><td>Calculate downslope direction from each cell to its neighbors.</td></tr>
<tr><td><code><i>focal.CostDistance</i></code></td><td>Calculate cost distance raster.</td></tr>
<tr><td><code><i>focal.FlowDirection</i></code></td><td>Calculate flow direction from input raster.</td></tr>
<tr><td><code>focal.Hillshade</code></td><td>Create a three dimensional appearance from an elevation raster.</td></tr>
<tr><td><code>focal.KernelDensity</code></td><td>Compute the kernel density of a set of points onto a raster.</td></tr>
<tr><td><code><i>focal.Max</i></code></td><td>Set pixels to maximum value in neighborhood.</td></tr>
<tr><td><code><i>focal.Mean</i></code></td><td>Set pixels to mean of specified neighborhood.</td></tr>
<tr><td><code><i>focal.Min</i></code></td><td>Set pixels to minimum value in neighborhood.</td></tr>
<tr><td><code>focal.Rescale</code></td><td>Rescale values between new min and max value.</td></tr>
<tr><td><code><i>focal.Slope</i></code></td><td>Calculate maximum rate of change cell to its neighbors.</td></tr>
<tr><td><code><i>focal.StandardDeviation</i></code></td><td>Set each cell to standard deviation within the specified neighborhood.</td></tr>
<tr><td><code><i>focal.Viewshed</i></code></td><td>Calculate viewshed from input points.</td></tr>
</tbody>
</table>

