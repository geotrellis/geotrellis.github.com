---
layout: operations
title: Local Operations

tutorial: operations
num: 3
sub: true
---

#### Local Operations

Local operations process each raster cell individually, without considering
other cells' nnvalues. When combining multiple rasters, a local operation will
map the value for each input's `(x, y)` cell to a single value in the output
raster's `(x, y)` cell. These properties allow GeoTrellis to parallelize local
operations very effectively.

Located in [geotrellis.raster.op.local.](http://azavea.github.com/geotrellis/latest/api/#geotrellis.raster.op.local.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
<tr><td><code>local.Add</code></td><td>Add the values of each cell in each raster.</td></tr>
<tr><td><code>local.And</code></td><td>Apply bitwise-and to each cell.</td></tr>
<tr><td><code>local.Ceil</code></td><td>Round each cell's value up to the nearest integer.</td></tr>
<tr><td><code>local.Defined</code></td><td>Set cell to 1 if defined, 0 if NoData.</td></tr>
<tr><td><code>local.Divide</code></td><td>Divide the values of each cell in each raster.</td></tr>
<tr><td><code>local.DoCell</code></td><td>Apply a custom function to each cell.</td></tr>
<tr><td><code>local.Equal</code></td><td>Set cell to 1 if equal to other cell, 0 if not.</td></tr>
<tr><td><code>local.Floor</code></td><td>Round each cell's value down to the nearest integer.</td></tr>
<tr><td><code>local.Greater</code></td><td>Set cell to 1 if cell is greater to other cell, 0 if not.</td></tr>
<tr><td><code>local.GreaterOrEqual</code></td><td>Set cell to 1 if cell is greater than or equal to other cell, 0 if not.</td></tr>
<tr><td><code>local.IfCell</code></td><td>Given a condition, set cell to value if true.</td></tr>
<tr><td><code>local.IfElseCell</code></td><td>Given a condition, set cell to true or false value.</td></tr>
<tr><td><code>local.Less</code></td><td>Set cell to 1 if cell is less to other cell, 0 if not.</td></tr>
<tr><td><code>local.LessOrEqual</code></td><td>Set cell to 1 if cell is less than or equal to other cell, 0 if not.</td></tr>
<tr><td><code>local.Log</code></td><td>Take the logarithm (base e) of each cell.</td></tr>
<tr><td><code>local.Mask</code></td><td>Set cells in raster to NoData based on values in other raster.</td></tr>
<tr><td><code>local.Max</code></td><td>Set cells to the maximum value.</td></tr>
<tr><td><code>local.Min</code></td><td>Set cells to the minimum value.</td></tr>
<tr><td><code>local.Multiply</code></td><td>Multiply the values of each cell in each raster.</td></tr>
<tr><td><code>local.Negate</code></td><td>Multiply cell values by -1.</td></tr>
<tr><td><code>local.Not</code></td><td>Apply bitwise-not to each cell.</td></tr>
<tr><td><code>local.Or</code></td><td>Apply bitwise-or to each cell.</td></tr>
<tr><td><code>local.Pow</code></td><td>Raise each cell to the specified power.</td></tr>
<tr><td><code>local.Round</code></td><td>Round each cell's value to the nearest integer.</td></tr>
<tr><td><code>local.Sqrt</code></td><td>Take the square root of each cell.</td></tr>
<tr><td><code>local.Subtract</code></td><td>Subtract the values of each cell in each raster.</td></tr>
<tr><td><code>local.Undefined</code></td><td>Set cell to 0 if defined, 1 if NoData.</td></tr>
<tr><td><code>local.Unequal</code></td><td>Set cell to 1 if not equal to other cell, 0 if not.</td></tr>
<tr><td><code>local.Xor</code></td><td>Apply bitwise-xor to each cell.</td></tr>
</tbody>
</table>
