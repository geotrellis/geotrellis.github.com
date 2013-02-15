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

Local operations also will normally provide version of the operations that will
act on single values. For example,

    val twentyfive:Op[Int] = local.Pow(5,2)
    
They will also normally provide a version that will perform a calculation of
each cell of a raster with a single value. For example,

    // Returns input cell values if they are less than 25,
    // otherwise 25.
    val maxValues:Op[Raster] = local.Max(inputRaster,25)
    
Local Operations will also provide calculations that operate on the corresponding cells 
of two or more Rasters. For example,

    //Returns the sum of each corresponding raster cell.
    val sum:Op[Raster] = local.Sum(inputRaster1, inputRaster2)

Located in [geotrellis.raster.op.local.](http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Add$" target="_blank">local.Add</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Add values. Overloads include adding integers to rasters and adding the cell values of two or more rasters.</p><div class="comment cmt"><p>Add the values of each cell in each raster.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.And$" target="_blank">local.And</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>And's a constant with each cell value of a raster, or the fcell values of two rasters together.</p></div>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>And does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.BinaryDoCell" target="_blank">local.BinaryDoCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a function on every cell in a raster with the values from another raster.</p><p>For an example, see the API documentation.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.BinaryIfCell" target="_blank">local.BinaryIfCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a condition over two rasters, set the value of each cell in the output to a specified value if the condition is true given the corresponding values in each of the two input rasters.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.BinaryIfElseCell" target="_blank">local.BinaryIfElseCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Given a condition over two rasters, set the value of each cell in the output to a specified true or false value after testing the specified condition on the corresponding values in each of the two input rasters.</p><p>See API documentation for usage.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Ceil$" target="_blank">local.Ceil</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Takes the Ceiling of each raster cell value or of a constant.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Defined$" target="_blank">local.Defined</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Maps values to 0 if the are NoData values, otherwise 1.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Divide$" target="_blank">local.Divide</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Operation for dividing raster or constant values.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.DoCell" target="_blank">local.DoCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Perform a function on every cell in a raster.</p><p>For an example see the API documentation.</p></div>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>DoCell does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Equal$" target="_blank">local.Equal</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if values are equal. In Raster applications, returns a Raster with TypeBit data that contains 1 if cell values are equal, and 0 if not.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Floor$" target="_blank">local.Floor</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Gets the Floor value for Raster cell values or constant values.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Greater$" target="_blank">local.Greater</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if one value is greater than another. Sets to 1 if true, else 0. For Rasters, returns a Raster with TypeBit data indicating per cell whether the value is greater than the corresponding value.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.GreaterOrEqual$" target="_blank">local.GreaterOrEqual</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if one value is greater than or equal to another. Sets to 1 if true, else 0. For Rasters, returns a Raster with TypeBit data indicating per cell whether the value is greater than or equal to the corresponding value.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.IfCell" target="_blank">local.IfCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Maps all cells matching <code>cond</code> to <code>trueValue</code>.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.IfElseCell" target="_blank">local.IfElseCell</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Set all values of output raster to one value or another based on whether a condition is true or false.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.InverseMask" target="_blank">local.InverseMask</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Generate a raster with the values from the first raster, but only include cells in which the corresponding cell in the second raster is set to the "readMask" value.</p>
    <p>For example, if *all* cells in the second raster are set to the readMask value, the output raster will be identical to the first raster.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Less$" target="_blank">local.Less</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if one value is less than another. Sets to 1 if true, else 0. For Raster, returns a Raster with TypeBit data indicating per cell whether the value is less than the corresponding value.</p></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.LessOrEqual$" target="_blank">local.LessOrEqual</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if one value is greater than or equal to another. Sets to 1 if true, else 0. For Rasters, returns a Raster with TypeBit data indicating per cell whether the value is greater than or equal to the corresponding value.</p></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Log$" target="_blank">local.Log</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Computes the Log of Raster or single values.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Mask" target="_blank">local.Mask</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Generate a raster with the values from the first raster, but only include cells in which the corresponding cell in the second raster *are not* set to the "readMask" value.</p>
    <p>For example, if *all* cells in the second raster are set to the readMask value, the output raster will be empty -- all values set to NODATA.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Max$" target="_blank">local.Max</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Get maximum values of Raster or constant values.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Max does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Min$" target="_blank">local.Min</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Takes the Min of Ints and integer typed Rasters.</p></div>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Min does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Multiply$" target="_blank">local.Multiply</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p> Multiplies values of Rasters or constants.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Negate" target="_blank">local.Negate</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Negate (multiply by -1) each value in a raster.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Not$" target="_blank">local.Not</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Bitwise negation of Raster or constant values.</p></div>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Not does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Or$" target="_blank">local.Or</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Performs a Bitwise OR operation on values.</p>
    <dl class="attributes block"><dt>Note</dt><dd><span class="cmt"><p>Or does not currently support Double raster data. If you use a Raster with a Double RasterType (TypeFloat,TypeDouble) the data values will be rounded to integers.</p></span></dd></dl></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Pow$" target="_blank">local.Pow</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Raises values to the given power.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Round$" target="_blank">local.Round</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Round values to the nearest integer.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Sqrt$" target="_blank">local.Sqrt</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Takes the Square Root of values.</p></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Subtract$" target="_blank">local.Subtract</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Subtracts values.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.UndefinedConstant" target="_blank">local.UndefinedConstant</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Maps an integer or Raster cell values to 1 if NoData or else 0.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.Unequal$" target="_blank">local.Unequal</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Determines if values are not equal, and sets results as 1 if not equal, 0 otherwise.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.raster.op.local.XorConstant1" target="_blank">local.XorConstant1</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Xor's values together.</p></div></td></tr>

</tbody>
</table>
