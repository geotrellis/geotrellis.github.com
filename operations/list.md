---
layout: oplist
title: Operations List

tutorial: operations
num: 11
---

<div class="filterbar">
  <span class="title">Look up a term</span>
  <input class="field" id="filter" type="text" />
  <span id="filter-count"></span>
</div>

* #### Op1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op1">See the API Documentation for Op1</a></div>

* #### DispatchedOperation
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.DispatchedOperation">See the API Documentation for DispatchedOperation</a></div>

* #### CompositeOperation
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given an operation and a function that takes the result of that operation and returns
a new operation, return an operation of the return type of the function.</p><p>If the initial operation is g, you can think of this operation as f(g(x))
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.CompositeOperation">See the API Documentation for CompositeOperation</a></div>

* #### OperationWrapper
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.OperationWrapper">See the API Documentation for OperationWrapper</a></div>

* #### Literal
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return the literal value specified.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.Literal">See the API Documentation for Literal</a></div>

* #### Op4
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op4">See the API Documentation for Op4</a></div>

* #### Op5
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op5">See the API Documentation for Op5</a></div>

* #### Op6
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op6">See the API Documentation for Op6</a></div>

* #### Op0
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Below are the Op0 - Op6 abstract classes.</p><p>These are useful for easily defining operations which just want to evaluate
their child operations and then run a single function afterwards.</p><p>For example:</p><p>case class Add2(x:Op[Int], y:Op[Int]) extends Op2(x, y)(_ + _)
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op0">See the API Documentation for Op0</a></div>

* #### Op2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op2">See the API Documentation for Op2</a></div>

* #### Op3
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.Op3">See the API Documentation for Op3</a></div>

* #### FlattenGeometry
None

* #### FilterGeometry
None

* #### AsPolygonSet
None

* #### Disjoint
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if two geometries are disjoint.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Disjoint">See the API Documentation for Disjoint</a></div>

* #### Simplify
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Simplify a polygon or multipolygon.</p><p>This operation uses a topology preserving simplifier that ensures the result has the same
characteristics as the input.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/simplify/TopologyPreservingSimplifier.html" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Simplify">See the API Documentation for Simplify</a></div>

* #### ConvexHull
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the convex hull of this geometry, which is the smallest polygon that contains it.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#convexHull()" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.ConvexHull">See the API Documentation for ConvexHull</a></div>

* #### Union
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the union of these geometries.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#union(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Union">See the API Documentation for Union</a></div>

* #### GetCentroid
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetCentroid">See the API Documentation for GetCentroid</a></div>

* #### GetDistance
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the minimum distance between these two geometries.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#distance(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetDistance">See the API Documentation for GetDistance</a></div>

* #### Covers
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry covers another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#covers(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Covers">See the API Documentation for Covers</a></div>

* #### GetEnvelope
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetEnvelope">See the API Documentation for GetEnvelope</a></div>

* #### Equals
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry equals another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#contains(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Equals">See the API Documentation for Equals</a></div>

* #### BufferWithParameters
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.BufferWithParameters">See the API Documentation for BufferWithParameters</a></div>

* #### GetArea
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the area of a geometry.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#getArea()" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetArea">See the API Documentation for GetArea</a></div>

* #### Erase
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry that contains the points in the first geometry that
aren't in the second geometry.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#difference(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Erase">See the API Documentation for Erase</a></div>

