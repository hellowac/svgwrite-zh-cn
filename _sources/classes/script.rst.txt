Script
======

.. tab:: 中文

  *script* 元素表示与客户端语言的链接。

.. tab:: 英文

  The *script* element indicate links to a client-side language.

.. autoclass:: svgwrite.container.Script

.. seealso:: http://www.w3.org/TR/SVG/script.html

.. automethod:: svgwrite.container.Script.__init__

.. automethod:: svgwrite.container.Script.append

Best place for the *script* element is the *defs* attribute of the :class:`~svgwrite.drawing.Drawing` class::

    drawing.defs.add(drawing.script('script-content'))

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **type** -- `string`

    指定给定 *script* 元素所使用的脚本语言。其值为符合 MIME 规范的媒体类型（content-type）。
    如果未提供 *type*，则使用 **svg** 元素上的 **contentScriptType** 作为默认值，该值默认设为 ``'application/ecmascript'``。
    如果 *script* 元素位于最外层 svg 元素之外，并且未提供 *type*，则其默认值必须为 ``'application/ecmascript'``。

  * **externalResourcesRequired** -- `bool`

    *False*：如果文档渲染可以继续进行，即使外部资源不可用；否则为 *True*。

  * **xlink:href** -- `string` -- **href** 参数。

  * **xlink:show** -- ``'new|replace'``

  * **xlink:actuate** -- ``'onRequest'``

    此属性为支持 XLink 的处理器提供文档信息，指示应用程序应仅在触发用于遍历的加载后事件时，从起始资源跳转到目标资源。


.. tab:: 英文

  * **type** -- `string`

    Identifies the scripting language for the given *script* element. The value
    content-type specifies a media type, per MIME. If a *type* is not provided,
    the value of **contentScriptType** on the **svg** element shall be used,
    which in turn defaults to ``'application/ecmascript'``. If a *script* element
    falls outside of the outermost svg element and the *type* is not provided,
    the *type* must default to ``'application/ecmascript'``

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **xlink:href** -- `string` -- **href** parameter

  * **xlink:show** -- ``'new|replace'``

  * **xlink:acuate** -- ``'onRequest'``

    This attribute provides documentation to XLink-aware processors that an
    application should traverse from the starting resource to the ending
    resource only on a post-loading event triggered for the purpose of traversal.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
* :doc:`XLink Attributes </attributes/xlink>`
