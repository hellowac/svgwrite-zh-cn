图案/Pattern
==============

.. autoclass:: svgwrite.pattern.Pattern

.. seealso:: http://www.w3.org/TR/SVG11/pservers.html#PatternElement

方法
-------

Methods


.. automethod:: svgwrite.pattern.Pattern.__init__

.. method:: Pattern.add

.. tab:: 中文

  **将元素** 添加到模式内容中。

  **pattern** 的内容是相对于一个新的坐标系统的。如果存在 **viewBox** 属性，则新坐标系统会根据 **pattern** 元素上的 **x**、**y**、**width**、**height** 和 **patternUnits** 属性，通过标准的 **viewBox** 和 **preserveAspectRatio** 规则拟合到该区域。如果没有 **viewBox** 属性，则新坐标系统的原点位于 (x, y)，其中 x 由 **pattern** 元素上的 **x** 属性确定，y 由 **pattern** 元素上的 **y** 属性确定。如下示例所示::

    <pattern x="10" y="10" width="20" height="20">
      <rect x="5" y="5" width="10" height="10"/>
    </pattern>

  或在 :mod:`svgwrite` 中调用如下::

    # dwg 是主 SVG 绘图
    pattern = dwg.pattern(insert=(10, 10), size=(20, 20))
    pattern.add(dwg.rect(insert=(5, 5), size=(10, 10)))

  在这个例子中，矩形的左上角位置距离模式图块的原点右侧 5 个单位，并且向下 5 个单位。