* #### Intersects
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry intersects another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersects(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Intersects">See the API Documentation for Intersects</a></div>

* #### GetSymDifference
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry defined by the points that are in one of the two geometries
but not the other.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.GetSymDifference">See the API Documentation for GetSymDifference</a></div>

* #### Buffer
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes a buffer area around this geometry.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#buffer(double," target="_blank">int, int) "JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Buffer">See the API Documentation for Buffer</a></div>

* #### Intersect
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the intersection of these geometries.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersection(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Intersect">See the API Documentation for Intersect</a></div>

* #### Overlaps
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry overlaps another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#intersects(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Overlaps">See the API Documentation for Overlaps</a></div>

* #### Contains
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry contains another.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html#contains(com.vividsolutions.jts.geom.Geometry)" target="_blank">"JTS documentation"</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.feature.op.geometry.Contains">See the API Documentation for Contains</a></div>

* #### LoadFile
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadFile">See the API Documentation for LoadFile</a></div>

* #### LoadFileWithRasterExtent
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadFileWithRasterExtent">See the API Documentation for LoadFileWithRasterExtent</a></div>

* #### CsvIntMap
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a Map of (String,String) =&gt; Int from a CSV file
of the format: String,String,Int
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.CsvIntMap">See the API Documentation for CsvIntMap</a></div>

* #### LoadRasterExtentFromFile
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the <a href="../RasterExtent.html" class="extype" name="geotrellis.RasterExtent">RasterExtent</a> from the raster in the specified file.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterExtentFromFile">See the API Documentation for LoadRasterExtentFromFile</a></div>

* #### LoadRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRaster">See the API Documentation for LoadRaster</a></div>

* #### LoadRasterMetadataFromFile
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the <a href="../process/RasterLayer.html" class="extype" name="geotrellis.process.RasterLayer">geotrellis.process.RasterLayer</a>, a representation of the raster metadata,
from the raster in the specified file.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterMetadataFromFile">See the API Documentation for LoadRasterMetadataFromFile</a></div>

* #### SimpleRenderPng
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a data raster.</p><p>This operation is designed to provide a simple interface to generate a
colored image from a data raster.  The data values in your raster will
be classified into a number of ranges, and cells in each range will be
rendered with a unique color.  You can select the number of ranges that
will be used, and the color ramp from which the colors will be selected.</p><p>There are some color ramps you can select in geotrellis.data, and the
default ramp (if you do not provide one) ranges from red to yellow to green.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.SimpleRenderPng">See the API Documentation for SimpleRenderPng</a></div>

* #### WritePng
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG graphic file to the file system at the specified path.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.WritePng">See the API Documentation for WritePng</a></div>

* #### LoadRasterExtent
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadRasterExtent">See the API Documentation for LoadRasterExtent</a></div>

* #### LoadWkt
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Reads feature data from a string of Well Known Text data.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadWkt">See the API Documentation for LoadWkt</a></div>

* #### LoadGeoJsonFeature
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load a feature from GeoJson.</p><p>This operation loads a feature from GeoJson.  It accepts both simple
geometry definitions and feature definitions.  If there is a property
JSON clause, the feature data will be Some(JsonNode).
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadGeoJsonFeature">See the API Documentation for LoadGeoJsonFeature</a></div>

* #### WritePngRgba
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG file of a raster that contains RGBA values)
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.WritePngRgba">See the API Documentation for WritePngRgba</a></div>

* #### RenderPng
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a raster.</p><p>Use this operation when you have a raster of data that you want to visualize
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
<span class="kw">val</span> pngOp = io.RenderPng(rOp, braeksOp, histogramOp, <span class="num">0</span>)</pre></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderPng">See the API Documentation for RenderPng</a></div>

* #### RenderPngRgba
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG from a raster of RGBA integer values.</p><p>Use this operation when you have created a raster whose values are already
RGBA color values that you wish to render into a PNG.  If you have a raster
with data that you wish to render, you should use RenderPng instead.</p><p>An RGBA value is a 32 bit integer with 8 bits used for each component:
the first 8 bits are the red value (between 0 and 255), then green, blue,
and alpha (with 0 being transparent and 255 being opaque).
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderPngRgba">See the API Documentation for RenderPngRgba</a></div>

* #### LoadTileSet
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the a set of tiles the specified directory.</p><p>This directory must contain a layout.json file as well as tiles written
in the ARG format.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.LoadTileSet">See the API Documentation for LoadTileSet</a></div>

* #### RenderGeoTiff
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Render a raster as a GeoTiff.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.io.RenderGeoTiff">See the API Documentation for RenderGeoTiff</a></div>

* #### Collect
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Collect">See the API Documentation for Collect</a></div>

* #### ForEach2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operations (opA and opB) to get an array of A's and an
array of B's. Then, applies the given function (f) to each (A, B) item in
the arrays (pairwise by array index) to get a Z value. The resulting array
of Z's is returned.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach2">See the API Documentation for ForEach2</a></div>

* #### ForEach3
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operations (opA opB, and opC) to get arrays of A's, B's
and C's (which should be the same length).</p><p>Then, applies the given function (f) to each (A, B, C) triple in (grouped by
array index) to get a Z value. The resulting array of Z's is returned.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach3">See the API Documentation for ForEach3</a></div>

* #### ForEach1
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operation (op) to get an array of A's. Then, applies
the given function (f) to each item in the array in. The resulting array of
Z's is returned.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.ForEach1">See the API Documentation for ForEach1</a></div>

* #### CollectArray
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.CollectArray">See the API Documentation for CollectArray</a></div>

* #### WithResult
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Run a function on the result of an operation</p><p>Functionally speaking, this represents the bind operation
on the Operation monad
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.WithResult">See the API Documentation for WithResult</a></div>

* #### AsList
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return the result of the input operation as a List.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.AsList">See the API Documentation for AsList</a></div>

* #### Do2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Invoke a function that takes two arguments.</p><p>Functionally speaking: Map an Op[A] and Op[B] into an Op[Z] using a
function from (A,B) =&gt; Z.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Do2">See the API Documentation for Do2</a></div>

* #### Do1
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Invoke a function that takes one argument.</p><p>Functionally speaking: Map an Op[A] into an Op[Z]
using a function from A =&gt; Z.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Do1">See the API Documentation for Do1</a></div>

* #### Reducer1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Reducer1">See the API Documentation for Reducer1</a></div>

* #### Reducer2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.Reducer2">See the API Documentation for Reducer2</a></div>

* #### If
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.If">See the API Documentation for If</a></div>

* #### Pure
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "pure" on Functor.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Pure">See the API Documentation for Pure</a></div>

* #### Apply
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "apply" (&lt;*&gt;) on Functor.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Apply">See the API Documentation for Apply</a></div>

* #### Fmap
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "fmap" on Functor.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.logic.applicative.Fmap">See the API Documentation for Fmap</a></div>

