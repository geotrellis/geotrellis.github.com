---
layout: operations
title: Vector

tutorial: operations
num: 8
---

#### Vector (Feature) Operations

Feature Operations. See [the JTS documentation on Geometry](http://tsusiatsoftware.net/jts/javadoc/com/vividsolutions/jts/geom/Geometry.html).

Located in [geotrellis.feature.op.geometry.](http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.AsPolygonSet" targe="_blank">AsPolygonSet</a></code></td><td><p>Returns a Geometry as a Polygon Set.</p></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Buffer" targe="_blank">Buffer</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes a buffer area around this geometry.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.BufferWithParameters" targe="_blank">BufferWithParameters</a></code></td><td><div id="comment" class="fullcommenttop"><p>Computes a buffer area around with geometry based on specified buffer parameters.</p></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Contains" targe="_blank">Contains</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry contains another.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.ConvexHull" targe="_blank">ConvexHull</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the convex hull of this geometry, which is the smallest polygon that contains it.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Covers" targe="_blank">Covers</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry covers another.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Disjoint" targe="_blank">Disjoint</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if two geometries are disjoint.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Equals" targe="_blank">Equals</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry equals another.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Erase" targe="_blank">Erase</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry that contains the points in the first geometry that aren't in the second geometry.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.FlattenGeometry" targe="_blank">FlattenGeometry</a></code></td><td><p>Given a Geometry object, inspect the underlying geometry type and recursively flatten it if it is a GeometryCollection</p></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.FilterGeometry" targe="_blank">FilterGeometry</a></code></td><td><p>Given list of geometries, inspect the underlying geometry type, selecting only geometries that match the given type.</p></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.GetArea" targe="_blank">GetArea</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the area of a geometry.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.GetCentroid" targe="_blank">GetCentroid</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.GetDistance" targe="_blank">GetDistance</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the minimum distance between these two geometries.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.GetEnvelope" targe="_blank">GetEnvelope</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Computes the centroid of this geometry.
</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.GetSymDifference" targe="_blank">GetSymDifference</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns a geometry defined by the points that are in one of the two geometries
but not the other.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Intersects" targe="_blank">Intersects</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry intersects another.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Intersect" targe="_blank">Intersect</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the intersection of these geometries.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Overlaps" targe="_blank">Overlaps</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Tests if one geometry overlaps another.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Simplify" targe="_blank">Simplify</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Simplify a polygon or multipolygon.</p><p>This operation uses a topology preserving simplifier that ensures the result has the same characteristics as the input.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.feature.op.geometry.Union" targe="_blank">Union</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Returns the union of these geometries.</p></div></div></td></tr>

</tbody>
</table>
