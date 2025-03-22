Hyperlink
=========

.. tab:: 中文

  **Hyperlink** 类代表 SVG **a** 元素。

.. tab:: 英文

  The **Hyperlink** class represents the SVG **a** element.

.. autoclass:: svgwrite.container.Hyperlink

.. seealso:: http://www.w3.org/TR/SVG11/linking.html#AElement

.. automethod:: svgwrite.container.Hyperlink.__init__

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
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

  * **transform** -- 使用 :class:`svgwrite.mixins.Transform` 接口。

  * **xlink:href** -- `string` -- **href** 参数。

  * **xlink:show** -- ``'new|replace'``

    使用 **target** 属性。

  * **xlink:actuate** -- ``'onRequest'``

    此属性为支持 XLink 的处理器提供文档信息，指示应用程序应仅在触发用于遍历的加载后事件时，从起始资源跳转到目标资源。

  * **target** -- `string` -- **target** 参数。

    此属性指定目标窗口、框架、面板、标签页或其他相关显示上下文（例如 HTML 或 XHTML 的 `frame`、`iframe` 或 `object` 元素）中的名称或部分，以便在链接激活时打开文档。

    - ``_replace``：当前 SVG 图像在相同的矩形区域内被链接内容替换，且位于相同的框架中。
    - ``_self``：当前 SVG 图像在相同的框架内被链接内容替换。如果未指定 **target** 属性，则该值为默认值。
    - ``_parent``：当前 SVG 图像的直接父框架集被链接内容替换。
    - ``_top``：整个窗口或标签页的内容（包括任何框架）被链接内容替换。
    - ``_blank``：请求在一个新的未命名窗口或标签页中显示链接内容。如果失败，则效果与 ``_top`` 相同。
    - ``<XML-Name>``：指定用于显示链接内容的框架、面板或其他相关显示上下文的名称。如果该名称已存在，则复用该窗口并替换其内容；如果不存在，则创建新的窗口（类似于 ``_blank``，但该窗口具有指定的名称）。


.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given
    element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **transform** -- use :class:`svgwrite.mixins.Transform` interface

  * **xlink:href** -- `string` -- **href** parameter

  * **xlink:show** -- ``'new|replace'``

    use the **target** attribute

  * **xlink:acuate** -- ``'onRequest'``

    This attribute provides documentation to XLink-aware processors that an
    application should traverse from the starting resource to the ending
    resource only on a post-loading event triggered for the purpose of traversal.

  * **target** -- `string` -- **target** parameter

    This attribute specifies the name or portion of
    the target window, frame, pane, tab, or other relevant presentation
    context (e.g., an HTML or XHTML frame, iframe, or object element)
    into which a document is to be opened when the link is activated.

    - ``_replace``: The current SVG image is replaced by the linked
      content in the same rectangular area in the same frame as the
      current SVG image.
    - ``_self``: The current SVG image is replaced by the linked content
      in the same frame as the current SVG image. This is the lacuna
      value, if the target attribute is not specified.
    - ``_parent``: The immediate frameset parent of the SVG image is
      replaced by the linked content.
    - ``_top``: The content of the full window or tab, including any
      frames, is replaced by the linked content
    - ``_blank``: A new un-named window or tab is requested for the
      display of the linked content. If this fails, the result is the
      same as ``_top``
    - ``<XML-Name>``: Specifies the name of the frame, pane, or other
      relevant presentation context for display of the linked content.
      If this already exists, it is re-used, replacing the existing
      content. If it does not exist, it is created (the same as ``_blank``,
      except that it now has a name).

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
* :doc:`XLink Attributes </attributes/xlink>`
