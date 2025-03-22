ClipPath
========


.. autoclass:: svgwrite.masking.ClipPath

.. tab:: 中文

  向 :class:`ClipPath` 添加剪切元素::

    dwg = svgwrite.Drawing()
    clip_path = dwg.defs.add(dwg.clipPath())
    clip_path.add(dwg.circle((100, 100), 50))

.. tab:: 英文

  Adding clipping elements to :class:`ClipPath`::

    dwg = svgwrite.Drawing()
    clip_path = dwg.defs.add(dwg.clipPath())
    clip_path.add(dwg.circle((100, 100), 50))

.. seealso:: http://www.w3.org/TR/SVG11/masking.html#ClippingPaths

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接为给定元素指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    `False`：如果外部资源不可用，文档渲染仍然可以继续；否则：`True`。

  * **transform** -- 使用 :class:`svgwrite.mixins.Transform` 方法。

  * **clipPathUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **clipPath** 内容的坐标系统。

    如果 clipPathUnits = ``'userSpaceOnUse'`` ，**clipPath** 的内容代表在引用 **clipPath** 元素时当前用户坐标系统中的值（即，通过 **clip-path** 属性引用 **clipPath** 元素的元素的用户坐标系统）。

    如果 clipPathUnits = ``'objectBoundingBox'`` ，则 **clipPath** 元素内容的用户坐标系统是通过应用裁剪路径的元素的边界框来确定的。

    默认值为 ``'userSpaceOnUse'``。

.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed
    even if external resources are unavailable else: *True*

  * **transform** -- use :class:`svgwrite.mixins.Transform` methods

  * **clipPathUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for the contents of the **clipPath**.

    If clipPathUnits = ``'userSpaceOnUse'`` , the contents of the **clipPath**
    represent values in the current user coordinate system in place at the
    time when the **clipPath** element is referenced (i.e., the user
    coordinate system for the element referencing the **clipPath** element
    via the **clip-path** property).

    If clipPathUnits = ``'objectBoundingBox'`` , then the user coordinate system
    for the contents of the **clipPath** element is established using the
    bounding box of the element to which the clipping path is applied.

    Default is ``'userSpaceOnUse'``

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Presentation Attributes </attributes/presentation>`

Mask
====

.. autoclass:: svgwrite.masking.Mask

.. seealso:: http://www.w3.org/TR/SVG11/masking.html#Masking

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    为元素分配一个或多个 CSS 类名。

  * **style** -- `string`

    允许直接为给定元素指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    `False`：如果外部资源不可用，文档渲染仍然可以继续；否则：`True`。

  * **maskUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **x**、**y**、**width** 和 **height** 的坐标系统。

    如果 maskUnits = ``'userSpaceOnUse'`` ，**x**、**y**、**width** 和 **height** 代表在引用 **mask** 元素时当前用户坐标系统中的值（即，通过 **mask** 属性引用 **mask** 元素的元素的用户坐标系统）。

    如果 maskUnits = ``'objectBoundingBox'`` ，**x**、**y**、**width** 和 **height** 代表应用该蒙版的元素的边界框的分数或百分比。

    默认值为 ``'objectBoundingBox'``。

  * **maskContentUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    定义 **mask** 内容的坐标系统。

    如果 maskContentUnits = ``'userSpaceOnUse'`` ，**mask** 元素内容的用户坐标系统是引用 **mask** 元素时当前用户坐标系统中的值（即，通过 **mask** 属性引用 **mask** 元素的元素的用户坐标系统）。

    如果 maskContentUnits = ``'objectBoundingBox'`` ，**mask** 内容的用户坐标系统是使用应用该蒙版的元素的边界框来确定的。

    默认值为 ``'userSpaceOnUse'``。

  * **x** -- `<coordinate>` -- **start** 参数

    最大可能离屏缓冲区一个角落的 x 轴坐标。请注意，用于渲染蒙版内任何图形的裁剪路径将由给定对象当前裁剪路径与由 **x**、**y**、**width** 和 **height** 定义的矩形的交集组成。

    默认值为 ``'-10%'``。

  * **y** -- `<coordinate>` -- **start** 参数

    最大可能离屏缓冲区一个角落的 y 轴坐标。

    默认值为 ``'-10%'``。

  * **width** -- `<length>` -- **size** 参数

    最大可能离屏缓冲区的宽度。请注意，用于渲染蒙版内任何图形的裁剪路径将由给定对象当前裁剪路径与由 **x**、**y**、**width** 和 **height** 定义的矩形的交集组成。

    默认值为 ``'120%'``。

  * **height** -- `<length>` -- **size** 参数

    最大可能离屏缓冲区的高度。

    默认值为 ``'120%'``。

.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    `False`: if document rendering can proceed even if external resources are
    unavailable else: `True`

  * **maskUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for attributes **x**, **y**, **width** and
    **height**.

    If maskUnits = ``'userSpaceOnUse'`` , **x**, **y**, **width** and **height**
    represent values in the current user coordinate system in place at the time
    when the **mask** element is referenced (i.e., the user coordinate system
    for the element referencing the **mask** element via the **mask** property).

    If maskUnits = ``'objectBoundingBox'`` , **x**, **y**, **width** and **height**
    represent fractions or percentages of the bounding box of the element to
    which the mask is applied.

    Default is ``'objectBoundingBox'``.

  * **maskContentUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    Defines the coordinate system for the contents of the **mask**.

    If maskContentUnits = ``'userSpaceOnUse'`` , the user coordinate system for
    the contents of the **mask** element is the current user coordinate system
    in place at the time when the **mask** element is referenced (i.e., the user
    coordinate system for the element referencing the **mask** element via the
    **mask** property).

    If maskContentUnits = ``'objectBoundingBox'`` , the user coordinate system for
    the contents of the **mask** is established using the bounding box of the
    element to which the mask is applied.

    Default is ``'userSpaceOnUse'``.

  * **x** -- `<coordinate>` -- **start** parameter

    The x-axis coordinate of one corner of the rectangle for the largest
    possible offscreen buffer. Note that the clipping path used to render any
    graphics within the mask will consist of the intersection of the current
    clipping path associated with the given object and the rectangle defined by
    **x**, **y**, **width** and **height**.

    Default is ``'-10%'``.

  * **y** -- `<coordinate>` -- **start** parameter

    The y-axis coordinate of one corner of the rectangle for the largest
    possible offscreen buffer.

    Default is ``'-10%'``.

  * **width** -- `<length>` -- **size** parameter

    The width of the largest possible offscreen buffer. Note that the clipping
    path used to render any graphics within the mask will consist of the
    intersection of the current clipping path associated with the given object
    and the rectangle defined by **x**, **y**, **width** and **height**.

    Default is ``'120%'``.

  * **height** -- `<length>` -- **size** parameter

    The height of the largest possible offscreen buffer.

    Default is ``'120%'``.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Presentation Attributes </attributes/presentation>`
