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

<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op1" targe="_blank">geotrellis.Op1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.DispatchedOperation" targe="_blank">geotrellis.DispatchedOperation</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.CompositeOperation" targe="_blank">geotrellis.CompositeOperation</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given an operation and a function that takes the result of that operation and returns
a new operation, return an operation of the return type of the function.</p><p>If the initial operation is g, you can think of this operation as f(g(x))
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.OperationWrapper" targe="_blank">geotrellis.OperationWrapper</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Literal" targe="_blank">geotrellis.Literal</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return the literal value specified.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op4" targe="_blank">geotrellis.Op4</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op5" targe="_blank">geotrellis.Op5</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op6" targe="_blank">geotrellis.Op6</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op0" targe="_blank">geotrellis.Op0</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Below are the Op0 - Op6 abstract classes.</p><p>These are useful for easily defining operations which just want to evaluate
their child operations and then run a single function afterwards.</p><p>For example:</p><p>case class Add2(x:Op[Int], y:Op[Int]) extends Op2(x, y)(_ + _)
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op2" targe="_blank">geotrellis.Op2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op3" targe="_blank">geotrellis.Op3</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.FlattenGeometry" targe="_blank">feature.op.FlattenGeometry</a></code></td><td>None</td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.FilterGeometry" targe="_blank">feature.op.FilterGeometry</a></code></td><td>None</td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.AsPolygonSet" targe="_blank">feature.op.AsPolygonSet</a></code></td><td>None</td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Disjoint" targe="_blank">feature.op.geometry.Disjoint</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if two geometries are disjoint.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Simplify" targe="_blank">feature.op.geometry.Simplify</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Simplify a polygon or multipolygon.</p><p>This operation uses a topology preserving simplifier that ensures the result has the same
characteristics as the input.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/simplify/TopologyPreservingSimplifier.html" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.ConvexHull" targe="_blank">feature.op.geometry.ConvexHull</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the convex hull of this geometry, which is the smallest polygon that contains it.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#convexHull()" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Union" targe="_blank">feature.op.geometry.Union</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the union of these geometries.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#union(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetCentroid" targe="_blank">feature.op.geometry.GetCentroid</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetDistance" targe="_blank">feature.op.geometry.GetDistance</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the minimum distance between these two geometries.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#distance(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Covers" targe="_blank">feature.op.geometry.Covers</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry covers another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#covers(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetEnvelope" targe="_blank">feature.op.geometry.GetEnvelope</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Equals" targe="_blank">feature.op.geometry.Equals</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry equals another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#contains(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.BufferWithParameters" targe="_blank">feature.op.geometry.BufferWithParameters</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetArea" targe="_blank">feature.op.geometry.GetArea</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the area of a geometry.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#getArea()" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Erase" targe="_blank">feature.op.geometry.Erase</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry that contains the points in the first geometry that
aren't in the second geometry.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#difference(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Intersects" targe="_blank">feature.op.geometry.Intersects</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry intersects another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersects(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetSymDifference" targe="_blank">feature.op.geometry.GetSymDifference</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry defined by the points that are in one of the two geometries
but not the other.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Buffer" targe="_blank">feature.op.geometry.Buffer</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes a buffer area around this geometry.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#buffer(double," target="_blank">int, int) "JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Intersect" targe="_blank">feature.op.geometry.Intersect</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the intersection of these geometries.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Overlaps" targe="_blank">feature.op.geometry.Overlaps</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry overlaps another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersects(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Contains" targe="_blank">feature.op.geometry.Contains</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry contains another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#contains(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadFile" targe="_blank">io.LoadFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadFileWithRasterExtent" targe="_blank">io.LoadFileWithRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.CsvIntMap" targe="_blank">io.CsvIntMap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a Map of (String,String) =&gt; Int from a CSV file
of the format: String,String,Int
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterExtentFromFile" targe="_blank">io.LoadRasterExtentFromFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the <a href="../RasterExtent.html" class="extype" name="geotrellis.RasterExtent">RasterExtent</a> from the raster in the specified file.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRaster" targe="_blank">io.LoadRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterMetadataFromFile" targe="_blank">io.LoadRasterMetadataFromFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the <a href="../process/RasterLayer.html" class="extype" name="geotrellis.process.RasterLayer">geotrellis.process.RasterLayer</a>, a representation of the raster metadata,
from the raster in the specified file.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.SimpleRenderPng" targe="_blank">io.SimpleRenderPng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a data raster.</p><p>This operation is designed to provide a simple interface to generate a
colored image from a data raster.  The data values in your raster will
be classified into a number of ranges, and cells in each range will be
rendered with a unique color.  You can select the number of ranges that
will be used, and the color ramp from which the colors will be selected.</p><p>There are some color ramps you can select in geotrellis.data, and the
default ramp (if you do not provide one) ranges from red to yellow to green.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.WritePng" targe="_blank">io.WritePng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG graphic file to the file system at the specified path.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterExtent" targe="_blank">io.LoadRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadWkt" targe="_blank">io.LoadWkt</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Reads feature data from a string of Well Known Text data.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadGeoJsonFeature" targe="_blank">io.LoadGeoJsonFeature</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load a feature from GeoJson.</p><p>This operation loads a feature from GeoJson.  It accepts both simple
geometry definitions and feature definitions.  If there is a property
JSON clause, the feature data will be Some(JsonNode).
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.WritePngRgba" targe="_blank">io.WritePngRgba</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG file of a raster that contains RGBA values)
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderPng" targe="_blank">io.RenderPng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a raster.</p><p>Use this operation when you have a raster of data that you want to visualize
with an image.</p><p>To render a data raster into an image, the operation needs to know which
values should be painted with which colors.  To that end, you'll need to
generate a ColorBreaks object which represents the value ranges and the
assigned color.  One way to create these color breaks is to use the
<a href="../statistics/op/stat/GetClassBreaks.html" class="extype" name="geotrellis.statistics.op.stat.GetClassBreaks">geotrellis.statistics.op.stat.GetClassBreaks</a> operation to generate
quantile class breaks.</p><p>Example usage:</p><pre><span class="kw">import</span> geotrellis.statistics.op._
<span class="kw">val</span> rOp = io.LoadRaster(<span class="lit">"foo"</span>) <span class="cmt">// get a data raster</span>
<span class="kw">val</span> histogramOp = stat.GetHistogram(r)
<span class="kw">val</span> colors = <span class="std">Array</span>(<span class="num">0</span>xFF0000FF, <span class="num">0</span>x00FF00FF) <span class="cmt">// red and green in RGBA values</span>
<span class="cmt">// generate a 6 color gradient between red and green</span>
<span class="kw">val</span> colorsOp = stat.GetColorsFromPalette(colors, <span class="num">6</span>)
<span class="kw">val</span> breaksOp = stat.GetColorBreaks(histogramOp, numColorsOp)
<span class="kw">val</span> pngOp = io.RenderPng(rOp, braeksOp, histogramOp, <span class="num">0</span>)</pre></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderPngRgba" targe="_blank">io.RenderPngRgba</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG from a raster of RGBA integer values.</p><p>Use this operation when you have created a raster whose values are already
RGBA color values that you wish to render into a PNG.  If you have a raster
with data that you wish to render, you should use RenderPng instead.</p><p>An RGBA value is a 32 bit integer with 8 bits used for each component:
the first 8 bits are the red value (between 0 and 255), then green, blue,
and alpha (with 0 being transparent and 255 being opaque).
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadTileSet" targe="_blank">io.LoadTileSet</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the a set of tiles the specified directory.</p><p>This directory must contain a layout.json file as well as tiles written
in the ARG format.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderGeoTiff" targe="_blank">io.RenderGeoTiff</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Render a raster as a GeoTiff.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Collect" targe="_blank">logic.Collect</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach2" targe="_blank">logic.ForEach2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operations (opA and opB) to get an array of A's and an
array of B's. Then, applies the given function (f) to each (A, B) item in
the arrays (pairwise by array index) to get a Z value. The resulting array
of Z's is returned.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach3" targe="_blank">logic.ForEach3</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operations (opA opB, and opC) to get arrays of A's, B's
and C's (which should be the same length).</p><p>Then, applies the given function (f) to each (A, B, C) triple in (grouped by
array index) to get a Z value. The resulting array of Z's is returned.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach1" targe="_blank">logic.ForEach1</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operation (op) to get an array of A's. Then, applies
the given function (f) to each item in the array in. The resulting array of
Z's is returned.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.CollectArray" targe="_blank">logic.CollectArray</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.WithResult" targe="_blank">logic.WithResult</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Run a function on the result of an operation</p><p>Functionally speaking, this represents the bind operation
on the Operation monad
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.AsList" targe="_blank">logic.AsList</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return the result of the input operation as a List.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Do2" targe="_blank">logic.Do2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Invoke a function that takes two arguments.</p><p>Functionally speaking: Map an Op[A] and Op[B] into an Op[Z] using a
function from (A,B) =&gt; Z.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Do1" targe="_blank">logic.Do1</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Invoke a function that takes one argument.</p><p>Functionally speaking: Map an Op[A] into an Op[Z]
using a function from A =&gt; Z.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Reducer1" targe="_blank">logic.Reducer1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Reducer2" targe="_blank">logic.Reducer2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.If" targe="_blank">logic.If</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Pure" targe="_blank">logic.applicative.Pure</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "pure" on Functor.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Apply" targe="_blank">logic.applicative.Apply</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "apply" (&lt;*&gt;) on Functor.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Fmap" targe="_blank">logic.applicative.Fmap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "fmap" on Functor.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.Force" targe="_blank">raster.op.Force</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Forces evaluation of the resulting raster of the passed in operation.
This is useful when you want to force lazy operations to happen
at specific points in the operation chain.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.CreateRaster" targe="_blank">raster.op.CreateRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates an empty raster object based on the given raster properties.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.ZonalHistogram" targe="_blank">raster.op.ZonalHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a raster, return a histogram summary of the cells within each zone.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>ZonalHistorgram does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.VerticalFlip" targe="_blank">raster.op.VerticalFlip</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Flip the data for a raster along the X-axis.</p><p>The geographic extent will remain unchanged.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>VerticalFlip does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.data.AsArrayDouble" targe="_blank">raster.op.data.AsArrayDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Converts a raster to a double array.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.data.AsArray" targe="_blank">raster.op.data.AsArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Converts a raster to an integer array.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetExtent" targe="_blank">raster.op.extent.GetExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates an extent out of boundary values.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CombineExtents" targe="_blank">raster.op.extent.CombineExtents</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return a the smallest extent that contains this extent and the provided
extent. This is provides a union of the two extents.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CropRasterExtentByExtent" targe="_blank">raster.op.extent.CropRasterExtentByExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CropRasterExtent" targe="_blank">raster.op.extent.CropRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetRasterExtentFromRaster" targe="_blank">raster.op.extent.GetRasterExtentFromRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Get the <a href="../../../RasterExtent.html" class="extype" name="geotrellis.RasterExtent">RasterExtent</a> from a given raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetRasterExtent" targe="_blank">raster.op.extent.GetRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.ChunkRasterExtent" targe="_blank">raster.op.extent.ChunkRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Used to chunk a RasterExtent object (geographical extent + grid information)
into many smaller contiguous pieces. The number of columns desired is
provided by <code>nx</code> and the number of rows by <code>ny</code>.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CostDistance" targe="_blank">raster.op.focal.CostDistance</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a Cost-Distance raster based on a set of starting points and a cost
raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Operation will only work with integer typed Cost Rasters (TypeBit,TypeByte,TypeShort,TypeInt).
         If a double typed Cost Raster (TypeFloat,TypeDouble) is passed in, those costs will be rounded
         to their floor integer values.</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.IndirectHillshade" targe="_blank">raster.op.focal.IndirectHillshade</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Indirect calculation of hill shading of a raster that uses Aspect and Slope operation results.</p><p>Construct through the <a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a> object.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Does not currently work with TiledFocalOps of Aspect and Slope.
                    Use the direct method with TileFocalOps and tiled raster data.</p></span></dd><dt>See also</dt><dd><span class="cmt"><p><a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Aspect" targe="_blank">raster.op.focal.Aspect</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates the aspect of each cell in a raster.</p><p>Aspect is the direction component of a gradient vector. It is the
