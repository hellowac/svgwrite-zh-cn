Symbol
======

.. autoclass:: svgwrite.container.Symbol

.. seealso:: http://www.w3.org/TR/SVG11/struct.html#SymbolElement

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.ViewBox`
* :class:`svgwrite.mixins.Presentation`
* :class:`svgwrite.mixins.Clipping`

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


.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are unavailable else: *True*

  * **viewBox** -- use :class:`svgwrite.mixins.ViewBox` interface

  * **preserveAspectRatio** -- use :class:`svgwrite.mixins.ViewBox` interface

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
