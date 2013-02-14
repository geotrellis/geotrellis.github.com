---
layout: operations
title: Focal Operations

tutorial: operations
num: 4
sub: true
---

#### Focal operations
Raster operations that work on raster cells and their neighbors. Located in [geotrellis.raster.op.focal.](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.package)

#### Neighborhoods
Neighborhoods define a region around a cell location in which the values (and possibly positions) will be used as input to a focal operation's calculation at that location. See the [Type Hierarchy of Neighborhood](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Neighborhood) to view the different types of Neighborhoods available.


<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Aspect" target="_blank">focal.Aspect</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Calculates the aspect of each cell in a raster.</p><p>Aspect is the direction component of a gradient vector. It is the direction in degrees of which direction the maximum change in direction is pointing. It is defined as the directional component of the gradient vector and is the direction of maximum gradient of the surface at a given point. It uses Horn's method for computing aspect.</p>
    <p>See the API documentation for more information, as well as <a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a> (Smit, Longley, and Goodchild) 
    </p></div></div></td></tr>
  
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Convolve" target="_blank">focal.Convolve</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the convolution of two rasters.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Convolve does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Conway" target="_blank">focal.Conway</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the next step of Conway's Game of Life for a given Raster.</p></div><dl class="attributes block"><dt>See also</dt>
    <dd><span class="cmt"><p>A description of Conway's Game of Life can be found on <a href="http://en.wikipedia.org/wiki/Conway's_Game_of_Life" target="_blank">wikipedia</a>.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.CostDistance" target="_blank">focal.CostDistance</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Generate a Cost-Distance raster based on a set of starting points and a cost raster</p></div>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Operation will only work with integer typed Cost Rasters (TypeBit,TypeByte,TypeShort,TypeInt). If a double typed Cost Raster (TypeFloat,TypeDouble) is passed in, those costs will be rounded to their floor integer values.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.CreateCircleRaster" target="_blank">focal.CreateCircleRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Creates a Circle raster. Can be used with the Convolve or KernelDensity operations.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.CreateGaussianRaster" target="_blank">focal.CreateGaussianRaster</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Creates a Gaussian raster. Can be used with the Convolve or KernelDensity operations.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Raster will be TypeInt</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Hillshade$" target="_blank">focal.Hillshade</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes Hillshade (shaded relief) from a raster. The resulting raster will be a shaded relief map (a hill shading) based on the sun altitude, azimuth, and the z factor. The z factor is a conversion factor from map units to elevation units. Returns a raster of TypeShort. This operation uses Horn's method for computing hill shading. See <a href="http://goo.gl/DtVDQ" target="_blank">Esri Desktop's description of Hillshade</a> for additional information.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.KernelDensity" target="_blank">focal.KernelDensity</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes a Density raster based on the Kernel and set of points provided.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>KernelDensity does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Max" target="_blank">focal.Max</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the maximum value of a neighborhood for a given raster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Maximum does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Mean" target="_blank">focal.Mean</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the mean value of a neighborhood for a given raster. Returns a raster of TypeDouble</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Mean does not currently support Double raster data inputs. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Median" target="_blank">focal.Median</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the median value of a neighborhood for a given raster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Median does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Min" target="_blank">focal.Min</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the minimum value of a neighborhood for a given raster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Min does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Mode" target="_blank">focal.Mode</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the mode of a neighborhood for a given raster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Mode does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.RasterMoransI" target="_blank">focal.RasterMoransI</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Calculates spatial autocorrelation of cells based on the similarity to neighboring values.</p><p>The statistic for each focus in the resulting raster is such that the more positive the number, the greater the similarity between the focus value and it's neighboring values, and the more negative the number, the more dissimilar the focus value is with it's neighboring values.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Since mean and standard deviation are based off of an Int based Histogram, those values will come from rounded values of a double typed Raster (TypeFloat,TypeDouble).</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Rescale$" target="_blank">focal.Rescale</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Rescale (normalize) the values in the given raster so that all values are within the specified minimum and maximum value range.</p>
    <p>You can also pass in the precomupted min and max raster values for optimization.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Rescale does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.ScalarMoransI" target="_blank">focal.ScalarMoransI</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Calculates global spatial autocorrelation of a raster based on the similarity to neighboring values.</p><p>The resulting statistic is such that the more positive the number, the greater the similarity of values in the raster, and the more negative the number, the more dissimilar the raster values are.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Since mean and standard deviation are based off of an Int based Histogram, those values will come from rounded values of a double typed Raster (TypeFloat,TypeDouble).</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Slope" target="_blank">focal.Slope</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Calculates the slope of each cell in a raster.</p><p>Slope is the magnitude portion of the gradient vector. It is the maximum change of elevation from a raster cell to any immediate neighbor. It uses Horn's method for computing slope.</p>
    <p>As with aspect, slope is calculated from estimates of the partial derivatives dz/dx and dz/dy.</p>
    <p>Slope is computed in degrees from horizontal.</p><p>See the API documentation for more information.</p></div><dl class="attributes block"><dt>See also</dt><dd><span class="cmt">
    <p><a href="http://goo.gl/JCnNP" target="_blank">Geospatial Analysis - A comprehensive guide</a> (Smit, Longley, and Goodchild)</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.StandardDeviation" target="_blank">focal.StandardDeviation</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the standard deviation of a neighborhood for a given raster. Returns a raster of TypeDouble.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>StandardDeviation does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.Sum" target="_blank">focal.Sum</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Computes the sum of values of a neighborhood for a given raster</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Sum does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.focal.TileFocalOp" target="_blank">focal.TileFocalOp</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Used to make an operation based off a focal operation that will parallelize correctly with tiled raster data.</p></div></td></tr>

</tbody>
</table>