direction in degrees of which direction the maximum change in direction is pointing.
It is defined as the directional component of the gradient vector and is the
direction of maximum gradient of the surface at a given point. It uses Horn's method
for computing aspect.</p><p>As with slope, aspect is calculated from estimates of the partial derivatives dz/dx and dz/dy.</p><p>Aspect is computed in degrees from due north, i.e. as an azimuth in degrees not radians.
The expression for aspect is:</p><pre><span class="kw">val</span> aspect = <span class="num">270</span> - <span class="num">360</span>/(<span class="num">2</span>*Pi) * atan2(`dz/dy`, - `dz/dx`)</pre></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Paraphrased from
<a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a>
(Smit, Longley, and Goodchild)
</p></span></dd><dt>See also</dt><dd><span class="cmt"><p><a href="SurfacePoint.html" class="extype" name="geotrellis.raster.op.focal.SurfacePoint">SurfacePoint</a> for aspect calculation logic.</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.AutomaticNormalize" targe="_blank">raster.op.focal.AutomaticNormalize</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Normalize the values in the given raster so that all values are within the
specified minimum and maximum value range.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>AutomaticNormalize does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Max" targe="_blank">raster.op.focal.Max</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the maximum value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Maximum does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation" targe="_blank">raster.op.focal.FocalOperation</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster and a neighborhood.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Median" targe="_blank">raster.op.focal.Median</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the median value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Median does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.DirectHillshade" targe="_blank">raster.op.focal.DirectHillshade</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Direct calculation of hill shading of a raster. Construct through the <a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a> object.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a>
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Mode" targe="_blank">raster.op.focal.Mode</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the mode of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Mode does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Mean" targe="_blank">raster.op.focal.Mean</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the mean value of a neighborhood for a given raster. Returns a raster of TypeDouble
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Mean does not currently support Double raster data inputs.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span>, <span class="cmt"><p>If the neighborhood is a <a href="Square.html" class="extype" name="geotrellis.raster.op.focal.Square">Square</a> neighborhood, the mean calucation will use
                 the <a href="CellwiseMeanCalc.html" class="extype" name="geotrellis.raster.op.focal.CellwiseMeanCalc">CellwiseMeanCalc</a> to perform the calculation, because it is faster.
                 If the neighborhood is of any other type, then <a href="CursorMeanCalc.html" class="extype" name="geotrellis.raster.op.focal.CursorMeanCalc">CursorMeanCalc</a> is used.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CreateCircleRaster" targe="_blank">raster.op.focal.CreateCircleRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a Circle raster. Can be used with the <a href="Convolve.html" class="extype" name="geotrellis.raster.op.focal.Convolve">Convolve</a> or <a href="KernelDensity.html" class="extype" name="geotrellis.raster.op.focal.KernelDensity">KernelDensity</a> operations.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation4" targe="_blank">raster.op.focal.FocalOperation4</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and four other argument.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation1" targe="_blank">raster.op.focal.FocalOperation1</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and one other argument.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation3" targe="_blank">raster.op.focal.FocalOperation3</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and three other argument.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation2" targe="_blank">raster.op.focal.FocalOperation2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and two other argument.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.ScalarMoransI" targe="_blank">raster.op.focal.ScalarMoransI</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates global spatial autocorrelation of a raster based on the similarity to
