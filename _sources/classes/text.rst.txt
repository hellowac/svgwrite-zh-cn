Text
====

.. automodule:: svgwrite.text

.. autoclass:: svgwrite.text.Text

.. seealso:: http://www.w3.org/TR/SVG11/text.html#TextElement

Refer to **TSpan** SVG Attributes

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.text.TSpan`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`

TSpan
=====

.. autoclass:: svgwrite.text.TSpan

.. seealso:: http://www.w3.org/TR/SVG11/text.html#TSpanElement

.. automethod::  svgwrite.text.TSpan.__init__

属性
----------

Attributes

.. attribute:: TSpan.text

   stores the text value.

方法
-------

Methods

.. automethod:: svgwrite.text.TSpan.__init__

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Presentation`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **x** -- `<coordinate+>`

    如果提供了单个 `<coordinate>`，则该值表示当前文本位置的新的绝对 X 坐标，用于渲染与此元素或其任何后代中的第一个字符相对应的字形。

    如果提供了 n 个 `<coordinates>` 的 `list`，则这些值表示当前文本位置的新的绝对 X 坐标，用于渲染与此元素或其任何后代中的前 n 个字符相对应的字形。

    如果提供的 `<coordinates>` 数量超过字符数，则额外的 `<coordinates>` 对字形位置不会产生影响。

    如果字符数超过 `<coordinates>` 的数量，则对于每个额外的字符：

    (a) 如果祖先 **Text** 或 **TSpan** 元素通过 **x** 属性为给定字符指定了绝对 X 坐标，则使用该绝对 X 坐标作为该字符的起始 X 坐标（最近的祖先优先），否则

    (b) 渲染与给定字符相对应的字形的起始 X 坐标是当前 **Text** 元素中最近渲染的字形所得到的当前文本位置的 X 坐标。

    如果未指定该属性：

    (a) 如果祖先 **Text** 或 **TSpan** 元素通过 **x** 属性为给定字符指定了绝对 X 坐标，则使用该绝对 X 坐标（最近的祖先优先），否则

    (b) 渲染与给定字符相对应的字形的起始 X 坐标是当前 **Text** 元素中最近渲染的字形所得到的当前文本位置的 X 坐标。

  * **y** -- `<coordinate+>`

    对应的绝对 Y 坐标列表，用于该元素中字符的字形。**y** 属性的处理规则与 **x** 属性的处理规则相同。

  * **dx** -- `<length+>`

    如果提供了单个 `<length>`，则该值表示当前文本位置的新的相对 X 坐标，用于渲染与此元素或其任何后代中的第一个字符相对应的字形。在渲染第一个字符的字形之前，当前文本位置将在当前用户坐标系的 x 轴上按 `<length>` 移动。

    如果提供了 n 个 `<length>` 的 `list`，则这些值表示渲染与此元素或其任何后代中的前 n 个字符相对应的字形之前，当前文本位置在 x 轴上的增量位移。因此，在渲染每个字符的字形之前，当前文本位置会按 `<length>` 在当前 **Text** 元素中前一个字符的字形渲染结果沿 x 轴偏移。

    如果提供的 `<lengths>` 数量超过字符数，则额外的 `<lengths>` 对字形位置不会产生影响。

    如果字符数超过 `<lengths>` 数量，则对于每个额外的字符：

    (a) 如果祖先 **Text** 或 **TSpan** 元素通过 **dx** 属性为给定字符指定了相对 X 坐标，则当前文本位置会沿当前用户坐标系的 x 轴按该值移动（最近的祖先优先），否则

    (b) 不会沿 x 轴进行额外的位移。

    如果未指定该属性：

    (a) 如果祖先 **Text** 或 **TSpan** 元素通过 **dx** 属性为给定字符指定了相对 X 坐标，则当前文本位置会沿当前用户坐标系的 x 轴按该值移动（最近的祖先优先），否则

    (b) 不会沿 x 轴进行额外的位移。

  * **dy** -- `<length+>`

    对应的相对 Y 坐标列表，用于 **tspan** 元素中的字符。**dy** 属性的处理规则与 **dx** 属性的处理规则相同。

  * **rotate** -- `<angle+>`

    在当前文本位置应用的附加旋转，将作用于该元素中每个字符的字形。

    如果提供了 `<numbers>` 的 `list`，则第一个 `<number>` 表示与此元素或其任何后代中的第一个字符相对应的字形的附加旋转，第二个 `<number>` 表示与第二个字符相对应的附加旋转，依此类推。

    如果提供的 `<numbers>` 数量超过字符数，则额外的 `<numbers>` 将被忽略。

    如果字符数超过 `<numbers>` 数量，则对于每个额外的字符，必须使用最后一个数值指定的旋转值。

    如果未指定该属性，并且祖先 **Text** 或 **TSpan** 元素通过 **rotate** 属性为给定字符指定了附加旋转，则对该字符应用给定的附加旋转（最近的祖先优先）。如果字符数超过祖先的 **rotate** 属性中指定的 `<numbers>` 数量，则对于每个额外的字符，必须使用最后一个数值指定的旋转值。

    此附加旋转对当前文本位置的修改规则没有影响，作为文本路径上的旋转以及 **glyph-orientation-horizontal** 或 **glyph-orientation-vertical** 的补充。

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接在给定元素上指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果即使外部资源不可用，文档渲染仍然可以继续，反之为 *True*。

  * **textLength** -- `<length>`

    此属性的目的是允许作者在视觉渲染顺序（经过双向重排后）中精确对齐与此元素相对应的第一个和最后一个渲染的字形；因此，对于最后渲染的字符（在视觉渲染顺序中，经过双向重排后），超出正常字形进展的额外字符间距在用户代理确定适当的文本字符串扩展/压缩以适应 **textLength** 长度时将被忽略（在大多数情况下）。

  * **lengthAdjust** -- `'spacing | spacingAndGlyphs'`

    指示用户代理应采取哪种类型的调整，以使渲染后的文本长度与 **textLength** 属性中指定的值匹配。

    * `'spacing'` 表示仅调整字形的进展值。字形本身不会被拉伸或压缩。

    * `'spacingAndGlyphs'` 表示调整进展值，并且字形本身会在一个轴（即沿着行进方向）上被拉伸或压缩。

    如果未指定该属性，则效果等同于指定了 *spacing* 值。

.. tab:: 英文


  * **x** -- `<coordinate+>`

    If a single `<coordinate>` is provided, then the value represents the new
    absolute X coordinate for the current text position for rendering the
    glyphs that correspond to the first character within this element or
    any of its descendants.

    If `list` of n `<coordinates>` is provided, then the values represent
    new absolute X coordinates for the current text position for rendering
    the glyphs corresponding to each of the first n characters within this
    element or any of its descendants.

    If more `<coordinates>` are provided than characters, then the extra
    `<coordinates>` will have no effect on glyph positioning.

    If more characters exist than `<coordinates>` , then for each of these
    extra characters:

      (a) if an ancestor **Text** or **TSpan**
          element specifies an absolute X coordinate for the given
          character via an **x** attribute, then that absolute X
          coordinate is used as the starting X coordinate for that
          character (nearest ancestor has precedence), else

      (b) the starting X coordinate for rendering the glyphs corresponding
          to the given character is the X coordinate of the resulting
          current text position from the most recently rendered glyph for
          the current **Text** element.

    If the attribute is not specified:

      (a) if an ancestor **Text** or **TSpan**
          element specifies an absolute X coordinate for a given character
          via an **x** attribute, then that absolute X coordinate is
          used (nearest ancestor has precedence), else

      (b) the starting X coordinate for rendering the glyphs corresponding
          to a given character is the X coordinate of the resulting current
          text position from the most recently rendered glyph for the current
          **Text** element.


  * **y** -- `<coordinate+>`

    The corresponding list of absolute Y coordinates for the glyphs
    corresponding to the characters within this element. The processing
    rules for the **y** attribute parallel the processing rules for
    the **x** attribute.

  * **dx** -- `<length+>`

    If a single <length> is provided, this value represents the new
    relative X coordinate for the current text position for rendering
    the glyphs corresponding to the first character within this element
    or any of its descendants. The current text position is shifted
    along the x-axis of the current user coordinate system by `<length>`
    before the first character's glyphs are rendered.

    If a `list` of n `<length>` is provided, then
    the values represent incremental shifts along the x-axis for the
    current text position before rendering the glyphs corresponding to
    the first n characters within this element or any of its descendants.
    Thus, before the glyphs are rendered corresponding to each character,
    the current text position resulting from drawing the glyphs for the
    previous character within the current **Text** element
    is shifted along the X axis of the current user coordinate system by
    `<length>` .

    If more `<lengths>` are provided than characters, then any extra
    `<lengths>` will have no effect on glyph positioning.

    If more characters exist than <length>s, then for each of these extra
    characters:

      (a) if an ancestor **Text** or **TSpan**
          element specifies a relative X coordinate for the given character
          via a **dx** attribute, then the current text position is shifted
          along the x-axis of the current user coordinate system by that
          amount (nearest ancestor has precedence), else

      (b) no extra shift along the x-axis occurs.

    If the attribute is not specified:

      (a) if an ancestor **Text** or **TSpan**
          element specifies a relative X coordinate for a given character
          via a **dx** attribute, then the current text position is shifted
          along the x-axis of the current user coordinate system by that
          amount (nearest ancestor has precedence), else

      (b) no extra shift along the x-axis occurs.

  * **dy** -- `<length+>`

    The corresponding list of relative Y coordinates for the characters
    within the **tspan** element. The processing rules for the **dy** attribute
    parallel the processing rules for the **dx** attribute.

  * **rotate** -- `<angle+>`

    The supplemental rotation about the current text position that will be
    applied to all of the glyphs corresponding to each character within
    this element.

    If a `list` of `<numbers>` is provided, then the first `<number>` represents
    the supplemental rotation for the glyphs corresponding to the first
    character within this element or any of its descendants, the second
    <number> represents the supplemental rotation for the glyphs that
    correspond to the second character, and so on.

    If more `<numbers>` are provided than there are characters, then the
    extra `<numbers>` will be ignored.

    If more characters are provided than `<numbers>`, then for each of these
    extra characters the rotation value specified by the last number must
    be used.

    If the attribute is not specified and if an ancestor **Text**
    or **TSpan** element specifies a supplemental rotation
    for a given character via a **rotate** attribute, then the given
    supplemental rotation is applied to the given character (nearest
    ancestor has precedence). If there are more characters than `<numbers>`
    specified in the ancestor's **rotate** attribute, then for each of
    these extra characters the rotation value specified by the last number
    must be used.

    This supplemental rotation has no impact on the rules by which current
    text position is modified as glyphs get rendered and is supplemental
    to any rotation due to text on a path and to **glyph-orientation-horizontal**
    or **glyph-orientation-vertical**.

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **textLength** -- `<length>`

    The purpose of this attribute is to allow
    the author to achieve exact alignment, in visual rendering order after
    any bidirectional reordering, for the first and last rendered glyphs
    that correspond to this element; thus, for the last rendered character
    (in visual rendering order after any bidirectional reordering), any
    supplemental inter-character spacing beyond normal glyph advances are
    ignored (in most cases) when the user agent determines the appropriate
    amount to expand/compress the text string to fit within a length of
    **textLength**.

  * **lengthAdjust** -- ``'spacing | spacingAndGlyphs'``

    Indicates the type of adjustments which the user agent shall make to make
    the rendered length of the text match the value specified on the **textLength**
    attribute.

    * ``'spacing'`` indicates that only the advance values are adjusted. The
      glyphs themselves are not stretched or compressed.

    * ``'spacingAndGlyphs'`` indicates that the advance values are adjusted and
      the glyphs themselves stretched or compressed in one axis (i.e., a
      direction parallel to the inline-progression-direction).

    If the attribute is not specified, the effect is as a value of *spacing*
    were specified.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`

