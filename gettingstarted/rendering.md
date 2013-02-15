---
layout: gettingstarted
title: Rendering Images

tutorial: gettingstarted
num: 7
outof: 9
---

#### Rendering Images from a Raster

GeoTrellis will render raster data as an image (in png format) for display
on a web map.  It's time to put on your cartographer's cap and consider
how best to represent your data on the map.

Some rasters only have a few unique values.  For example, a raster representing
a rank between 1 and 5 or a landcover raster in which each value is a different
kind of land use (e.g. 11 for water or 40 for forest).  In these cases,
it makes sense to assign each value its own color.  But when raster values
represents counts, measurements, or ratios, there are usually many distinct
values.  One common way to represent raster data visually on a map 
is to divide up the values of the data into different categories called classes,
and then represent each class on the map with its own color.  Each class has
an lower and upper limit that defines what values falls within it.  For example,
a class might contain values between 0 and 10.  We call these limits *class breaks*.

When rendering a raster in GeoTrellis, you can either use one of the automated classification schemes or manually determine the class breaks.  For example, if you were creating a map of average household income, you might want one of the classes to be defined as below the federal poverty guidelines (manual classification) or organized into several equal intervals between the minimum and maximum (using the built-in linear breaks classification scheme).

#### Classification

GeoTrellis is able to generate two types of class breaks:  quantile and linear.  
By default, GeoTrellis will create *quantile* class breaks for your raster.  
The intuitive idea of a quantile break is that there should be an equal number of 
cells in each class.  For example, if most cells in our income map have incomes
below the national average, we would generate more classes for that range of
values and only a few classes for higher income ranges, even though those
ranges will have a bigger difference between the low and high limits.  This
classification scheme is particularly good at emphasizing highlights or hotspots
where values are particularly high or low.

You can also request linear breaks (or "equal interval" breaks).  Linear breaks simply divides up the values between the lowest value and the
highest value, with the difference between the low and high limit being the
same for each class.  For example, if we want 5 linear breaks between 0 and 50,
the classes would be 0-10, 10-20, 20-30, 30-40, and 40-50.

There are other classification schemes that GeoTrellis does not currently
support, such as Natural breaks (Jenks) and Standard Deviation, but we 
intend to implement them in the future.  Let us know if you have a need.

#### Color Ramps

GeoTrellis provides a set of color ramps (a list of colors) from which to choose.  These are provided to ease the transition from developer to 
cartographer.  However, you need not feel constrained by these and can use your own color palettes as well.  There are many good resources online 
for selecting color ramps.

## Usage
    val colorRamp = ColorRamps.BlueToOrange
    val png = SimpleRenderPNG(raster, colorRamp)

#### Diverging Color Schemes

<div class="ramp">
<span class="floating"> <img  src="{{site.baseurl}}/images/01_blue-to-orange.png" /> </span>
  <h2>Blue to Orange</h2>
  <span>
    <p>An 11-step diverging color ramp from blue to gray to orange. </p> 
    <p>The gray critical class in the middle clearly shows a median or zero value. Example uses include temperature, climate, elevation, or other color ranges where it is necessary to distinguish categories with multiple hues.</p>
  </span>
</div>

<div class="ramp">
  <span class="floating">
    <img src="{{site.baseurl}}/images/03_blue-to-red.png" />  </span>
    <h2>Blue to Red</h2>

    <span>
<p>A 10-step diverging color ramp from blue to red. </p>
<p>Example uses include elections and politics, voter swing, climate or temperature, or other color ranges where it is necessary to distinguish categories with multiple hues.</p>
</span>
</div>

<div class="ramp">
  <span class="floating">
    <img src="{{site.baseurl}}/images/04_green-to-red-orange.png" /> </span>
    <h2>Green to Red-Orange</h2>
    <span>
<p>A 10-step diverging color ramp from green to red-orange.  </p>
<p>Example uses include elections and politics, voter swing, climate or temperature, or other color ranges where it is necessary to distinguish categories with multiple hues.</p>

</span>
</div>

<div class="ramp">
  <span class="floating">
    <img src="{{site.baseurl}}/images/02_green-to-orange.png" /> </span>
    <h2>Green to Orange</h2>
    <span>
<p>A 13-step diverging color ramp from green to orange. </p>
<p>Example uses include elevation, relief maps, topography, or other color ranges where it is necessary to distinguish categories with multiple hues.</p>
</span>
</div>

#### Sequential Color Schemes

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/05_light-to-dark-sunset.png" /></span>
  <h2>Light to Dark - Sunset</h2>
  <p>An 11-step sequential color ramp showing intensity from light to dark.</p>
  <p>This color ramp is perfect for showing density where it is critical to highlight very different values with bold colors at the higher, darker end of the ramp. Example uses include population density, accessibility, or ranking.</p>
</div>

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/06_light-to-dark-green.png" /></span>
  <h2>Light to Dark - Green</h2>
  <p>A basic 8-step sequential color ramp showing light to dark in shades of green.</p>
  <p>Example uses include density, ordered data, ranking, or any map where darker colors represent higher data values and lighter colors represent lower data values, generally.</p>
