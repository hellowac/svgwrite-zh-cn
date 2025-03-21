SVG
===

.. autoclass:: svgwrite.container.SVG

.. seealso:: http://www.w3.org/TR/SVG11/struct.html#SVGElement

.. automethod:: svgwrite.container.SVG.__init__
.. automethod:: svgwrite.container.SVG.embed_stylesheet
.. automethod:: svgwrite.container.SVG.embed_font
.. automethod:: svgwrite.container.SVG.embed_google_web_font

属性
----------

Attributes

.. attribute:: SVG.defs

  .. tab:: 中文

    引用元素的 `Defs` 容器

    将 SVG 元素添加到 *defs*::

      svgobject.defs.add(element)

  .. tab:: 英文

    `Defs` container for referenced elements

    adding SVG elements to *defs*::

      svgobject.defs.add(element)


父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.container.Symbol`
* :class:`svgwrite.container.SVG`
* :class:`svgwrite.mixins.Transform`
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

  * **transform** -- 使用 :class:`svgwrite.mixins.Transform` 接口。

  * **x** -- `<coordinate>` -- **插入** 参数

    （对 :class:`~svgwrite.drawing.Drawing` 无意义或无影响。）

    矩形区域的一个角的 x 轴坐标，该区域用于放置嵌入的 **svg** 元素。

    默认值为 ``'0'``。

  * **y** -- `<coordinate>` -- **插入** 参数

    （对 :class:`~svgwrite.drawing.Drawing` 无意义或无影响。）

    矩形区域的一个角的 y 轴坐标，该区域用于放置嵌入的 **svg** 元素。

    默认值为 ``'0'``。

  * **width** -- `<length>` -- **尺寸** 参数

    对于最外层的 **svg** 元素（:class:`~svgwrite.drawing.Drawing`），表示 SVG 文档片段的内在宽度。
    对于嵌入的 **svg** 元素，表示 **svg** 元素被放置的矩形区域的宽度。

    负值是错误的。值为零时，将禁用该元素的渲染。

    默认值为 ``'100%'``。

  * **height** -- `<length>` -- **尺寸** 参数

    对于最外层的 **svg** 元素（:class:`~svgwrite.drawing.Drawing`），表示 SVG 文档片段的内在高度。
    对于嵌入的 **svg** 元素，表示 **svg** 元素被放置的矩形区域的高度。

    负值是错误的。值为零时，将禁用该元素的渲染。

    默认值为 ``'100%'``。

  * **viewBox** -- :class:`svgwrite.mixins.ViewBox` 接口。

  * **preserveAspectRatio**  -- :class:`svgwrite.mixins.ViewBox` 接口。

  * **zoomAndPan** -- ``'disable | magnify'``

    默认值为 ``'magnify'``。

  .. note::
    
    请勿设置或更改以下 SVG 属性：
    version、baseProfile、contentScriptType、contentStyleType。

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

  * **x** -- `<coordinate>` -- **insert** parameter

    (Has no meaning or effect on :class:`~svgwrite.drawing.Drawing` .)

    The x-axis coordinate of one corner of the rectangular region into which an
    embedded **svg** element is placed.

    Default is ``'0'``.

  * **y** -- `<coordinate>` -- **insert** parameter

    (Has no meaning or effect on :class:`~svgwrite.drawing.Drawing` .)

    The y-axis coordinate of one corner of the rectangular region into which an
    embedded **svg** element is placed.

    Default is ``'0'``.

  * **width** -- `<length>` -- **size** parameter

    For outermost **svg** elements (:class:`~svgwrite.drawing.Drawing`), the
    intrinsic width of the SVG document fragment. For embedded **svg** elements,
    the width of the rectangular region into which the **svg** element is placed.

    A negative value is an error. A value of zero disables rendering of the element.

    Default is ``'100%'``.

  * **height** -- `<length>` -- **size** parameter

    For outermost **svg** elements (:class:`~svgwrite.drawing.Drawing`), the
    intrinsic height of the SVG document fragment. For embedded **svg** elements,
    the height of the rectangular region into which the **svg** element is placed.

    A negative value is an error. A value of zero disables rendering of the element.

    Default is ``'100%'``.

  * **viewBox** -- :class:`svgwrite.mixins.ViewBox` interface

  * **preserveAspectRatio**  -- :class:`svgwrite.mixins.ViewBox` interface

  * **zoomAndPan** -- ``'disable | magnify'``

    Default is ``'magnify'``.

  .. note::
    do not set or change following SVG attributes:
    version, baseProfile, contentScriptType, contentStyleType

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Document Event Attributes </attributes/document_event>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