* #### Force
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Forces evaluation of the resulting raster of the passed in operation.
This is useful when you want to force lazy operations to happen
at specific points in the operation chain.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.Force">See the API Documentation for Force</a></div>

* #### CreateRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates an empty raster object based on the given raster properties.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.CreateRaster">See the API Documentation for CreateRaster</a></div>

* #### ZonalHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a raster, return a histogram summary of the cells within each zone.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>ZonalHistorgram does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.ZonalHistogram">See the API Documentation for ZonalHistogram</a></div>

* #### VerticalFlip
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Flip the data for a raster along the X-axis.</p><p>The geographic extent will remain unchanged.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>VerticalFlip does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.VerticalFlip">See the API Documentation for VerticalFlip</a></div>

* #### AsArrayDouble
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Converts a raster to a double array.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.data.AsArrayDouble">See the API Documentation for AsArrayDouble</a></div>

* #### AsArray
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Converts a raster to an integer array.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.data.AsArray">See the API Documentation for AsArray</a></div>

* #### GetExtent
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates an extent out of boundary values.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetExtent">See the API Documentation for GetExtent</a></div>

* #### CombineExtents
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return a the smallest extent that contains this extent and the provided
extent. This is provides a union of the two extents.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CombineExtents">See the API Documentation for CombineExtents</a></div>

* #### CropRasterExtentByExtent
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CropRasterExtentByExtent">See the API Documentation for CropRasterExtentByExtent</a></div>

* #### CropRasterExtent
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.CropRasterExtent">See the API Documentation for CropRasterExtent</a></div>

* #### GetRasterExtentFromRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Get the <a href="../../../RasterExtent.html" class="extype" name="geotrellis.RasterExtent">RasterExtent</a> from a given raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetRasterExtentFromRaster">See the API Documentation for GetRasterExtentFromRaster</a></div>

* #### GetRasterExtent
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a geographical extent and grid height/width, return an object used to
load raster data.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.GetRasterExtent">See the API Documentation for GetRasterExtent</a></div>

* #### ChunkRasterExtent
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Used to chunk a RasterExtent object (geographical extent + grid information)
into many smaller contiguous pieces. The number of columns desired is
provided by <code>nx</code> and the number of rows by <code>ny</code>.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.extent.ChunkRasterExtent">See the API Documentation for ChunkRasterExtent</a></div>

* #### CostDistance
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a Cost-Distance raster based on a set of starting points and a cost
raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Operation will only work with integer typed Cost Rasters (TypeBit,TypeByte,TypeShort,TypeInt).
         If a double typed Cost Raster (TypeFloat,TypeDouble) is passed in, those costs will be rounded
         to their floor integer values.</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CostDistance">See the API Documentation for CostDistance</a></div>

* #### IndirectHillshade
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Indirect calculation of hill shading of a raster that uses Aspect and Slope operation results.</p><p>Construct through the <a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a> object.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Does not currently work with TiledFocalOps of Aspect and Slope.
                    Use the direct method with TileFocalOps and tiled raster data.</p></span></dd><dt>See also</dt><dd><span class="cmt"><p><a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.IndirectHillshade">See the API Documentation for IndirectHillshade</a></div>

* #### Aspect
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates the aspect of each cell in a raster.</p><p>Aspect is the direction component of a gradient vector. It is the
direction in degrees of which direction the maximum change in direction is pointing.
It is defined as the directional component of the gradient vector and is the
direction of maximum gradient of the surface at a given point. It uses Horn's method
for computing aspect.</p><p>As with slope, aspect is calculated from estimates of the partial derivatives dz/dx and dz/dy.</p><p>Aspect is computed in degrees from due north, i.e. as an azimuth in degrees not radians.
The expression for aspect is:</p><pre><span class="kw">val</span> aspect = <span class="num">270</span> - <span class="num">360</span>/(<span class="num">2</span>*Pi) * atan2(`dz/dy`, - `dz/dx`)</pre></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Paraphrased from
<a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a>
(Smit, Longley, and Goodchild)
</p></span></dd><dt>See also</dt><dd><span class="cmt"><p><a href="SurfacePoint.html" class="extype" name="geotrellis.raster.op.focal.SurfacePoint">SurfacePoint</a> for aspect calculation logic.</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Aspect">See the API Documentation for Aspect</a></div>

* #### AutomaticNormalize
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Normalize the values in the given raster so that all values are within the
specified minimum and maximum value range.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>AutomaticNormalize does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.AutomaticNormalize">See the API Documentation for AutomaticNormalize</a></div>

* #### Max
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the maximum value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Maximum does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Max">See the API Documentation for Max</a></div>

* #### FocalOperation
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster and a neighborhood.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation">See the API Documentation for FocalOperation</a></div>

* #### Median
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the median value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Median does not currently support Double raster data.
         If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
         the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Median">See the API Documentation for Median</a></div>

* #### DirectHillshade
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Direct calculation of hill shading of a raster. Construct through the <a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a> object.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="Hillshade%24.html" class="extype" name="geotrellis.raster.op.focal.Hillshade">Hillshade</a>
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.DirectHillshade">See the API Documentation for DirectHillshade</a></div>