</div>

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/07_yellow-to-red-heatmap.png" /></span>
  <h2>Yellow to Red - Heatmap</h2>
  <p>An 8-step sequential heatmap from yellow to dark red.</p>
  <p>Great for heatmaps on a light basemap where the hottest values are more opaque or dark. Also useful for sequential color ranges where the lowest value is the median or zero value.</p>
</div>

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/08_blue-to-yellow-to-red-heatmap.png" /></span>
  <h2>Blue to Yellow to Red Spectrum - Heatmap</h2>
  <p>An 11-step heatmap from blue to yellow to red.</p>
  <p>Great for showing a wide range of values with clear differences in hue.</p>
</div>

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/09_dark-red-to-yellow-heatmap.png" /></span>
  <h2>Dark Red to Yellow-White - Heatmap</h2>
  <p>A 10-step sequential heatmap from dark red to yellow to white.</p>
  <p>Great for heatmaps where the hottest values should look more vibrant or intense.</p>
</div>

<div class="ramp">
    <span class="floating"><img src="{{site.baseurl}}/images/10_purple-to-dark-purple-to-white-heatmap.png" /></span>
  <h2>Light Purple to Dark Purple To White</h2>
  <p>An 8-step sequential heatmap to show intensity with shades of purple with white as the "hottest" value.</p>
  <p>Great for light or gray basemaps, or where the highest value needs to be called out visually.</p>
</div>

#### Qualitative or Categorical Schemes

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/11_bold-land-use-qualitative.png" /></span>
  <h2>Bold Land Use</h2>
  <p>An 8-hue qualitative scheme used to show a clear difference in categories that are unordered or very different.</p>
  <p>Example uses include zoning, land use, land cover, or maps where all categories or groups are equal in visual strength/magnitude.</p>
</div>

<div class="ramp">
  <span class="floating"><img src="{{site.baseurl}}/images/12_muted-terrain-qualitative.png" /></span>
  <h2>Muted Terrain</h2>
  <p>An 8-hue qualitative scheme used to show different kinds of map topology or features.</p>
  <p>This is generally used to show landforms, terrain, and topology.</p>
</div>

### Customizing Color Ramps

You can create your own color ramp with a list of RGB hex color values.  

    import geotrellis.data.ColorRamp

## Generate a color ramp with red (#FF0000), green (#00FF00), blue (0000FF)
    val ramp = 
        ColorRamp.createWithRGBColors(0xFF0000, 0x00FF00, 0x0000FF)

By default, GeoTrellis will generate a number of classes to match the number of
colors in the color ramp.  You can ask GeoTrellis to generate a new ramp by
generating  a requested number of new breaks using an existing color ramp as
a guide.  The first and last colors will be the first and last colors from the
existing color ramp, and the rest will be interpolated.  For example, given a 
color ramp of two colors, red and yellow, a request for 5 colors would return 
Red, Yellowish-Red, Orange, Reddish-Yellow, Yellow.  

    import geotrellis.data._
  
    ## Create a color ramp with red and yellow
    val ramp = ColorRamp.createWithRGBColors(0xFF0000, 0xFFFF00)
    val newRamp = ramp.interpolate(5)

    ## Create a 15 class ramp from an existing ramp
    val fifteenColors = ColorRamps.BlueToOrange.interpolate(15)

There are many online and offline resources for generating color palettes for cartography including:  
+ [ColorBrewer 2.0](http://colorbrewer2.org/js/)
+ [Cartographer's Toolkit: Colors, Typography, Patterns](http://www.amazon.com/Cartographers-Toolkit-Colors-Typography-Patterns/dp/0615467946), by Gretchen N. Peterson
+ [Designing Better Maps](http://www.amazon.com/Designing-Better-Maps-Guide-Users/dp/1589480899/), by Cynthia A. Brewer
+ [Designed Maps: A Sourcebook](http://www.amazon.com/Designed-Maps-Sourcebook-GIS-Users/dp/1589481607/), by Cynthia A. Brewer

See the [geotrellis.data.ColorRamp scala docs](http://geotrellis.github.com/scaladocs/0.8/#geotrellis.data.ColorRamp) for additional functionality,
including adding an alpha gradient to your color ramp.  

### RGBA vs RGB values

One way to represent a color is as an RGB hex value, as often seen in CSS or
graphics programs.  For example, the color red is represented by #FF0000
(or, in scala, 0xFF0000).

Internally to GeoTrellis, colors are represented as RGBA values, which includes
a value for transparency.  These can be represented with 8 instead of 6 hex characters
(with the alpha opacity value being the last two charcters) such as 0xFF0000FF
for opaque red.  When using the programming interface, just be sure to keep the
distinction in mind and, when using RGB values, be sure to use the utility 
methods that convert them into RGBA values (such as [ColorRamp.createWithRGBColors](http://geotrellis.github.com/scaladocs/0.8/#geotrellis.data.ColorRamp$)).
