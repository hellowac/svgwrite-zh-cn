线性渐变/LinearGradient
============================

LinearGradient

.. automodule:: svgwrite.gradients

.. seealso::

  * http://www.w3.org/TR/SVG11/pservers.html#Gradients
  * http://www.w3.org/TR/SVG11/pservers.html#LinearGradients

.. autoclass:: svgwrite.gradients.LinearGradient

方法
-------

Methods

.. automethod:: svgwrite.gradients.LinearGradient.__init__

.. automethod:: svgwrite.gradients.LinearGradient.add_stop_color

.. automethod:: svgwrite.gradients.LinearGradient.get_paint_server

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

  * **gradientUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **x1**、**y1**、**x2** 和 **y2** 属性的坐标系统。

    .. 参见： http://www.w3.org/TR/SVG11/pservers.html#LinearGradientElementGradientUnitsAttribute

  * **gradientTransform** -- `<transform-list>`

    使用 :class:`-svgwrite.mixins.Transform` 接口设置转换。

    包含一个可选的附加变换的定义，用于将渐变坐标系统转换为目标坐标系统（即，userSpaceOnUse 或 objectBoundingBox）。这允许对渐变进行如倾斜等变换。此附加变换矩阵是后乘的（即，插入到任何先前定义的变换之后），包括将对象边界框单位转换为用户空间所需的隐式变换。

  * **x1** -- `<coordinate>`  -- **start** 参数

    **x1**、**y1**、**x2** 和 **y2** 定义了线性渐变的渐变向量。该渐变向量提供渐变停止点的起始和结束位置。**x1**、**y1**、**x2** 和 **y2** 的值可以是数字或百分比。

    默认值为 ``'0%'``。

  * **y1** -- `<coordinate>`  -- **start** 参数

    参见 **x1**。默认值为 ``'0%'``。

  * **x2** -- `<coordinate>` -- **end** 参数

    参见 **x1**。默认值为 ``'100%'``。

  * **y2** -- `<coordinate>` -- **end** 参数

    参见 **x1**。默认值为 ``'0%'``。

  * **spreadMethod** -- ``'pad | reflect | repeat'``

    指示当渐变在目标矩形的边界内开始或结束时会发生什么。可能的值为： ``'pad'`` ，表示使用渐变的终端颜色填充目标区域的其余部分； ``'reflect'`` ，表示反射渐变图案，从起始到结束，再从结束到起始，反复填充目标矩形； ``'repeat'`` ，表示重复渐变图案，从起始到结束，再从起始到结束，反复填充目标区域。

    默认值为 ``'pad'``。

  * **xlink:href** -- `<iri>` -- **inherit** 参数

    指向当前 SVG 文档片段内的另一个 :class:`LinearGradient` 或 :class:`RadialGradient` 元素的 URI 引用。任何在引用元素上定义的 :class:`LinearGradient` 属性（这些属性在此元素上未定义）将由此元素继承。如果此元素没有定义渐变停止点，并且引用的元素有渐变停止点（可能是由于其自己的 **xlink:href** 属性），则此元素将继承引用元素的渐变停止点。继承可以间接进行，且可以达到任意级别；因此，如果引用的元素由于其自身的 **xlink:href** 属性继承了属性或渐变停止点，则当前元素也可以继承这些属性或渐变停止点。

.. tab:: 英文


  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed
    even if external resources are unavailable else: *True*

  * **gradientUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for attributes **x1**, **y1**, **x2** and **y2**.

    .. seealso:: http://www.w3.org/TR/SVG11/pservers.html#LinearGradientElementGradientUnitsAttribute

  * **gradientTransform** -- `<transform-list>`

    Use the :class:`-svgwrite.mixins.Transform` interface to set transformations.

    Contains the definition of an optional additional transformation from the
    gradient coordinate system onto the target coordinate system (i.e.,
    userSpaceOnUse or objectBoundingBox). This allows for things such as skewing
    the gradient. This additional transformation matrix is post-multiplied to
    (i.e., inserted to the right of) any previously defined transformations,
    including the implicit transformation necessary to convert from object
    bounding box units to user space.

  * **x1** -- `<coordinate>`  -- **start** parameter

    **x1**, **y1**, **x2** and **y2** define a gradient vector for the linear
    gradient. This gradient vector provides starting and ending points onto
    which the gradient stops are mapped. The values of **x1**, **y1**, **x2**
    and **y2** can be either numbers or percentages.

    default is ``'0%'``

  * **y1** -- `<coordinate>`  -- **start** parameter

    See **x1**. Default is ``'0%'``

  * **x2** -- `<coordinate>` -- **end** parameter

    See **x1**. Default is ``'100%'``

  * **y2** -- `<coordinate>` -- **end** parameter

    See **x1**. Default is ``'0%'``

  * **spreadMethod** -- ``'pad | reflect | repeat'``

    Indicates what happens if the gradient starts or ends inside the bounds of
    the target rectangle. Possible values are: ``'pad'``, which says to use the
    terminal colors of the gradient to fill the remainder of the target region,
    ``'reflect'``, which says to reflect the gradient pattern start-to-end,
    end-to-start, start-to-end, etc. continuously until the target rectangle is
    filled, and ``'repeat'``, which says to repeat the gradient pattern start-to-end,
    start-to-end, start-to-end, etc. continuously until the target region is
    filled.

    default is ``'pad'``

  * **xlink:href** -- `<iri>` -- **inherit** parameter

    A URI reference to a different :class:`LinearGradient` or :class:`RadialGradient`
    element within the current SVG document fragment. Any :class:`LinearGradient`
    attributes which are defined on the referenced element which are not defined
    on this element are inherited by this element. If this element has no defined
    gradient stops, and the referenced element does (possibly due to its own
    **xlink:href** attribute), then this element inherits the gradient stop from
    the referenced element. Inheritance can be indirect to an arbitrary level;
    thus, if the referenced element inherits attribute or gradient stops due to
    its own **xlink:href** attribute, then the current element can inherit those
    attributes or gradient stops.