neighboring values.</p><p>The resulting statistic is such that the more positive the number, the greater
the similarity of values in the raster, and the more negative the number,
the more dissimilar the raster values are.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Since mean and standard deviation are based off of an
                       Int based Histogram, those values will come from rounded values
                       of a double typed Raster (TypeFloat,TypeDouble).
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp" targe="_blank">raster.op.focal.FocalOp</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster and a neighborhood.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Convolve" targe="_blank">raster.op.focal.Convolve</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the convolution of two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Convolve does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Slope" targe="_blank">raster.op.focal.Slope</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates the slope of each cell in a raster.</p><p>Slope is the magnitude portion of the gradient vector. It is the maximum
change of elevation from a raster cell to any immediate neighbor. It uses Horn's method
for computing slope.</p><p>As with aspect, slope is calculated from estimates of the partial derivatives dz/dx and dz/dy.</p><p>Slope is computed in degrees from horizontal.</p><p>The expression for slope is:</p><pre><span class="kw">val</span> slope = atan(sqrt(pow(`dz/dy`,<span class="num">2</span>) * pow(`dz/dx`,<span class="num">2</span>)))</pre></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a>
(Smit, Longley, and Goodchild)
</p></span><span class="cmt"><p><a href="SurfacePoint.html" class="extype" name="geotrellis.raster.op.focal.SurfacePoint">SurfacePoint</a> for slope calculation logic.</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp4" targe="_blank">raster.op.focal.FocalOp4</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and four other arguments.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp2" targe="_blank">raster.op.focal.FocalOp2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and two other arguments.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp3" targe="_blank">raster.op.focal.FocalOp3</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and three other arguments.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp1" targe="_blank">raster.op.focal.FocalOp1</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and one other argument.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CreateGaussianRaster" targe="_blank">raster.op.focal.CreateGaussianRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a Gaussian raster. Can be used with the <a href="Convolve.html" class="extype" name="geotrellis.raster.op.focal.Convolve">Convolve</a> or <a href="KernelDensity.html" class="extype" name="geotrellis.raster.op.focal.KernelDensity">KernelDensity</a> operations.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Conway" targe="_blank">raster.op.focal.Conway</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the next step of Conway's Game of Life for a given <a href="../../../Raster.html" class="extype" name="geotrellis.Raster">Raster</a>.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p>A description of Conway's Game of Life can be found on
<a href="http://en.wikipedia.org/wiki/Conway's_Game_of_Life" target="_blank">wikipedia</a>.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.RasterMoransI" targe="_blank">raster.op.focal.RasterMoransI</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates spatial autocorrelation of cells based on the similarity to
neighboring values.</p><p>The statistic for each focus in the resulting raster is such that the more
positive the number, the greater the similarity between the focus value and
it's neighboring values, and the more negative the number, the more dissimilar
the focus value is with it's neighboring values.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Since mean and standard deviation are based off of an
                       Int based Histogram, those values will come from rounded values
                       of a double typed Raster (TypeFloat,TypeDouble).
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Min" targe="_blank">raster.op.focal.Min</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the minimum value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Min does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.TileFocalOp" targe="_blank">raster.op.focal.TileFocalOp</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.PrecomputedNormalize" targe="_blank">raster.op.focal.PrecomputedNormalize</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Normalize the values in the given raster.
zmin and zmax are the lowest and highest values in the provided raster.
gmin and gmax are the desired minimum and maximum values in the output raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>PrecomputedNormalize does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Sum" targe="_blank">raster.op.focal.Sum</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the sum of values of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Sum does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span>, <span class="cmt"><p>If the neighborhood is a <a href="Square.html" class="extype" name="geotrellis.raster.op.focal.Square">Square</a> neighborhood, the sum calucation will use
                 the <a href="CellwiseSumCalc.html" class="extype" name="geotrellis.raster.op.focal.CellwiseSumCalc">CellwiseSumCalc</a> to perform the calculation, because it is faster.
                 If the neighborhood is of any other type, then <a href="CursorSumCalc.html" class="extype" name="geotrellis.raster.op.focal.CursorSumCalc">CursorSumCalc</a> is used.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.KernelDensity" targe="_blank">raster.op.focal.KernelDensity</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the Kernel Density for a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>KernelDensity does not currently support Double raster data.
                             If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                             the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UndefinedConstant" targe="_blank">raster.op.local.UndefinedConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps an integer to 1 if NODATA, else 0.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.InverseMask" targe="_blank">raster.op.local.InverseMask</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a raster with the values from the first raster, but only include