* #### Mode
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the mode of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Mode does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Mode">See the API Documentation for Mode</a></div>

* #### Mean
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the mean value of a neighborhood for a given raster. Returns a raster of TypeDouble
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Mean does not currently support Double raster data inputs.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span>, <span class="cmt"><p>If the neighborhood is a <a href="Square.html" class="extype" name="geotrellis.raster.op.focal.Square">Square</a> neighborhood, the mean calucation will use
                 the <a href="CellwiseMeanCalc.html" class="extype" name="geotrellis.raster.op.focal.CellwiseMeanCalc">CellwiseMeanCalc</a> to perform the calculation, because it is faster.
                 If the neighborhood is of any other type, then <a href="CursorMeanCalc.html" class="extype" name="geotrellis.raster.op.focal.CursorMeanCalc">CursorMeanCalc</a> is used.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Mean">See the API Documentation for Mean</a></div>

* #### CreateCircleRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a Circle raster. Can be used with the <a href="Convolve.html" class="extype" name="geotrellis.raster.op.focal.Convolve">Convolve</a> or <a href="KernelDensity.html" class="extype" name="geotrellis.raster.op.focal.KernelDensity">KernelDensity</a> operations.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CreateCircleRaster">See the API Documentation for CreateCircleRaster</a></div>

* #### FocalOperation4
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and four other argument.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation4">See the API Documentation for FocalOperation4</a></div>

* #### FocalOperation1
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and one other argument.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation1">See the API Documentation for FocalOperation1</a></div>

* #### FocalOperation3
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and three other argument.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation3">See the API Documentation for FocalOperation3</a></div>

* #### FocalOperation2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Base class for a focal operation that takes a raster, a neighborhood, and two other argument.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOperation2">See the API Documentation for FocalOperation2</a></div>

* #### ScalarMoransI
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates global spatial autocorrelation of a raster based on the similarity to
neighboring values.</p><p>The resulting statistic is such that the more positive the number, the greater
the similarity of values in the raster, and the more negative the number,
the more dissimilar the raster values are.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Since mean and standard deviation are based off of an
                       Int based Histogram, those values will come from rounded values
                       of a double typed Raster (TypeFloat,TypeDouble).
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.ScalarMoransI">See the API Documentation for ScalarMoransI</a></div>

* #### FocalOp
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster and a neighborhood.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp">See the API Documentation for FocalOp</a></div>

* #### Convolve
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the convolution of two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Convolve does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Convolve">See the API Documentation for Convolve</a></div>

* #### Slope
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates the slope of each cell in a raster.</p><p>Slope is the magnitude portion of the gradient vector. It is the maximum
change of elevation from a raster cell to any immediate neighbor. It uses Horn's method
for computing slope.</p><p>As with aspect, slope is calculated from estimates of the partial derivatives dz/dx and dz/dy.</p><p>Slope is computed in degrees from horizontal.</p><p>The expression for slope is:</p><pre><span class="kw">val</span> slope = atan(sqrt(pow(`dz/dy`,<span class="num">2</span>) * pow(`dz/dx`,<span class="num">2</span>)))</pre></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p><a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a>
(Smit, Longley, and Goodchild)
</p></span><span class="cmt"><p><a href="SurfacePoint.html" class="extype" name="geotrellis.raster.op.focal.SurfacePoint">SurfacePoint</a> for slope calculation logic.</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Slope">See the API Documentation for Slope</a></div>

* #### FocalOp4
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and four other arguments.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp4">See the API Documentation for FocalOp4</a></div>

* #### FocalOp2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and two other arguments.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp2">See the API Documentation for FocalOp2</a></div>

* #### FocalOp3
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and three other arguments.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp3">See the API Documentation for FocalOp3</a></div>

* #### FocalOp1
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Focal Operation that takes a raster, a neighborhood, and one other argument.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.FocalOp1">See the API Documentation for FocalOp1</a></div>

* #### CreateGaussianRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a Gaussian raster. Can be used with the <a href="Convolve.html" class="extype" name="geotrellis.raster.op.focal.Convolve">Convolve</a> or <a href="KernelDensity.html" class="extype" name="geotrellis.raster.op.focal.KernelDensity">KernelDensity</a> operations.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.CreateGaussianRaster">See the API Documentation for CreateGaussianRaster</a></div>

* #### Conway
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the next step of Conway's Game of Life for a given <a href="../../../Raster.html" class="extype" name="geotrellis.Raster">Raster</a>.
</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt"><p>A description of Conway's Game of Life can be found on
<a href="http://en.wikipedia.org/wiki/Conway's_Game_of_Life" target="_blank">wikipedia</a>.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Conway">See the API Documentation for Conway</a></div>

* #### RasterMoransI
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Calculates spatial autocorrelation of cells based on the similarity to
neighboring values.</p><p>The statistic for each focus in the resulting raster is such that the more
positive the number, the greater the similarity between the focus value and
it's neighboring values, and the more negative the number, the more dissimilar
the focus value is with it's neighboring values.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Since mean and standard deviation are based off of an
                       Int based Histogram, those values will come from rounded values
                       of a double typed Raster (TypeFloat,TypeDouble).
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.RasterMoransI">See the API Documentation for RasterMoransI</a></div>

