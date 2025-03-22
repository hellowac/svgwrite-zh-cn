Use
===

.. autoclass:: svgwrite.container.Use

.. seealso:: http://www.w3.org/TR/SVG11/struct.html#UseElement

.. automethod:: svgwrite.container.Use.__init__

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.XLink`
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

  * **x** -- `<coordinate>` -- **插入** 参数

    被引用元素放置的矩形区域的一个角的 x 轴坐标。

    默认值为 ``'0'``。

  * **y** -- `<coordinate>` -- **插入** 参数

    被引用元素放置的矩形区域的一个角的 y 轴坐标。

    默认值为 ``'0'``。

  * **width** -- `<length>` -- **尺寸** 参数

    被引用元素放置的矩形区域的宽度。负值无效，零值将禁用该元素的渲染。

    默认值为 ``'100%'``。

  * **height** -- `<length>` -- **尺寸** 参数

    被引用元素放置的矩形区域的高度。负值无效，零值将禁用该元素的渲染。

    默认值为 ``'100%'``。

  * **transform** -- :class:`svgwrite.mixins.Transform` 接口。

  * **xlink:href** -- `string` -- **href** 参数

    在 `__init__(href)` 中设置。


.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are unavailable else: *True*

  * **x** -- `<coordinate>` -- **insert** parameter

    The x-axis coordinate of one corner of the rectangular region into which the referenced element is placed.

    Default is ``'0'``.

  * **y** -- `<coordinate>` -- **insert** parameter

    The y-axis coordinate of one corner of the rectangular region into which the referenced element is placed.

    Default is ``'0'``.

  * **width** -- `<length>` -- **size** parameter

    The width of the rectangular region into which the referenced element is placed. A negative value is an error. A value of zero disables rendering of this element.

    Default is ``'100%'``.

  * **height** -- `<length>` -- **size** parameter

    The height of the rectangular region into which the referenced element is placed. A negative value is an error. A value of zero disables rendering of this element.

    Default is ``'100%'``.

  * **transform** -- :class:`svgwrite.mixins.Transform` interface

  * **xlink:href** -- `string` -- **href** parameter

    set on __init__(href)

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
* :doc:`XLink Attributes </attributes/xlink>`
