Marker
======

.. autoclass:: svgwrite.container.Marker

.. seealso:: http://www.w3.org/TR/SVG11/painting.html#MarkerElement

.. tab:: 中文

  示例::

      dwg = svgwrite.Drawing()
      # 创建一个新的 marker 对象
      marker = dwg.marker(insert=(5,5), size=(10,10))

      # 作为标记的红色点
      marker.add(dwg.circle((5, 5), r=5, fill='red'))

      # 将标记添加到绘图的 defs 部分
      dwg.defs.add(marker)

      # 创建一个新的折线对象
      line = dwg.add(dwg.polyline(
          [(10, 10), (50, 20), (70, 50), (100, 30)],
          stroke='black', fill='none'))

      # 设置标记（起点、中间点和终点标记相同）
      line.set_markers(marker)

      # 或者直接将标记设置为 SVG 属性 'marker-start'、'marker-mid'、
      # 'marker-end' 或 'marker'（如果所有标记相同）。
      line['marker'] = marker.get_funciri()

      # 1.1.11 版新增功能
      # 通过单独设置标记，仅设置终点标记时，可将其他标记设为 None 或 False：
      line.set_markers((None, False, marker))


.. tab:: 英文

  example::

      dwg = svgwrite.Drawing()
      # create a new marker object
      marker = dwg.marker(insert=(5,5), size=(10,10))

      # red point as marker
      marker.add(dwg.circle((5, 5), r=5, fill='red'))

      # add marker to defs section of the drawing
      dwg.defs.add(marker)

      # create a new line object
      line = dwg.add(dwg.polyline(
          [(10, 10), (50, 20), (70, 50), (100, 30)],
          stroke='black', fill='none'))

      # set marker (start, mid and end markers are the same)
      line.set_markers(marker)

      # or set markers direct as SVG Attributes 'marker-start', 'marker-mid',
      # 'marker-end' or 'marker' if all markers are the same.
      line['marker'] = marker.get_funciri()

      # NEW in v1.1.11
      # set individually markers, to just set the end marker set other markers to None or False:
      line.set_markers((None, False, marker))

.. automethod:: svgwrite.container.Marker.__init__

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.ViewBox`
* :class:`svgwrite.mixins.Presentation`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接在指定元素上定义每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果文档渲染可以继续进行，即使外部资源不可用；否则为 *True*。

  * **viewBox** -- 使用 :class:`svgwrite.mixins.ViewBox` 接口。

  * **preserveAspectRatio** -- 使用 :class:`svgwrite.mixins.ViewBox` 接口。

  * **markerUnits** -- ``'strokeWidth|userSpaceOnUse'``

    定义 **markerWidth**、**markerHeight** 属性及 **marker** 内容的坐标系统。

    如果 markerUnits 为 ``'strokeWidth'``，则 **markerWidth**、**markerHeight** 和 **marker** 的内容在一个坐标系统中，该系统的单位等于当前参考该标记的图形对象的笔画宽度的用户单位大小。

    如果 markerUnits 为 ``'userSpaceOnUse'``，则 **markerWidth**、**markerHeight** 和 **marker** 的内容在当前用户坐标系统中，该系统适用于引用该 **marker** 的图形对象（即，引用 **marker**、**marker-start**、**marker-mid** 或 **marker-end** 属性的元素的用户坐标系统）。

  * **refX** -- `<coordinate>` -- **插入** 参数

    需要精确对齐到标记位置的参考点的 x 轴坐标。该坐标在应用 **viewBox** 和 **preserveAspectRatio** 属性后定义的坐标系统中表示。

    （默认值 = "0"）

  * **refY** -- `<coordinate>` -- **插入** 参数

    需要精确对齐到标记位置的参考点的 y 轴坐标。该坐标在应用 **viewBox** 和 **preserveAspectRatio** 属性后定义的坐标系统中表示。

    （默认值 = "0"）

  * **markerWidth** -- `<length>` -- **尺寸** 参数

    代表渲染标记时用于适配标记的视口宽度。

    （默认值 = "3"）

  * **markerHeight** -- `<length>` -- **尺寸** 参数

    代表渲染标记时用于适配标记的视口高度。值为零时，将禁用该元素的渲染。

    （默认值 = "3"）

  * **orient** -- ``'auto'`` | `<angle>` -- **方向** 参数

    指定标记的旋转方式。（SVG 默认值为 "0"，但对于 :meth:`__init__`，默认值为 ``'auto'``）


.. tab:: 英文


  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given
    element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **viewBox** -- use :class:`svgwrite.mixins.ViewBox` interface

  * **preserveAspectRatio** -- use :class:`svgwrite.mixins.ViewBox`
    interface

  * **markerUnits** -- ``'strokeWidth|userSpaceOnUse'``

    Defines the coordinate system for attributes **markerWidth**, **markerHeight**
    and the contents of the **marker**.

    If markerUnits -- ``'strokeWidth'``, **markerWidth**,
    **markerHeight** and the contents of the **marker** represent values in a coordinate
    system which has a single unit equal the size in user units of the current
    stroke width in place for the graphic object referencing the marker.

    If markerUnits -- ``'userSpaceOnUse'``, **markerWidth**, **markerHeight** and the
    contents of the **marker** represent values in the current user coordinate
    system in place for the graphic object referencing the marker (i.e., the
    user coordinate system for the element referencing the **marker** element via
    a **marker**, **marker-start**, **marker-mid** or **marker-end** property).

  * **refX** -- `<coordinate>` -- **insert** parameter

    The x-axis coordinate of the reference point which is to be aligned exactly
    at the marker position. The coordinate is defined in the coordinate system
    after application of the **viewBox** and **preserveAspectRatio** attributes.
    (default = "0")

  * **refY** -- `<coordinate>` -- **insert** parameter

    The y-axis coordinate of the reference point which is to be aligned exactly
    at the marker position. The coordinate is defined in the coordinate system
    after application of the **viewBox** and **preserveAspectRatio** attributes.
    (default = "0")

  * **markerWidth** -- `<length>` -- **size** parameter

    Represents the width of the viewport into which the marker is to be fitted
    when it is rendered. (default = "3")

  * **markerHeight** -- `<length>` -- **size** parameter

    Represents the height of the viewport into which the marker is to be fitted
    when it is rendered. A value of zero disables rendering of the element.
    (default = "3")

  * **orient** -- ``'auto'`` | `<angle>` -- **orient** parameter

    Indicates how the marker is rotated. (SVG default = "0", but for :meth:`__init__`
    ``'auto'`` is the default value)

  .. seealso:: http://www.w3.org/TR/SVG11/painting.html#OrientAttribute

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Presentation Attributes </attributes/presentation>`