TRef
====

.. autoclass:: svgwrite.text.TRef

.. seealso:: http://www.w3.org/TR/SVG11/text.html#TRefElement

.. automethod:: svgwrite.text.TRef.__init__

.. automethod:: svgwrite.text.TRef.set_href

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.mixins.Presentation`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接在给定元素上指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果即使外部资源不可用，文档渲染仍然可以继续；否则为 *True*。

  * **xlink:href** -- `<string>`

    指向一个元素的 IRI 引用，该元素的字符数据内容将作为此 **tref** 元素的字符数据。

.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **xlink:href** -- `<string>`
    A IRI reference to an element whose character data content shall be used
    as character data for this **tref** element.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`

TextPath
========

.. autoclass:: svgwrite.text.TextPath

.. seealso:: http://www.w3.org/TR/SVG11/text.html#TextPathElement

方法
-------

Methods

.. automethod:: svgwrite.text.TextPath.__init__

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.mixins.Presentation`

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接在给定元素上指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果即使外部资源不可用，文档渲染仍然可以继续；否则为 *True*。

  * **xlink:href** -- `string`

    指向一个元素的 IRI 引用，该元素的字符数据内容将作为此 **TRef** 元素的字符数据。

  * **startOffset** -- `<length>`

    从 **path** 起始位置的偏移量，用于计算初始当前文本位置，采用用户代理的路径距离算法计算。值可以是百分比或在当前用户坐标系统中测量的路径距离。

  * **method** -- ``'align | stretch'``

    指示文本沿路径渲染的方式。

  * **spacing** -- ``'auto | exact'``

    指示用户代理应如何确定沿路径渲染的字形之间的间距。

.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **xlink:href** -- `string`

    A IRI reference to an element whose character data content shall be used
    as character data for this **TRef** element.

  * **startOffset** -- `<length>`

    An offset from the start of the **path** for
    the initial current text position, calculated using the user agent's
    distance along the path algorithm. Value as percentage or distance along
    the path measured in the current user coordinate system.

  * **method** -- ``'align | stretch'``

    Indicates the method by which text should be rendered along the path.

  * **spacing** -- ``'auto | exact'``

    Indicates how the user agent should determine the spacing between glyphs
    that are to be rendered along a path.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`

