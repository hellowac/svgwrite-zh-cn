.. _feOffset:

feOffset 滤镜元素
=======================

feOffset Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feOffsetElement

.. tab:: 中文

    此过滤器原语将输入图像相对于其当前在图像空间中的位置偏移指定的向量。

    这对于像阴影效果这样的操作非常重要。

    在应用此过滤器时，目标位置可能会在设备空间中偏移一个像素的分数。在这种情况下，高质量的查看器应使用适当的插值技术，例如双线性插值或双三次插值。特别推荐在动态查看器中使用插值，因为它提供了图像平滑移动的视觉效果。对于静态查看器，这种影响较小。应特别注意 **image-rendering** 属性的设置，以确定作者的意图。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive offsets the input image relative to its current position
    in the image space by the specified vector.

    This is important for effects like drop shadows.

    When applying this filter, the destination location may be offset by a fraction
    of a pixel in device space. In this case a high quality viewer should make use
    of appropriate interpolation techniques, for example bilinear or bicubic. This
    is especially recommended for dynamic viewers where this interpolation provides
    visually smoother movement of images. For static viewers this is less of a concern.
    Close attention should be made to the **image-rendering** property setting to
    determine the authors intent.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (请参见 :ref:`in <in_attr>` 属性)

    * **dx** -- `<number>`

        沿 x 轴偏移输入图形的距离。偏移量以 **filter** 元素的 **primitiveUnits** 属性所定义的坐标系统为单位表示。

        如果未指定该属性，则效果与指定值为 ``'0'`` 时相同。

    * **dy** -- `<number>`

        沿 y 轴偏移输入图形的距离。偏移量以 **filter** 元素的 **primitiveUnits** 属性所定义的坐标系统为单位表示。

        如果未指定该属性，则效果与指定值为 ``'0'`` 时相同。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **dx** -- `<number>`

        The amount to offset the input graphic along the x-axis. The offset amount
        is expressed in the coordinate system established by attribute **primitiveUnits**
        on the **filter** element.

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.

    * **dy** -- `<number>`

        The amount to offset the input graphic along the y-axis. The offset amount
        is expressed in the coordinate system established by attribute **primitiveUnits**
        on the **filter** element.

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.