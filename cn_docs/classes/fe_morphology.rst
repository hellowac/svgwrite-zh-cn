.. _feMorphology:

feMorphology 滤镜元素
=============================

feMorphology Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feMorphologyElement

.. tab:: 中文

    此过滤原语执行艺术作品的“加粗”或“细化”。它特别适用于加粗或细化 alpha 通道。

    膨胀（或腐蚀）核是一个矩形，宽度为 2*x-radius ，高度为 2*y-radius 。在膨胀中，输出像素是输入图像的核矩形中相应的 R、G、B、A 值的逐组件最大值。在腐蚀中，输出像素是输入图像的核矩形中相应的 R、G、B、A 值的逐组件最小值。

    此操作通常会在仅包含 alpha 通道的图像上执行，如通过内置输入 ``'SourceAlpha'`` 产生的图像。在这种情况下，实施可能会优化单通道情况。

    如果输入具有无限扩展且为常数，则此操作没有效果。如果输入具有无限扩展且为平铺图像，则过滤器将在周期边界条件下进行评估。

    由于 **feMorphology** 在预乘颜色值上操作，它将始终导致小于或等于 alpha 通道的颜色值。

    常见属性请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive performs "fattening" or "thinning" of artwork. It is
    particularly useful for fattening or thinning an alpha channel.

    The dilation (or erosion) kernel is a rectangle with a width of 2*x-radius and a
    height of 2*y-radius. In dilation, the output pixel is the individual
    component-wise maximum of the corresponding R,G,B,A values in the input image's
    kernel rectangle. In erosion, the output pixel is the individual component-wise
    minimum of the corresponding R,G,B,A values in the input image's kernel rectangle.

    Frequently this operation will take place on alpha-only images, such as that
    produced by the built-in input, ``'SourceAlpha'``. In that case, the implementation
    might want to optimize the single channel case.

    If the input has infinite extent and is constant, this operation has no effect.
    If the input has infinite extent and is a tile, the filter is evaluated with
    periodic boundary conditions.

    Because **feMorphology** operates on premultipied color values, it will always
    result in color values less than or equal to the alpha channel.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (见 :ref:`in <in_attr>` 属性)

    * **operator** -- ``'erode | dilate'``

        一个关键字，用于指示是进行腐蚀（即细化）还是膨胀（加粗）源图形。如果没有指定 **operator** 属性，则默认效果相当于指定了 ``'erode'``。

    * **radius** -- `<number-optional-number>`

        操作的半径。如果提供两个 `<number>`，第一个值表示 x-radius，第二个值表示 y-radius。如果只提供一个数字，则该值同时用于 X 和 Y。该值的坐标系统由 **filter** 元素上的 **primitiveUnits** 属性确定。

        负值是错误的。零值将禁用该过滤器原语的效果（即，结果为透明的黑色图像）。

        如果没有指定该属性，则效果相当于指定了 ``'0'``。


.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **operator** -- ``'erode | dilate'``

        A keyword indicating whether to erode (i.e., thin) or dilate (fatten) the
        source graphic. If attribute **operator** is not specified, then the effect
        is as if a value of ``'erode'`` were specified.

    * **radius** -- `<number-optional-number>`

        The radius (or radii) for the operation. If two `<number>s` are provided,
        the first number represents a x-radius and the second value represents a
        y-radius. If one number is provided, then that value is used for both X and
        Y. The values are in the coordinate system established by attribute
        **primitiveUnits** on the **filter** element.

        A negative value is an error. A value of zero disables the effect of the
        given filter primitive (i.e., the result is a transparent black image).

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.