TextArea
========

.. autoclass:: svgwrite.text.TextArea

.. seealso:: http://www.w3.org/TR/SVGMobile12/text.html#TextAreaElement

方法
-------

Methods

.. automethod:: svgwrite.text.TextArea.write

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

  * **x** -- *<coordinate>*

    文本内容将被放置的矩形区域的一个角落的 x 轴坐标。lacuna 值为 ``'0'``。

  * **y** -- *<coordinate>*

    文本内容将被放置的矩形区域的一个角落的 y 轴坐标。lacuna 值为 ``'0'``。

  * **width** -- ``'auto'`` | *<coordinate>*

    文本内容将被放置的矩形区域的宽度。值为 ``'auto'`` 表示矩形区域的宽度是无限的。lacuna 值为 ``'auto'``。

  * **height** -- ``'auto'`` | *<coordinate>*

    文本内容将被放置的矩形区域的高度。值为 ``'auto'`` 表示矩形区域的高度是无限的。lacuna 值为 ``'auto'``。

  * **editable** -- ``'auto'| simple'``

    此属性指示文本是否可以编辑。参见 'editable' 属性的定义。

  * **focusable** -- ``'true | false | auto'``

    ===========  =============================================================
    值            描述
    ===========  =============================================================
    ``'true'``   元素是键盘可识别的，必须像其他任何可以获得焦点的 UI 组件一样处理。
    ``'false'``  元素不可聚焦。
    ``'auto'``   lacuna 值。等同于 ``'false'``。
    ===========  =============================================================

    例外情况：参见 http://www.w3.org/TR/SVGMobile12/interact.html#focusable-attr

  * **line-increment** -- ``'auto | inherit'`` | `<number>`

    **line-increment** 属性提供了对块级进展方向中每一行大小的有限控制。此属性适用于 **textArea** 元素及其子元素。**line-increment** 属性在用于非 **textArea** 元素或没有 **textArea** 元素作为祖先的元素时，不应产生任何效果。

  * **text-align** -- ``'start | end | center | inherit'``

    在流动文本的行进方向中，文本对齐通过 text-align 属性提供。

  * **display-align** -- ``'auto | before | center | after | inherit'``

    **display-align** 属性指定 **textArea** 元素中文本内容在块级进展方向上的对齐方式。

    =============  ===========================================================
    值              描述
    =============  ===========================================================
    ``'auto'``     对于 SVG，auto 等同于 before。
    ``'before'``   第一行的前边缘与第一区域的前边缘对齐。
    ``'center'``   行在块级进展方向上居中。
    ``'after'``    最后一行的后边缘与最后区域的后边缘对齐。
    =============  ===========================================================

    布局规则：参见 http://www.w3.org/TR/SVGMobile12/text.html#TextAreaElement