cells in which the corresponding cell in the second raster is set to the
"readMask" value.</p><p>For example, if *all* cells in the second raster are set to the readMask value,
the output raster will be identical to the first raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinConstant" targe="_blank">raster.op.local.MinConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes a Raster and an Int, and gives a raster with each cell being
the min value of the original raster and the integer.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinConstant does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryLocal" targe="_blank">raster.op.local.BinaryLocal</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>BinaryLocal is an abstract class for all operations that are both local (operating
on each cell in a raster without knowledge of other cells) and binary, by which
we mean that the input includes two rasters (as opposed to 'unary' or 'multi').
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryDoCell" targe="_blank">raster.op.local.BinaryDoCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a function on every cell in a raster with the values from another raster.</p><p>For example,
</p><pre>
val A = LoadFile(a)
val B = LoadFile(b)
// Generate a raster by adding the values of each cell in A and B
val D = BinaryDoCell(R, (a, b) =&gt; a + b )
</pre>
</div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyDoubleConstant" targe="_blank">raster.op.local.MultiplyDoubleConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant (double).</p><p>Create with MultiplyConstant(raster, doubleValue).
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilInt" targe="_blank">raster.op.local.CeilInt</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractConstant" targe="_blank">raster.op.local.SubtractConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract a constant value from each cell.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryIfElseCell" targe="_blank">raster.op.local.BinaryIfElseCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a condition over two rasters, set the value of each cell in the output
to a specified true or false value after testing the specified condition on
the corresponding values in each of the two input rasters.
each of the two input rasters.</p><p>Usage:
</p><pre>
// Generate a raster with the value 1 in each cell in which the value of A
// is greater than B in the corresponding cell.  Set the value to 0 if the
// condition is false.
val C = BinaryIfElseCell(A,B, (a,b) =&gt; a &gt; b, 1, 0)
</pre>
</div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddConstant2" targe="_blank">raster.op.local.AddConstant2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add a constant value to each cell.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubleConstantBy" targe="_blank">raster.op.local.PowDoubleConstantBy</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideConstantBy" targe="_blank">raster.op.local.DivideConstantBy</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>For each cell, divide a constant value by that cell's value.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.Mask" targe="_blank">raster.op.local.Mask</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a raster with the values from the first raster, but only include
cells in which the corresponding cell in the second raster *are not* set to the
"readMask" value.</p><p>For example, if *all* cells in the second raster are set to the readMask value,
the output raster will be empty -- all values set to NODATA.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyConstant" targe="_blank">raster.op.local.MultiplyConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualConstant1" targe="_blank">raster.op.local.EqualConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualConstant1" targe="_blank">raster.op.local.LessOrEqualConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualConstant2" targe="_blank">raster.op.local.GreaterOrEqualConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualConstant1" targe="_blank">raster.op.local.GreaterOrEqualConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DefinedConstant" targe="_blank">raster.op.local.DefinedConstant</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryIfCell" targe="_blank">raster.op.local.BinaryIfCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a condition over two rasters, set the value of each cell in the output
to a specified value if the condition is true given the corresponding values in
each of the two input rasters.</p><p>Local operation.
Binary operation (input includes two rasters).
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractRaster" targe="_blank">raster.op.local.SubtractRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract each value in the second raster from the corresponding value in the first raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalConstant1" targe="_blank">raster.op.local.UnequalConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundRaster" targe="_blank">raster.op.local.RoundRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundInt" targe="_blank">raster.op.local.RoundInt</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.NotRaster" targe="_blank">raster.op.local.NotRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the bitwise negation of each cell value.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>NotRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DoCell" targe="_blank">raster.op.local.DoCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a function on every cell in a raster.</p><p>For example,
</p><pre>
val R = LoadFile(f)
val D = DoCell(R, x =&gt; x + 3 ) // add 3 to every cell in the raster
</pre>
</div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>DoCell does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtDouble" targe="_blank">raster.op.local.SqrtDouble</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtInt" targe="_blank">raster.op.local.SqrtInt</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrRaster" targe="_blank">raster.op.local.OrRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Or's the cell values of the two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndConstant1" targe="_blank">raster.op.local.AndConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilDouble" targe="_blank">raster.op.local.CeilDouble</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndConstant2" targe="_blank">raster.op.local.AndConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideDoubleConstantBy" targe="_blank">raster.op.local.DivideDoubleConstantBy</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorInt" targe="_blank">raster.op.local.FloorInt</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilRaster" targe="_blank">raster.op.local.CeilRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes the Ceiling of each raster cell value.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowConstant" targe="_blank">raster.op.local.PowConstant</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.NotConstant" targe="_blank">raster.op.local.NotConstant</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubles" targe="_blank">raster.op.local.PowDoubles</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyArray" targe="_blank">raster.op.local.MultiplyArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell of each raster in array.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrConstant2" targe="_blank">raster.op.local.OrConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrConstant1" targe="_blank">raster.op.local.OrConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowConstantBy" targe="_blank">raster.op.local.PowConstantBy</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogDouble" targe="_blank">raster.op.local.LogDouble</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorConstant1" targe="_blank">raster.op.local.XorConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxConstant" targe="_blank">raster.op.local.MaxConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of a rasters and a constant.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxConstant does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorConstant2" targe="_blank">raster.op.local.XorConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualConstant2" targe="_blank">raster.op.local.LessOrEqualConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualRaster" targe="_blank">raster.op.local.EqualRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogInt" targe="_blank">raster.op.local.LogInt</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideConstant" targe="_blank">raster.op.local.DivideConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Divide each cell by a constant value.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinConstant2" targe="_blank">raster.op.local.MinConstant2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes an Int and a Raster, and gives a raster with each cell being
the min value of the original raster and the integer.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinConstant2 does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiLocal" targe="_blank">raster.op.local.MultiLocal</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalConstant2" targe="_blank">raster.op.local.UnequalConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyConstant2" targe="_blank">raster.op.local.MultiplyConstant2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessConstant1" targe="_blank">raster.op.local.LessConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessConstant2" targe="_blank">raster.op.local.LessConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinRaster" targe="_blank">raster.op.local.MinRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes two Rasters and gives a raster with the min values of the two at each cell.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DefinedRaster" targe="_blank">raster.op.local.DefinedRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps an integer typed Raster to 1 if the cell value is not NODATA, otherwise 0.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorRaster" targe="_blank">raster.op.local.FloorRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubleConstant" targe="_blank">raster.op.local.PowDoubleConstant</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessRaster" targe="_blank">raster.op.local.LessRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorRaster" targe="_blank">raster.op.local.XorRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Xor's the cell values of two integer typed Rasters.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualRaster" targe="_blank">raster.op.local.LessOrEqualRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorDouble" targe="_blank">raster.op.local.FloorDouble</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UndefinedRaster" targe="_blank">raster.op.local.UndefinedRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps Raster cell values to 1 if they are NODATA, else 0.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddArray" targe="_blank">raster.op.local.AddArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add the values of each cell in each raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowInts" targe="_blank">raster.op.local.PowInts</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtRaster" targe="_blank">raster.op.local.SqrtRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterRaster" targe="_blank">raster.op.local.GreaterRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddConstant" targe="_blank">raster.op.local.AddConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add a constant value to each cell.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowRaster" targe="_blank">raster.op.local.PowRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes the cell value of the first raster and raises it to the power determined
by the cell value of the second raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogRaster" targe="_blank">raster.op.local.LogRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiLocalArray" targe="_blank">raster.op.local.MultiLocalArray</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.IfCell" targe="_blank">raster.op.local.IfCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps all cells matching <code>cond</code> to <code>trueValue</code>.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LocalOperation" targe="_blank">raster.op.local.LocalOperation</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Local operations involve each individual value in a raster without information
about other values in the raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundDouble" targe="_blank">raster.op.local.RoundDouble</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterConstant2" targe="_blank">raster.op.local.GreaterConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterConstant1" targe="_blank">raster.op.local.GreaterConstant1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideDoubleConstant" targe="_blank">raster.op.local.DivideDoubleConstant</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractConstantBy" targe="_blank">raster.op.local.SubtractConstantBy</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract the value of each cell by a constant.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.Negate" targe="_blank">raster.op.local.Negate</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Negate (multiply by -1) each value in a raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideRaster" targe="_blank">raster.op.local.DivideRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Divide each value of one raster with the values from another raster.
Local operation.
Binary operation.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndRaster" targe="_blank">raster.op.local.AndRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>And's the cell values of two rasters together.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualRaster" targe="_blank">raster.op.local.GreaterOrEqualRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualConstant2" targe="_blank">raster.op.local.EqualConstant2</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalRaster" targe="_blank">raster.op.local.UnequalRaster</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxRaster" targe="_blank">raster.op.local.MaxRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.IfElseCell" targe="_blank">raster.op.local.IfElseCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Set all values of output raster to one value or another based on whether a
condition is true or false.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxConstant2" targe="_blank">raster.op.local.MaxConstant2</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of a rasters and a constant.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxConstant2 does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileMin" targe="_blank">raster.op.tiles.TileMin</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Performs a local Min operation on a TiledRaster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileMin does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileHistogram" targe="_blank">raster.op.tiles.TileHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a histogram for a TiledRaster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileHistogram does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.ThroughputLimitedReducer1" targe="_blank">raster.op.tiles.ThroughputLimitedReducer1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileMax" targe="_blank">raster.op.tiles.TileMax</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Performs a local Max operation on a TiledRaster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileMax does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.Reducer1" targe="_blank">raster.op.tiles.Reducer1</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.transform.ResampleRaster" targe="_blank">raster.op.transform.ResampleRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This uses a nearest-neighbor algorithm to resample a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Resample does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.transform.Crop" targe="_blank">raster.op.transform.Crop</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a new raster from the data in a sub-extent of an existing raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Max" targe="_blank">raster.op.zonal.Max</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Max for double type rasters
(TypeFloat,TypeDouble) use <a href="MaxDouble.html" class="extype" name="geotrellis.raster.op.zonal.MaxDouble">MaxDouble</a>
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Histogram" targe="_blank">raster.op.zonal.Histogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates a histogram all raster cells within a geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.MinDouble" targe="_blank">raster.op.zonal.MinDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the min of all raster cells within a geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Sum" targe="_blank">raster.op.zonal.Sum</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the sum of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Sum for double type rasters
(TypeFloat,TypeDouble) use <a href="SumDouble.html" class="extype" name="geotrellis.raster.op.zonal.SumDouble">SumDouble</a>
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Min" targe="_blank">raster.op.zonal.Min</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the min of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Min for double type rasters
(TypeFloat,TypeDouble) use <a href="MinDouble.html" class="extype" name="geotrellis.raster.op.zonal.MinDouble">MinDouble</a>
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.MaxDouble" targe="_blank">raster.op.zonal.MaxDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.SumDouble" targe="_blank">raster.op.zonal.SumDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the sum of all raster cells within a geometry.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.TiledPolygonalZonalSummary" targe="_blank">raster.op.zonal.TiledPolygonalZonalSummary</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.SplitOnComma" targe="_blank">rest.op.string.SplitOnComma</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Split a string on a comma.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseColor" targe="_blank">rest.op.string.ParseColor</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as a color.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseInt" targe="_blank">rest.op.string.ParseInt</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as an integer.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseExtent" targe="_blank">rest.op.string.ParseExtent</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseDouble" targe="_blank">rest.op.string.ParseDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as a double.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.Split" targe="_blank">rest.op.string.Split</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Split a string on a comma.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.MapHistogram" targe="_blank">statistics.MapHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram that uses a Map (as in hashtable map/dictionary) for internal storage.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.CompressedArrayHistogram" targe="_blank">statistics.CompressedArrayHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram using an array for internal storage,
which requires an initial minimum and maximum val and a specified number of 'breaks' which
are used to group values together into ranges.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>CompressedArrayHistogram can currently only handle non-negative integers.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.FastMapHistogram" targe="_blank">statistics.FastMapHistogram</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.ArrayHistogram" targe="_blank">statistics.ArrayHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram that uses an array for internal storage.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetClassBreaks" targe="_blank">statistics.op.stat.GetClassBreaks</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate quantile class breaks for a given raster.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetHistogramArray" targe="_blank">statistics.op.stat.GetHistogramArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Implements a histogram in terms of an array of the given size.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Rasters with a double type (TypeFloat,TypeDouble) will have their values
          rounded to integers when making the Histogram.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetStandardDeviation" targe="_blank">statistics.op.stat.GetStandardDeviation</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetDoubleHistogram" targe="_blank">statistics.op.stat.GetDoubleHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a histogram from double values in a raster.</p><p>FastMapHistogram only works with integer values, which is great for performance