* #### Min
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the minimum value of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Min does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Min">See the API Documentation for Min</a></div>

* #### TileFocalOp
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.TileFocalOp">See the API Documentation for TileFocalOp</a></div>

* #### PrecomputedNormalize
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Normalize the values in the given raster.
zmin and zmax are the lowest and highest values in the provided raster.
gmin and gmax are the desired minimum and maximum values in the output raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>PrecomputedNormalize does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.PrecomputedNormalize">See the API Documentation for PrecomputedNormalize</a></div>

* #### Sum
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the sum of values of a neighborhood for a given raster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Sum does not currently support Double raster data.
                 If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                 the data values will be rounded to integers.
</p></span>, <span class="cmt"><p>If the neighborhood is a <a href="Square.html" class="extype" name="geotrellis.raster.op.focal.Square">Square</a> neighborhood, the sum calucation will use
                 the <a href="CellwiseSumCalc.html" class="extype" name="geotrellis.raster.op.focal.CellwiseSumCalc">CellwiseSumCalc</a> to perform the calculation, because it is faster.
                 If the neighborhood is of any other type, then <a href="CursorSumCalc.html" class="extype" name="geotrellis.raster.op.focal.CursorSumCalc">CursorSumCalc</a> is used.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.Sum">See the API Documentation for Sum</a></div>

* #### KernelDensity
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the Kernel Density for a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>KernelDensity does not currently support Double raster data.
                             If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                             the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.focal.KernelDensity">See the API Documentation for KernelDensity</a></div>

* #### UndefinedConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps an integer to 1 if NODATA, else 0.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UndefinedConstant">See the API Documentation for UndefinedConstant</a></div>

* #### InverseMask
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a raster with the values from the first raster, but only include
cells in which the corresponding cell in the second raster is set to the
"readMask" value.</p><p>For example, if *all* cells in the second raster are set to the readMask value,
the output raster will be identical to the first raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.InverseMask">See the API Documentation for InverseMask</a></div>

* #### MinConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes a Raster and an Int, and gives a raster with each cell being
the min value of the original raster and the integer.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinConstant does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinConstant">See the API Documentation for MinConstant</a></div>

* #### BinaryLocal
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>BinaryLocal is an abstract class for all operations that are both local (operating
on each cell in a raster without knowledge of other cells) and binary, by which
we mean that the input includes two rasters (as opposed to 'unary' or 'multi').
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryLocal">See the API Documentation for BinaryLocal</a></div>

* #### BinaryDoCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a function on every cell in a raster with the values from another raster.</p><p>For example,
</p><pre>
val A = LoadFile(a)
val B = LoadFile(b)
// Generate a raster by adding the values of each cell in A and B
val D = BinaryDoCell(R, (a, b) =&gt; a + b )
</pre>
</div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryDoCell">See the API Documentation for BinaryDoCell</a></div>

* #### MultiplyDoubleConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant (double).</p><p>Create with MultiplyConstant(raster, doubleValue).
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyDoubleConstant">See the API Documentation for MultiplyDoubleConstant</a></div>

* #### CeilInt
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilInt">See the API Documentation for CeilInt</a></div>

* #### SubtractConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract a constant value from each cell.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractConstant">See the API Documentation for SubtractConstant</a></div>

* #### BinaryIfElseCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a condition over two rasters, set the value of each cell in the output
to a specified true or false value after testing the specified condition on
the corresponding values in each of the two input rasters.
each of the two input rasters.</p><p>Usage:
</p><pre>
// Generate a raster with the value 1 in each cell in which the value of A
// is greater than B in the corresponding cell.  Set the value to 0 if the
// condition is false.
val C = BinaryIfElseCell(A,B, (a,b) =&gt; a &gt; b, 1, 0)
</pre>
</div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryIfElseCell">See the API Documentation for BinaryIfElseCell</a></div>

* #### AddConstant2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add a constant value to each cell.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddConstant2">See the API Documentation for AddConstant2</a></div>

* #### PowDoubleConstantBy
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubleConstantBy">See the API Documentation for PowDoubleConstantBy</a></div>

* #### DivideConstantBy
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>For each cell, divide a constant value by that cell's value.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideConstantBy">See the API Documentation for DivideConstantBy</a></div>

* #### Mask
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a raster with the values from the first raster, but only include
cells in which the corresponding cell in the second raster *are not* set to the
"readMask" value.</p><p>For example, if *all* cells in the second raster are set to the readMask value,
the output raster will be empty -- all values set to NODATA.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.Mask">See the API Documentation for Mask</a></div>

* #### MultiplyConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyConstant">See the API Documentation for MultiplyConstant</a></div>

* #### EqualConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualConstant1">See the API Documentation for EqualConstant1</a></div>

* #### LessOrEqualConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualConstant1">See the API Documentation for LessOrEqualConstant1</a></div>

* #### GreaterOrEqualConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualConstant2">See the API Documentation for GreaterOrEqualConstant2</a></div>