.. tab:: 英文


  * **x** -- *<coordinate>*

    The x-axis coordinate of one corner of the rectangular region into which
    the text content will be placed. The lacuna value is ``'0'``.

  * **y** -- *<coordinate>*

    The y-axis coordinate of one corner of the rectangular region into which
    the text content will be placed. The lacuna value is ``'0'``.

  * **width** -- ``'auto'`` | *<coordinate>*

    The width of the rectangular region into which the text content will be
    placed. A value of ``'auto'`` indicates that the width of the rectangular
    region is infinite. The lacuna value is ``'auto'``.

  * **height** -- ``'auto'`` | *<coordinate>*

    The height of the rectangular region into which the text content will be
    placed. A value of ``'auto'`` indicates that the height of the rectangular
    region is infinite. The lacuna value is ``'auto'``.

  * **editable** -- ``'auto`| simple'``

    This attribute indicates whether the text can be edited. See the definition
    of the 'editable' attribute.

  * **focusable** -- ``'true | false | auto'``

    ===========  =============================================================
    Value        Description
    ===========  =============================================================
    ``'true'``   The element is keyboard-aware and must be treated as any
                other UI component that can get focus.
    ``'false'``  The element is not focusable.
    ``'auto'``   The lacuna value. Equivalent to ``'false'``
    ===========  =============================================================

    Exception: see http://www.w3.org/TR/SVGMobile12/interact.html#focusable-attr

  * **line-increment** -- ``'auto | inherit'`` | `<number>`

    The **line-increment** property provides limited control over the size of
    each line in the block-progression-direction. This property applies to the
    **textArea** element, and to child elements of the **textArea** element.
    The **line-increment** property must not have any effect when used on an
    element which is not, or does not have as an ancestor, a **textArea**
    element.

  * **text-align** -- ``'start | end | center | inherit'``

    Alignment in the inline progression direction in flowing text is provided
    by the text-align property.

  * **display-align** -- ``'auto | before | center | after | inherit'``

    The **display-align** property specifies the alignment, in the
    block-progression-direction, of the text content of the **textArea** element.

    =============  ===========================================================
    Value          Description
    =============  ===========================================================
    ``'auto'``     For SVG, auto is equivalent to before.
    ``'before'``   The before-edge of the first line is aligned with the
                  before-edge of the first region.
    ``'center'``   The lines are centered in the block-progression-direction.
    ``'after'``    The after-edge of the last line is aligned with the
                  after-edge of the last region.
    =============  ===========================================================

    Layout rules: see http://www.w3.org/TR/SVGMobile12/text.html#TextAreaElement
