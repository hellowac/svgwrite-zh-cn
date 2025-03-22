Line
====

.. autoclass:: svgwrite.shapes.Line

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#LineElement

.. automethod:: svgwrite.shapes.Line.__init__

SVG 属性
--------------

SVG Attributes

* **x1** -- `<coordinate>` -- **start** parameter
* **y1** -- `<coordinate>` -- **start** parameter
* **x2** -- `<coordinate>` -- **end** parameter
* **y2** -- `<coordinate>` -- **end** parameter

常见 SVG 属性
---------------------

Common SVG Attributes

.. tab:: 中文

  这些是线条、矩形、圆形、椭圆、多边形和多边形常见的 SVG 属性。

  * **class** -- `string`

    将一个或多个 CSS 类名分配给一个元素。

  * **style** -- `string`

    允许在给定元素上直接指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果即使外部资源不可用，文档渲染也能继续进行；否则为 *True*。

  * **transform** -- 使用 :class:`svgwrite.mixins.Transform` 接口。


.. tab:: 英文

  These are the common SVG Attributes for Line, Rect, Circle, Ellipse,
  Poliyline and Polygon.

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given
    element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **transform** -- use :class:`svgwrite.mixins.Transform` interface

常见标准 SVG 属性
------------------------------

Common Standard SVG Attributes

.. tab:: 中文

  这些是线、矩形、圆、椭圆、多段线和多边形的常见标准 SVG 属性。

.. tab:: 英文

  These are the common Standard SVG Attributes for Line, Rect, Circle, Ellipse,
  Poliyline and Polygon.

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`
* :class:`svgwrite.mixins.Markers`

Rect
====

.. autoclass:: svgwrite.shapes.Rect

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#RectElement

.. automethod:: svgwrite.shapes.Rect.__init__

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **x** -- `<coordinate>` -- **插入** 参数

    矩形的那一侧的 x 轴坐标，具有较小的 x 轴坐标值

  * **y** -- `<coordinate>` -- **插入** 参数

    矩形的那一侧的 y 轴坐标，具有较小的 y 轴坐标值

  * **width** -- `<length>` -- **大小** 参数

  * **height** -- `<length>` -- **大小** 参数

  * **rx** -- `<length>` -- **rx** 参数

    对于圆角矩形，用于圆化矩形角落的椭圆的 y 轴半径。

  * **ry** -- `<length>` -- **ry** 参数

    对于圆角矩形，用于圆化矩形角落的椭圆的 y 轴半径。

.. tab:: 英文


  * **x** -- `<coordinate>` -- **insert** parameter

    The x-axis coordinate of the side of the
    rectangle which has the smaller x-axis coordinate value

  * **y** -- `<coordinate>` -- **insert** parameter

    The y-axis coordinate of the side of the
    rectangle which has the smaller y-axis coordinate value

  * **width** -- `<length>` -- **size** parameter

  * **height** -- `<length>` -- **size** parameter

  * **rx** -- `<length>` -- **rx** parameter

    For rounded rectangles, the y-axis radius of the
    ellipse used to round off the corners of the rectangle.

  * **ry** -- `<length>` -- **ry** parameter

    For rounded rectangles, the y-axis radius of the
    ellipse used to round off the corners of the rectangle.


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`

Circle
======

.. autoclass:: svgwrite.shapes.Circle

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#CircleElement

.. automethod:: svgwrite.shapes.Circle.__init__

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **cx** -- `<coordinate>` -- **中心** 参数

    圆心的 x 轴坐标。

  * **cy** -- `<coordinate>` -- **中心** 参数

    圆心的 y 轴坐标。

  * **r** -- `<length>` -- **r** 参数

    圆的半径。

.. tab:: 英文


  * **cx** -- `<coordinate>` -- **center** parameter

    The x-axis coordinate of the center of the circle.

  * **cy** -- `<coordinate>` -- **center** parameter

    The y-axis coordinate of the center of the circle.

  * **r** -- `<length>` -- **r** parameter

    The radius of the circle.


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`

Ellipse
=======

.. autoclass:: svgwrite.shapes.Ellipse

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#EllipseElement

.. automethod:: svgwrite.shapes.Ellipse.__init__

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **cx** -- `<coordinate>` -- **中心** 参数

    椭圆的圆心的 x 轴坐标。

  * **cy** -- `<coordinate>` -- **中心** 参数

    椭圆的圆心的 y 轴坐标。

  * **rx** -- `<length>` -- **r** 参数

    椭圆的 x 轴半径。

  * **ry** -- `<length>` -- **r** 参数

    椭圆的 y 轴半径。

.. tab:: 英文


  * **cx** -- `<coordinate>` -- **center** parameter

    The x-axis coordinate of the center of the ellipse.

  * **cy** -- `<coordinate>` -- **center** parameter

    The y-axis coordinate of the center of the ellipse.

  * **rx** -- `<length>` -- **r** parameter

    The x-axis radius of the ellipse.

  * **ry** -- `<length>` -- **r** parameter

    The y-axis radius of the ellipse.


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`

Polyline
========

.. autoclass:: svgwrite.shapes.Polyline

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#PolylineElement

.. automethod:: svgwrite.shapes.Polyline.__init__

属性
----------

Attributes

.. attribute:: Polyline.points

.. tab:: 中文

  点的 `list`，一个点是一个 `2-tuple` (x, y): x, y = `<number>`

.. tab:: 英文

  `list` of points, a point is a `2-tuple` (x, y): x, y = `<number>`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **points** -- `list` of points  -- **points** 参数

    构成折线的点。所有坐标值都在 **用户坐标系统** 中（不允许使用单位）。

  如何追加点::  

      Polyline.points.append( point )  
      Polyline.points.extend( [point1, point2, point3, ...] )

.. tab:: 英文


  * **points** -- `list` of points  -- **points** parameter

    The points that make up the polyline. All coordinate values are in the
    **user coordinate system** (no units allowed).

  How to append points::

      Polyline.points.append( point )
      Polyline.points.extend( [point1, point2, point3, ...] )


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`
* :class:`svgwrite.mixins.Markers`

Polygon
=======

.. autoclass:: svgwrite.shapes.Polygon

.. seealso:: http://www.w3.org/TR/SVG11/shapes.html#PolygonElement


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`
* :class:`svgwrite.mixins.Markers`

Basic Shapes Examples
=====================

.. literalinclude:: ../../examples/basic_shapes.py
   :lines: 16-

basic_shapes.svg
----------------

.. image:: ../../examples/basic_shapes.svg
   :width: 800
   :height: 800
   :alt: Your browser can't render SVG images.