but means that, in order to use FastMapHistogram with double values, each value
must be multiplied by a power of ten to preserve significant fractional digits.</p><p>For example, if you want to save one significant digit (2.1 from 2.123), set
sigificantDigits to 1, and the histogram will save 2.1 as "21" by multiplying
each value by 10.  The multiplier is 10 raised to the power of significant digits
(e.g. 1 digit: 10, 2 digits: 100, and so on).</p><p>Important: Be sure that the maximum value in the rater multiplied by
           10 ^ significantDigits does not overflow Int.MaxValue (2,147,483,647).
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetColorBreaks" targe="_blank">statistics.op.stat.GetColorBreaks</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate quantile class breaks with assigned colors.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.BuildColorMapper" targe="_blank">statistics.op.stat.BuildColorMapper</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.BuildColorBreaks" targe="_blank">statistics.op.stat.BuildColorBreaks</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetColorsFromPalette" targe="_blank">statistics.op.stat.GetColorsFromPalette</a></code></td><td><div id="comment" class="fullcommenttop"></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetMinMax" targe="_blank">statistics.op.stat.GetMinMax</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Find the minimum and maximum value of a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Currently does not support finding double Min and Max values.
         If used with a raster with a double data type (TypeFloat,TypeDouble),
         will find the integer min and max of the rounded cell values.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetHistogramMap" targe="_blank">statistics.op.stat.GetHistogramMap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Implements a histogram in terms of a map.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Rasters with a double type (TypeFloat,TypeDouble) will have their values
          rounded to integers when making the Histogram.
</p></span></dd></dl></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetStatistics" targe="_blank">statistics.op.stat.GetStatistics</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Determine statistical data for the given histogram.</p><p>This includes mean, median, mode, stddev, and min and max values.
</p></div></div></td></tr>


</tbody>
</table>
