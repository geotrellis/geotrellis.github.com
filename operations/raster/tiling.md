---
layout: operations
title: Other Operations

tutorial: operations
num: 7
sub: true
---

#### Tile Operations

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.tiles.TileHistogram" target="_blank">tiles.TileHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Creates a histogram for a TiledRaster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>TileHistogram does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.tiles.TileMax" target="_blank">tiles.TileMax</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Performs a local Max operation on a TiledRaster.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>TileMax does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.tiles.TileMin" target="_blank">tiles.TileMin</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Performs a local Min operation on a TiledRaster.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>TileMin does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
</tbody>
</table>
    
#### RasterExtent Operations

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.ChunkRasterExtent" target="_blank">extent.ChunkRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Used to chunk a RasterExtent object (geographical extent + grid information) into many smaller contiguous pieces. The number of columns desired is provided by <code>nx</code> and the number of rows by <code>ny</code>. </p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.CombineExtents" target="_blank">extent.CombineExtents</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Return a the smallest extent that contains this extent and the provided extent. This is provides a union of the two extents.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.CropRasterExtent" target="_blank">extent.CropRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a geographical extent and grid height/width, return an object used to load raster data.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.CropRasterExtentByExtent" target="_blank">op.extent.CropRasterExtentByExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a geographical extent and grid height/width, return an object used to load raster data.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.GetExtent" target="_blank">extent.GetExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Creates an extent out of boundary values.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.GetRasterExtent" target="_blank">extent.GetRasterExtent</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a geographical extent and grid height/width, return an object used to load raster data.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.extent.GetRasterExtentFromRaster" target="_blank">extent.GetRasterExtentFromRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Get the RasterExtent from a given raster.</p></div></div></td></tr>
    
</tbody>
</table>

#### Transform Operations

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.transform.Crop" target="_blank">transform.Crop</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Create a new raster from the data in a sub-extent of an existing raster.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.transform.ResampleRaster" target="_blank">transform.ResampleRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>This uses a nearest-neighbor algorithm to resample a raster.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Resample does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
</tbody>
</table>

#### Other Operations

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.raster.op.CreateRaster" targe="_blank">CreateRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Creates an empty raster object based on the given raster properties.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.raster.op.Force" targe="_blank">Force</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Forces evaluation of the resulting raster of the passed in operation. This is useful when you want to force lazy operations to happen at specific points in the operation chain.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.raster.op.VerticalFlip" targe="_blank">VerticalFlip</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Flip the data for a raster along the X-axis.</p><p>The geographic extent will remain unchanged.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>VerticalFlip does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.raster.op.data.AsArray" targe="_blank">data.AsArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Converts a raster to an integer array.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.raster.op.data.AsArrayDouble" targe="_blank">data.AsArrayDouble</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Converts a raster to a double array.</p></div></div></td></tr>

</tbody>
</table>
