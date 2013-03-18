---
layout: overviews
title: Vector Operations

tutorial: overviews
num: 2
outof: 6
---

#### Vector Operations

GeoTrellis provides a full suite of vector operations in the
[geotrellis.feature.op](http://geotrellis.github.com/scaladocs/0.8/#geotrellis.feature.op.geometry.package)
package. Most of the vector operations that we provide use
[JTS](http://www.vividsolutions.com/jts/jtshome.htm) under the hood
to provide fast and correct vector results.

For instance, simplifying and clipping an extent can be done all within
the context of an operation

    val stateOfNewJersey:Op[Geometry[_]] = ...
    val bbox:Op[Geometry[_]] = ...

    val simplifiedState:Op[Geometry[_]] =
        geometry.Simplify(stateOfNewJersey, 10.0)

    val relevantSection:Op[Geometry[_]] =
        geometry.Intersect(simplifiedState, bbox)

    val sqMetersOfJerseyInBbox:Op[Double] =
        geometry.GetArea(relevantSection)

#### Working with Extents as Vectors

When working with data it can often be useful to perform vector
operations on extents. One very common operations is buffered a given
extent to make sure that data isn't being clipped

    val extent:Op[Extent] = ParseExtent(extentParam)
    val extentFt:Op[Feature[_]] = logic.Do(extent)(_.asFeature)

    val bufFt:Op[Feature[_]] = geometry.Buffer(
         extentFt, 50.0, 8, geometry.EndCapSquare)

    val bufExt:Op[Extent] = logic.Do(extentFt)

#### Creating Your Own Vector Operations

If an operation that you want to use isn't yet exposed by the GeoTrellis
API adding a new one is as simple as extending and operation class:

    case class GetInteriorPoint[A](g: Geometry[A])
        extends Op1[Geometry[A], Point[A](geom =>
           geom.mapGeom(_.getInteriorPoint()))

    val geom:Op[Geometry[Int]] = ...
    val pt:Op[Point[Int]] = GetInteriorPoint(geom)