径向渐变/RadialGradient
============================

RadialGradient

.. seealso:: http://www.w3.org/TR/SVG11/pservers.html#RadialGradients

.. autoclass:: svgwrite.gradients.RadialGradient

方法
-------

Methods

.. automethod:: svgwrite.gradients.RadialGradient.__init__

.. automethod:: svgwrite.gradients.RadialGradient.add_stop_color

.. automethod:: svgwrite.gradients.RadialGradient.get_paint_server

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

  * **gradientUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **cx**、**cy**、**r**、**fx** 和 **fy** 属性的坐标系统。

    .. 参见： http://www.w3.org/TR/SVG11/pservers.html#RadialGradientElementGradientUnitsAttribute

  * **cx** -- `<coordinate>` -- **center** 参数

    **cx**、**cy** 和 **r** 定义了径向渐变的最大（即，最外层）圆。渐变将绘制，使得 100% 渐变停止点被映射到这个最大（即最外层）圆的周长。

    默认值为 ``'50%'``。

  * **cy** -- `<coordinate>` -- **center** 参数

    参见 **cx**。默认值为 ``'50%'``。

  * **r** -- `<length>` -- **r** 参数

    参见 **cx**。

    如果值为零，将会使用最后一个渐变停止点的颜色和不透明度将区域绘制为单一颜色。

    默认值为 ``'50%'``。

  * **fx** -- `<coordinate>` -- **focal** 参数

    **fx** 和 **fy** 定义了径向渐变的焦点。渐变将绘制，使得 0% 渐变停止点被映射到 (fx, fy)。如果没有指定 **fx** 属性，则 **fx** 将与元素的 **cx** 的呈现值重合，无论 **cx** 的值是否继承。如果该元素引用了一个指定 **fx** 值的元素，那么 **fx** 的值将从引用的元素继承。

  * **fy** -- `<coordinate>` -- **focal** 参数

    参见 **fx**。如果没有指定 **fy** 属性，则 **fy** 将与元素的 **cy** 的呈现值重合，无论 **cy** 的值是否继承。如果该元素引用了一个指定 **fy** 值的元素，那么 **fy** 的值将从引用的元素继承。

  * **gradientTransform** -- `<transform-list>`

    使用 :class:`-svgwrite.mixins.Transform` 接口设置变换。

    参见 :class:`LinearGradient`

  * **spreadMethod** -- ``'pad | reflect | repeat'``

    参见 :class:`LinearGradient`

  * **xlink:href** -- `<iri>` -- **inherit** 参数

    参见 :class:`LinearGradient`

.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed
    even if external resources are unavailable else: *True*

  * **gradientUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for attributes **cx**, **cy**, **r**, **fx**
    and **fy**.

    .. seealso:: http://www.w3.org/TR/SVG11/pservers.html#RadialGradientElementGradientUnitsAttribute

  * **cx** -- `<coordinate>` -- **center** parameter

    **cx**, **cy** and **r** define the largest (i.e., outermost) circle for
    the radial gradient. The gradient will be drawn such that the 100% gradient
    stop is mapped to the perimeter of this largest (i.e., outermost) circle.

    default is ``'50%'``

  * **cy** -- `<coordinate>` -- **center** parameter

    See **cx**. Default is ``'50%'``.

  * **r** -- `<length>` -- **r** parameter

    See **cx**.

    A value of zero will cause the area to be painted as a single color using
    the color and opacity of the last gradient stop.

    Default is ``'50%'``.

  * **fx** -- `<coordinate>` -- **focal** parameter

    **fx** and **fy** define the focal point for the radial gradient. The
    gradient will be drawn such that the 0% gradient stop is mapped to (fx, fy).
    If attribute **fx** is not specified, **fx** will coincide with the
    presentational value of **cx** for the element whether the value for **cx**
    was inherited or not. If the element references an element that specifies a
    value for **fx**, then the value of 'fx' is inherited from the referenced
    element.

  * **fy** -- `<coordinate>` -- **focal** parameter

    See **fx**.
    If attribute **fy** is not specified, **fy** will coincide with the
    presentational vlaue of **cy** for the element whether the value for **cy**
    was inherited or not. If the element references an element that specifies a
    value for **fy**, then the value of **fy** is inherited from the referenced
    element.

  * **gradientTransform** -- `<transform-list>`

    Use the :class:`-svgwrite.mixins.Transform` interface to set transformations.

    See :class:`LinearGradient`

  * **spreadMethod** -- ``'pad | reflect | repeat'``

    See :class:`LinearGradient`

  * **xlink:href** -- `<iri>` -- **inherit** parameter

    See :class:`LinearGradient`