.. tab:: 英文

  Add **element** to the pattern content.

  The contents of the **pattern** are relative to a new coordinate system.
  If there is a **viewBox** attribute, then the new coordinate system is fitted
  into the region defined by the **x**, **y**, **width**, **height** and
  **patternUnits** attributes on the **pattern** element using the standard
  rules for **viewBox** and **preserveAspectRatio**. If there is no **viewBox**
  attribute, then the new coordinate system has its origin at (x, y), where x
  is established by the **x** attribute on the **pattern** element, and y is
  established by the **y** attribute on the ‘pattern’ element. Thus, in the
  following example::

    <pattern x="10" y="10" width="20" height="20">
      <rect x="5" y="5" width="10" height="10"/>
    </pattern>

  or as :mod:`svgwrite` calls::

    # dwg is the main svg drawing
    pattern = dwg.pattern(insert=(10, 10), size=(20, 20))
    pattern.add(dwg.rect(insert=(5, 5), size=(10, 10))

  the rectangle has its top/left located 5 units to the right and 5 units down
  from the origin of the pattern tile.

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **patternUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **x**、**y**、**width** 和 **height** 属性的坐标系统。

    如果 `patternUnits= 'userSpaceOnUse'`，**x**、**y**、**width** 和 **height** 表示在当前用户坐标系统中的值，当前坐标系统是在引用 **pattern** 元素时存在的（即通过 **fill** 或 **stroke** 属性引用 **pattern** 元素的元素的用户坐标系统），然后应用由 **patternTransform** 属性指定的变换。

    如果 `patternUnits= 'objectBoundingBox'`，则 **x**、**y**、**width** 和 **height** 属性的用户坐标系统是通过使用应用图案的元素的边界框来建立的（参见对象边界框单位），然后应用由 **patternTransform** 属性指定的变换。

    默认值为 ``'objectBoundingBox'``。

  * **patternContentUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **pattern** 内容的坐标系统。请注意，如果指定了 **viewBox** 属性，则此属性无效。

    如果 `patternContentUnits= 'userSpaceOnUse'`，**pattern** 元素内容的用户坐标系统是通过在引用 **pattern** 元素时采用当前的用户坐标系统建立的（即通过 **fill** 或 **stroke** 属性引用 **pattern** 元素的元素的用户坐标系统），然后应用由 **patternTransform** 属性指定的变换。

    如果 `patternContentUnits= 'objectBoundingBox'`，则 **pattern** 元素内容的用户坐标系统是通过使用应用图案的元素的边界框来建立的（参见对象边界框单位），然后应用由 **patternTransform** 属性指定的变换。

    默认值为 ``'userSpaceOnUse'``。

  * **patternTransform** -- `<transform-list>`

    使用 :class:`~svgwrite.mixins.Transform` 接口设置变换。

    包含从图案坐标系统到目标坐标系统（即 ``'userSpaceOnUse'`` 或 ``'objectBoundingBox'``）的可选附加变换的定义。这允许对图案瓦片进行扭曲等变换。这个附加的变换矩阵是后乘（即插入到之前定义的变换的右侧）任何已经定义的变换，包括将对象边界框单位转换为用户空间所需的隐式变换。

  * **x** -- `<coordinate>` -- **insert** 参数

    **x**、**y**、**width** 和 **height** 指定了图案瓦片的放置和间距。这些属性表示由 **patternUnits** 和 **patternTransform** 属性组合定义的坐标空间中的坐标和值。

    默认值为 ``'0'``。

  * **y** -- `<coordinate>` -- **center** 参数

    见 **x**。

    默认值为 ``'0'``。

  * **width** -- `<length>` -- **size** 参数

    见 **x**。

    负值是错误。零值会禁用元素的渲染（即不应用绘制）。

    默认值为 ``'0'``。

  * **height** -- `<length>` -- **size** 参数

    见 **x**。

    负值是错误。零值会禁用元素的渲染（即不应用绘制）。

    默认值为 ``'0'``。

  * **xlink:href** -- `string` -- **inherit** 参数

    指向当前 SVG 文档片段中另一个 **pattern** 元素的 URI 引用。任何在引用元素中定义但在当前元素中未定义的属性将由当前元素继承。如果该元素没有子元素，而引用的元素有子元素（可能是由于它自己的 **xlink:href** 属性），则当前元素继承该引用元素的子元素。继承可以是间接的，甚至可以通过任意级别的 **xlink:href** 属性间接继承。因此，如果引用的元素由于其自己的 **xlink:href** 属性继承了属性或子元素，那么当前元素也可以继承这些属性或子元素。

  * **preserveAspectRatio** -- ``'[defer] <align> [<meetOrSlice>]'``

    使用 :class:`~svgwrite.mixins.ViewBox` 接口设置 **viewBox** 和 **preserveAspectRatio**。

.. tab:: 英文

  * **patternUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for attributes **x**, **y**, **width** and
    **height**.

    If patternUnits= ``'userSpaceOnUse'`` , **x** , **y**, **width** and **height**
    represent values in the coordinate system that results from taking the
    current user coordinate system in place at the time when the **pattern**
    element is referenced (i.e., the user coordinate system for the element
    referencing the **pattern** element via a **fill** or **stroke** property)
    and then applying the transform specified by attribute **patternTransform**.

    If patternUnits= ``'objectBoundingBox'`` , the user coordinate system for
    attributes **x**, **y**, **width** and **height** is established using the
    bounding box of the element to which the pattern is applied (see Object
    bounding box units) and then applying the transform specified by attribute
    **patternTransform**.

    Default is ``'objectBoundingBox'``.

  * **patternContentUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for the contents of the **pattern**. Note that
    this attribute has no effect if attribute **viewBox** is specified.

    If patternContentUnits= ``'userSpaceOnUse'`` , the user coordinate system for
    the contents of the **pattern** element is the coordinate system that
    results from taking the current user coordinate system in place at the time
    when the **pattern** element is referenced (i.e., the user coordinate system
    for the element referencing the **pattern** element via a **fill** or
    **stroke** property) and then applying the transform specified by attribute
    **patternTransform**.

    If patternContentUnits= ``'objectBoundingBox'`` , the user coordinate system
    for the contents of the **pattern** element is established using the bounding
    box of the element to which the pattern is applied (see Object bounding box
    units) and then applying the transform specified by attribute
    **patternTransform**.

    Default is ``'userSpaceOnUse'``.

  * **patternTransform** -- `<transform-list>`

    Use the :class:`~svgwrite.mixins.Transform` interface to set transformations.

    Contains the definition of an optional additional transformation from the
    pattern coordinate system onto the target coordinate system (i.e.,
    ``'userSpaceOnUse'`` or ``'objectBoundingBox'``). This allows for things
    such as skewing the pattern tiles. This additional transformation matrix is
    post-multiplied to (i.e., inserted to the right of) any previously defined
    transformations, including the implicit transformation necessary to convert
    from object bounding box units to user space.

  * **x** -- `<coordinate>` -- **insert** parameter

    **x**, **y**, **width** and **height** indicate how the pattern tiles are
    placed and spaced. These attributes represent coordinates and values in the
    coordinate space specified by the combination of attributes **patternUnits**
    and **patternTransform**.

    Default is ``'0'``.

  * **y** -- `<coordinate>` -- **center** parameter

    See **x**.

    Default is ``'0'``.

  * **width** -- `<length>` -- **size** parameter

    See **x**.

    A negative value is an error. A value of zero disables rendering of the
    element (i.e., no paint is applied).

    Default is ``'0'``.

  * **height** -- `<length>` -- **size** parameter

    See **x**.

    A negative value is an error. A value of zero disables rendering of the
    element (i.e., no paint is applied).

    Default is ``'0'``.

  * **xlink:href** -- `string` -- **inherit** parameter

    A URI reference to a different **pattern** element within the current SVG
    document fragment. Any attributes which are defined on the referenced
    element which are not defined on this element are inherited by this element.
    If this element has no children, and the referenced element does (possibly
    due to its own **xlink:href** attribute), then this element inherits the
    children from the referenced element. Inheritance can be indirect to an
    arbitrary level; thus, if the referenced element inherits attributes or
    children due to its own **xlink:href** attribute, then the current element
    can inherit those attributes or children.

  * **preserveAspectRatio** -- ``'[defer] <align> [<meetOrSlice>]'``

    Use the :class:`~svgwrite.mixins.ViewBox` interface to set **viewbox**
    and **preserveAspectRatio**.
