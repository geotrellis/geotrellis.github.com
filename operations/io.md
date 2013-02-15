---
layout: operations
title: IO

tutorial: operations
num: 10
---

These sets of operation are relevant to all compound operations as they are used to load data, produce output formats, and as the functional programming constructs that are critical to operation composition.

#### IO operations 

IO operations provide input, loading data, and output, translating the output of geoprocessing models
into output formats. Scala package [geotrellis.io.op.](http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.CsvIntMap" target="_blank">io.CsvIntMap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Create a Map of (String,String) =&gt; Int from a CSV file of the format: String,String,Int</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadFile" target="_blank">io.LoadFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadFileWithRasterExtent" target="_blank">io.LoadFileWithRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><p>Load the raster data from the specified file, using the RasterExtent provided.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadGeoJsonFeature" target="_blank">io.LoadGeoJsonFeature</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load a feature from GeoJson.</p><p>This operation loads a feature from GeoJson.  It accepts both simple geometry definitions and feature definitions.  If there is a property JSON clause, the feature data will be Some(JsonNode).</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadRaster" target="_blank">io.LoadRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the raster data for a particular extent/resolution from the specified file.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadRasterExtent" target="_blank">io.LoadRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><p>Load the RasterExtent from the raster layer with the specified name.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadRasterExtentFromFile" target="_blank">io.LoadRasterExtentFromFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the RasterExtent from the raster in the specified file.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadRasterMetadataFromFile" target="_blank">io.LoadRasterMetadataFromFile</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the RasterLayer, a representation of the raster metadata,from the raster in the specified file.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadTileSet" target="_blank">io.LoadTileSet</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Load the a set of tiles the specified directory.</p><p>This directory must contain a layout.json file as well as tiles written in the ARG format. </p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.LoadWkt" target="_blank">io.LoadWkt</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Reads feature data from a string of Well Known Text data.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.RenderGeoTiff" target="_blank">io.RenderGeoTiff</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Render a raster as a GeoTiff.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.RenderPng" target="_blank">io.RenderPng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a raster.</p><p>Use this operation when you have a raster of data that you want to visualize with an image.</p><p>To render a data raster into an image, the operation needs to know which values should be painted with which colors.  To that end, you'll need to generate a ColorBreaks object which represents the value ranges and the assigned color.  One way to create these color breaks is to use the GetClassBreaks operation to generate quantile class breaks.</p><p>See the API documentation for example usage.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.RenderPngRgba" target="_blank">io.RenderPngRgba</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG from a raster of RGBA integer values.</p><p>Use this operation when you have created a raster whose values are already RGBA color values that you wish to render into a PNG.  If you have a raster with data that you wish to render, you should use RenderPng instead.</p><p>An RGBA value is a 32 bit integer with 8 bits used for each component: the first 8 bits are the red value (between 0 and 255), then green, blue, and alpha (with 0 being transparent and 255 being opaque). </p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.SimpleRenderPng" target="_blank">io.SimpleRenderPng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Generate a PNG image from a data raster.</p><p>This operation is designed to provide a simple interface to generate a colored image from a data raster.  The data values in your raster will be classified into a number of ranges, and cells in each range will be rendered with a unique color.  You can select the number of ranges that will be used, and the color ramp from which the colors will be selected.</p><p>There are some color ramps you can select in geotrellis.data, and the default ramp (if you do not provide one) ranges from red to yellow to green. </p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.WritePng" target="_blank">io.WritePng</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG graphic file to the file system at the specified path. </p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.io.WritePngRgba" target="_blank">io.WritePngRgba</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Write out a PNG file of a raster that contains RGBA values) </p></div></div></td></tr>



</tbody>
</table>