* #### GreaterOrEqualConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualConstant1">See the API Documentation for GreaterOrEqualConstant1</a></div>

* #### DefinedConstant
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DefinedConstant">See the API Documentation for DefinedConstant</a></div>

* #### BinaryIfCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Given a condition over two rasters, set the value of each cell in the output
to a specified value if the condition is true given the corresponding values in
each of the two input rasters.</p><p>Local operation.
Binary operation (input includes two rasters).
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.BinaryIfCell">See the API Documentation for BinaryIfCell</a></div>

* #### SubtractRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract each value in the second raster from the corresponding value in the first raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractRaster">See the API Documentation for SubtractRaster</a></div>

* #### UnequalConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalConstant1">See the API Documentation for UnequalConstant1</a></div>

* #### RoundRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundRaster">See the API Documentation for RoundRaster</a></div>

* #### RoundInt
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundInt">See the API Documentation for RoundInt</a></div>

* #### NotRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the bitwise negation of each cell value.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>NotRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.NotRaster">See the API Documentation for NotRaster</a></div>

* #### DoCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a function on every cell in a raster.</p><p>For example,
</p><pre>
val R = LoadFile(f)
val D = DoCell(R, x =&gt; x + 3 ) // add 3 to every cell in the raster
</pre>
</div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>DoCell does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DoCell">See the API Documentation for DoCell</a></div>

* #### SqrtDouble
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtDouble">See the API Documentation for SqrtDouble</a></div>

* #### SqrtInt
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtInt">See the API Documentation for SqrtInt</a></div>

* #### OrRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Or's the cell values of the two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrRaster">See the API Documentation for OrRaster</a></div>

* #### AndConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndConstant1">See the API Documentation for AndConstant1</a></div>

* #### CeilDouble
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilDouble">See the API Documentation for CeilDouble</a></div>

* #### AndConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndConstant2">See the API Documentation for AndConstant2</a></div>

* #### DivideDoubleConstantBy
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideDoubleConstantBy">See the API Documentation for DivideDoubleConstantBy</a></div>

* #### FloorInt
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorInt">See the API Documentation for FloorInt</a></div>

* #### CeilRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes the Ceiling of each raster cell value.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.CeilRaster">See the API Documentation for CeilRaster</a></div>

* #### PowConstant
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowConstant">See the API Documentation for PowConstant</a></div>

* #### NotConstant
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.NotConstant">See the API Documentation for NotConstant</a></div>

* #### PowDoubles
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubles">See the API Documentation for PowDoubles</a></div>

* #### MultiplyArray
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell of each raster in array.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyArray">See the API Documentation for MultiplyArray</a></div>

* #### OrConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrConstant2">See the API Documentation for OrConstant2</a></div>

* #### OrConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.OrConstant1">See the API Documentation for OrConstant1</a></div>

* #### PowConstantBy
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowConstantBy">See the API Documentation for PowConstantBy</a></div>

* #### LogDouble
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogDouble">See the API Documentation for LogDouble</a></div>

* #### XorConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorConstant1">See the API Documentation for XorConstant1</a></div>

* #### MaxConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of a rasters and a constant.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxConstant does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxConstant">See the API Documentation for MaxConstant</a></div>

* #### XorConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorConstant2">See the API Documentation for XorConstant2</a></div>

* #### LessOrEqualConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualConstant2">See the API Documentation for LessOrEqualConstant2</a></div>

* #### EqualRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualRaster">See the API Documentation for EqualRaster</a></div>

* #### LogInt
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogInt">See the API Documentation for LogInt</a></div>

* #### DivideConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Divide each cell by a constant value.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideConstant">See the API Documentation for DivideConstant</a></div>

* #### MinConstant2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes an Int and a Raster, and gives a raster with each cell being
the min value of the original raster and the integer.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinConstant2 does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinConstant2">See the API Documentation for MinConstant2</a></div>

* #### MultiLocal
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiLocal">See the API Documentation for MultiLocal</a></div>

* #### UnequalConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalConstant2">See the API Documentation for UnequalConstant2</a></div>

* #### MultiplyConstant2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Multiply each cell by a constant.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiplyConstant2">See the API Documentation for MultiplyConstant2</a></div>

* #### LessConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessConstant1">See the API Documentation for LessConstant1</a></div>

* #### LessConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessConstant2">See the API Documentation for LessConstant2</a></div>

* #### MinRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes two Rasters and gives a raster with the min values of the two at each cell.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MinRaster">See the API Documentation for MinRaster</a></div>

* #### DefinedRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps an integer typed Raster to 1 if the cell value is not NODATA, otherwise 0.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DefinedRaster">See the API Documentation for DefinedRaster</a></div>

* #### FloorRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorRaster">See the API Documentation for FloorRaster</a></div>

* #### PowDoubleConstant
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowDoubleConstant">See the API Documentation for PowDoubleConstant</a></div>

* #### LessRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessRaster">See the API Documentation for LessRaster</a></div>

* #### XorRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Xor's the cell values of two integer typed Rasters.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.XorRaster">See the API Documentation for XorRaster</a></div>

