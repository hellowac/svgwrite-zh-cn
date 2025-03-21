Style
=====

Internal Stylesheets

.. autoclass:: svgwrite.container.Style

.. seealso:: http://www.w3.org/TR/SVG/styling.html#StyleElement

.. automethod:: svgwrite.container.Style.__init__

.. automethod:: svgwrite.container.Style.append

Best place for the *style* element is the *defs* attribute of the
:class:`~svgwrite.drawing.Drawing` class::

    drawing.defs.add(drawing.style('stylesheet-content'))

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **type** -- `string`

    默认值为 ``'text/css'``。

  * **title** -- `string`

    （为了与 HTML 4 兼容）此属性为 `style` 元素指定一个建议性的标题。

  * **media** -- `string`

    此属性指定样式信息的目标媒介。可以是单个媒介描述符或逗号分隔的列表。
    该属性的默认值为 ``'all'``。


.. tab:: 英文

  * **type** -- `string`

    default is ``'text/css'``

  * **title** -- `string`

    (For compatibility with HTML 4.) This attribute specifies an advisory
    title for the ‘style’ element.

  * **media** -- `string`

    This attribute specifies the intended destination medium for style information.
    It may be a single media descriptor or a comma-separated list.
    The default value for this attribute is ``'all'``.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
* :doc:`XLink Attributes </attributes/xlink>`
