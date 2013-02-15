---
layout: operations
title: Statistics

tutorial: operations
num: 11
---

#### Statistics operations

Operations for computing statistics from geographic and non-geographic data. [Scala package geotrellis.statistics.op.stat.](http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetClassBreaks" target="_blank">stat.GetClassBreaks</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Generate quantile class breaks for a given raster.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetColorBreaks" target="_blank">stat.GetColorBreaks</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Generate quantile class breaks with assigned colors.</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetColorsFromPalette" target="_blank">stat.GetColorsFromPalette</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Creates a range of colors interpolated from a smaller set of colors.</p></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetDoubleHistogram" target="_blank">stat.GetDoubleHistogram</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Create a histogram from double values in a raster.</p><p>FastMapHistogram only works with integer values, which is great for performance but means that, in order to use FastMapHistogram with double values, each value must be multiplied by a power of ten to preserve significant fractional digits.</p>
    <p>For example, if you want to save one significant digit (2.1 from 2.123), set sigificantDigits to 1, and the histogram will save 2.1 as "21" by multiplying each value by 10.  The multiplier is 10 raised to the power of significant digits (e.g. 1 digit: 10, 2 digits: 100, and so on).</p>
    <p>Important: Be sure that the maximum value in the rater multiplied by 10 ^ significantDigits does not overflow Int.MaxValue (2,147,483,647).</p></div></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetHistogramArray" target="_blank">stat.GetHistogramArray</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Implements a histogram in terms of an array of the given size.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Rasters with a double type (TypeFloat,TypeDouble) will have their values rounded to integers when making the Histogram.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetHistogramMap" target="_blank">stat.GetHistogramMap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Implements a histogram in terms of a map.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Rasters with a double type (TypeFloat,TypeDouble) will have their values rounded to integers when making the Histogram.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetMinMax" target="_blank">stat.GetMinMax</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Find the minimum and maximum value of a raster.</p></div><dl class="attributes block"><dt>Note</dt><dd><span class="cmt">
    <p>Currently does not support finding double Min and Max values. If used with a raster with a double data type (TypeFloat,TypeDouble), will find the integer min and max of the rounded cell values.</p></span></dd></dl></div></td></tr>
    
<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetStandardDeviation" target="_blank">stat.GetStandardDeviation</a></code></td><td><div id="comment" class="fullcommenttop">
    <p>Calculate a raster in which each value is set to the standard deviation of that cell's value.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/scaladocs/latest/#geotrellis.statistics.op.stat.GetStatistics" target="_blank">stat.GetStatistics</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt">
    <p>Determine statistical data for the given histogram.</p>
    <p>This includes mean, median, mode, stddev, and min and max values.</p></div></div></td></tr>

</tbody>
</table>