* #### LessOrEqualRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LessOrEqualRaster">See the API Documentation for LessOrEqualRaster</a></div>

* #### FloorDouble
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.FloorDouble">See the API Documentation for FloorDouble</a></div>

* #### UndefinedRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps Raster cell values to 1 if they are NODATA, else 0.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UndefinedRaster">See the API Documentation for UndefinedRaster</a></div>

* #### AddArray
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add the values of each cell in each raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddArray">See the API Documentation for AddArray</a></div>

* #### PowInts
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowInts">See the API Documentation for PowInts</a></div>

* #### SqrtRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SqrtRaster">See the API Documentation for SqrtRaster</a></div>

* #### GreaterRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterRaster">See the API Documentation for GreaterRaster</a></div>

* #### AddConstant
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Add a constant value to each cell.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AddConstant">See the API Documentation for AddConstant</a></div>

* #### PowRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Takes the cell value of the first raster and raises it to the power determined
by the cell value of the second raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.PowRaster">See the API Documentation for PowRaster</a></div>

* #### LogRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LogRaster">See the API Documentation for LogRaster</a></div>

* #### MultiLocalArray
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MultiLocalArray">See the API Documentation for MultiLocalArray</a></div>

* #### IfCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Maps all cells matching <code>cond</code> to <code>trueValue</code>.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.IfCell">See the API Documentation for IfCell</a></div>

* #### LocalOperation
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Local operations involve each individual value in a raster without information
about other values in the raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.LocalOperation">See the API Documentation for LocalOperation</a></div>

* #### RoundDouble
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.RoundDouble">See the API Documentation for RoundDouble</a></div>

* #### GreaterConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterConstant2">See the API Documentation for GreaterConstant2</a></div>

* #### GreaterConstant1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterConstant1">See the API Documentation for GreaterConstant1</a></div>

* #### DivideDoubleConstant
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideDoubleConstant">See the API Documentation for DivideDoubleConstant</a></div>

* #### SubtractConstantBy
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Subtract the value of each cell by a constant.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.SubtractConstantBy">See the API Documentation for SubtractConstantBy</a></div>

* #### Negate
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Negate (multiply by -1) each value in a raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.Negate">See the API Documentation for Negate</a></div>

* #### DivideRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Divide each value of one raster with the values from another raster.
Local operation.
Binary operation.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.DivideRaster">See the API Documentation for DivideRaster</a></div>

* #### AndRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>And's the cell values of two rasters together.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MinRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.AndRaster">See the API Documentation for AndRaster</a></div>

* #### GreaterOrEqualRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.GreaterOrEqualRaster">See the API Documentation for GreaterOrEqualRaster</a></div>

* #### EqualConstant2
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.EqualConstant2">See the API Documentation for EqualConstant2</a></div>

* #### UnequalRaster
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.UnequalRaster">See the API Documentation for UnequalRaster</a></div>

* #### MaxRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of two rasters.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxRaster does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxRaster">See the API Documentation for MaxRaster</a></div>

* #### IfElseCell
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Set all values of output raster to one value or another based on whether a
condition is true or false.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.IfElseCell">See the API Documentation for IfElseCell</a></div>

* #### MaxConstant2
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Gets the maximum value between cell values of a rasters and a constant.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>MaxConstant2 does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.local.MaxConstant2">See the API Documentation for MaxConstant2</a></div>

* #### TileMin
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Performs a local Min operation on a TiledRaster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileMin does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileMin">See the API Documentation for TileMin</a></div>

* #### TileHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Creates a histogram for a TiledRaster
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileHistogram does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileHistogram">See the API Documentation for TileHistogram</a></div>

* #### ThroughputLimitedReducer1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.ThroughputLimitedReducer1">See the API Documentation for ThroughputLimitedReducer1</a></div>

* #### TileMax
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Performs a local Max operation on a TiledRaster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>TileMax does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.TileMax">See the API Documentation for TileMax</a></div>

* #### Reducer1
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.tiles.Reducer1">See the API Documentation for Reducer1</a></div>

* #### ResampleRaster
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This uses a nearest-neighbor algorithm to resample a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Resample does not currently support Double raster data.
                    If you use a Raster with a Double RasterType (TypeFloat,TypeDouble)
                    the data values will be rounded to integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.transform.ResampleRaster">See the API Documentation for ResampleRaster</a></div>

* #### Crop
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a new raster from the data in a sub-extent of an existing raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.transform.Crop">See the API Documentation for Crop</a></div>

* #### Max
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Max for double type rasters
(TypeFloat,TypeDouble) use <a href="MaxDouble.html" class="extype" name="geotrellis.raster.op.zonal.MaxDouble">MaxDouble</a>
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Max">See the API Documentation for Max</a></div>

* #### Histogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates a histogram all raster cells within a geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Histogram">See the API Documentation for Histogram</a></div>

* #### MinDouble
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the min of all raster cells within a geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.MinDouble">See the API Documentation for MinDouble</a></div>

* #### Sum
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the sum of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Sum for double type rasters
(TypeFloat,TypeDouble) use <a href="SumDouble.html" class="extype" name="geotrellis.raster.op.zonal.SumDouble">SumDouble</a>
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Sum">See the API Documentation for Sum</a></div>

* #### Min
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the min of all raster cells within a geometry.
This operation is for integer typed Rasters. If you want the Min for double type rasters
(TypeFloat,TypeDouble) use <a href="MinDouble.html" class="extype" name="geotrellis.raster.op.zonal.MinDouble">MinDouble</a>
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.Min">See the API Documentation for Min</a></div>

* #### MaxDouble
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the max value of all raster cells within a geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.MaxDouble">See the API Documentation for MaxDouble</a></div>

* #### SumDouble
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Perform a zonal summary that calculates the sum of all raster cells within a geometry.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.SumDouble">See the API Documentation for SumDouble</a></div>

* #### TiledPolygonalZonalSummary
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.raster.op.zonal.TiledPolygonalZonalSummary">See the API Documentation for TiledPolygonalZonalSummary</a></div>

* #### SplitOnComma
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Split a string on a comma.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.SplitOnComma">See the API Documentation for SplitOnComma</a></div>

* #### ParseColor
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as a color.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseColor">See the API Documentation for ParseColor</a></div>

* #### ParseInt
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as an integer.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseInt">See the API Documentation for ParseInt</a></div>

* #### ParseExtent
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseExtent">See the API Documentation for ParseExtent</a></div>

* #### ParseDouble
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Parse a string as a double.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.ParseDouble">See the API Documentation for ParseDouble</a></div>

* #### Split
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Split a string on a comma.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.rest.op.string.Split">See the API Documentation for Split</a></div>

* #### MapHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram that uses a Map (as in hashtable map/dictionary) for internal storage.</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.MapHistogram">See the API Documentation for MapHistogram</a></div>

* #### CompressedArrayHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram using an array for internal storage,
which requires an initial minimum and maximum val and a specified number of 'breaks' which
are used to group values together into ranges.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>CompressedArrayHistogram can currently only handle non-negative integers.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.CompressedArrayHistogram">See the API Documentation for CompressedArrayHistogram</a></div>

* #### FastMapHistogram
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.FastMapHistogram">See the API Documentation for FastMapHistogram</a></div>

* #### ArrayHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Data object representing a histogram that uses an array for internal storage.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.ArrayHistogram">See the API Documentation for ArrayHistogram</a></div>

* #### GetClassBreaks
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate quantile class breaks for a given raster.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetClassBreaks">See the API Documentation for GetClassBreaks</a></div>

* #### GetHistogramArray
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Implements a histogram in terms of an array of the given size.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Rasters with a double type (TypeFloat,TypeDouble) will have their values
          rounded to integers when making the Histogram.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetHistogramArray">See the API Documentation for GetHistogramArray</a></div>

* #### GetStandardDeviation
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetStandardDeviation">See the API Documentation for GetStandardDeviation</a></div>

* #### GetDoubleHistogram
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a histogram from double values in a raster.</p><p>FastMapHistogram only works with integer values, which is great for performance
but means that, in order to use FastMapHistogram with double values, each value
must be multiplied by a power of ten to preserve significant fractional digits.</p><p>For example, if you want to save one significant digit (2.1 from 2.123), set
sigificantDigits to 1, and the histogram will save 2.1 as "21" by multiplying
each value by 10.  The multiplier is 10 raised to the power of significant digits
(e.g. 1 digit: 10, 2 digits: 100, and so on).</p><p>Important: Be sure that the maximum value in the rater multiplied by
           10 ^ significantDigits does not overflow Int.MaxValue (2,147,483,647).
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetDoubleHistogram">See the API Documentation for GetDoubleHistogram</a></div>

* #### GetColorBreaks
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate quantile class breaks with assigned colors.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetColorBreaks">See the API Documentation for GetColorBreaks</a></div>

* #### BuildColorMapper
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.BuildColorMapper">See the API Documentation for BuildColorMapper</a></div>

* #### BuildColorBreaks
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.BuildColorBreaks">See the API Documentation for BuildColorBreaks</a></div>

* #### GetColorsFromPalette
<div id="comment" class="fullcommenttop"><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetColorsFromPalette">See the API Documentation for GetColorsFromPalette</a></div>

* #### GetMinMax
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Find the minimum and maximum value of a raster.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Currently does not support finding double Min and Max values.
         If used with a raster with a double data type (TypeFloat,TypeDouble),
         will find the integer min and max of the rounded cell values.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetMinMax">See the API Documentation for GetMinMax</a></div>

* #### GetHistogramMap
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Implements a histogram in terms of a map.
</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Rasters with a double type (TypeFloat,TypeDouble) will have their values
          rounded to integers when making the Histogram.
</p></span></dd></dl><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetHistogramMap">See the API Documentation for GetHistogramMap</a></div>

* #### GetStatistics
<div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Determine statistical data for the given histogram.</p><p>This includes mean, median, mode, stddev, and min and max values.
</p></div><a href="http://geotrellis.github.com/latest/api/#geotrellis.statistics.op.stat.GetStatistics">See the API Documentation for GetStatistics</a></div>

