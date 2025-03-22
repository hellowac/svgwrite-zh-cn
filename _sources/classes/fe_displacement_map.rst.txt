.. _feDisplacementMap:

feDisplacementMap 滤镜元素
================================

feDisplacementMap Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feDisplacementMapElement

.. tab:: 中文

    该滤镜原语使用来自 **in2** 图像的像素值来空间地位移 **in** 图像。

    此滤镜可能对输入图像产生任意的非本地化效果，这可能需要在处理管道中进行大量缓冲。然而，通过这种方式，任何中间缓冲需求都可以通过 **scale** 来确定， **scale** 代表了 x 或 y 方向的最大位移范围。

    在应用此滤镜时，源像素位置通常会位于几个源像素之间。在这种情况下，建议高质量的查看器对周围像素应用插值，例如双线性或三次插值，而不仅仅是选择最近的源像素。根据可用插值器的速度，这一选择可能会受到 **image-rendering** 属性设置的影响。

    **color-interpolation-filters** 属性仅适用于 **in2** 源图像，而不适用于 **in** 源图像。**in** 源图像必须保持其当前的颜色空间。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive uses the pixels values from the image from **in2** to
    spatially displace the image from **in**.

    This filter can have arbitrary non-localized effect on the input which might
    require substantial buffering in the processing pipeline. However with this
    formulation, any intermediate buffering needs can be determined by scale which
    represents the maximum range of displacement in either x or y.

    When applying this filter, the source pixel location will often lie between
    several source pixels. In this case it is recommended that high quality viewers
    apply an interpolent on the surrounding pixels, for example bilinear or bicubic,
    rather than simply selecting the nearest source pixel. Depending on the speed of
    the available interpolents, this choice may be affected by the
    **image-rendering** property setting.

    The **color-interpolation-filters** property only applies to the **in2** source
    image and does not apply to the **in** source image. The ‘in’ source image must
    remain in its current color space.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (见 :ref:`in <in_attr>` 属性)

    * **in2** -- (见 :ref:`in <in_attr>` 属性)

        第二个输入图像，用于在 **in** 图像中位移像素。此属性可以具有与 **in** 属性相同的值。

    * **scale** -- `<number>`

        位移缩放因子。该值以 **filter** 元素上的 **primitiveUnits** 属性所定义的坐标系统来表示。

        当此属性的值为 ``'0'`` 时，此操作对源图像没有任何影响。

        如果未指定此属性，则效果等同于指定值为 ``'0'``。

    * **xChannelSelector** -- ``'R | G | B | A'``

        指定使用 **in2** 中的哪个通道来沿 x 轴位移 **in** 图像的像素。如果未指定 **xChannelSelector** 属性，则效果等同于指定值为 ``'A'``。

    * **yChannelSelector** -- ``'R | G | B | A'``

        指定使用 **in2** 中的哪个通道来沿 y 轴位移 **in** 图像的像素。如果未指定 **yChannelSelector** 属性，则效果等同于指定值为 ``'A'``。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **in2** -- (see :ref:`in <in_attr>` attribute)

        The second input image, which is used to displace the pixels in the image
        from attribute **in**. This attribute can take on the same values as the
        **in** attribute.

    * **scale** -- `<number>`

        Displacement scale factor. The amount is expressed in the coordinate system
        established by attribute **primitiveUnits** on the **filter** element.

        When the value of this attribute is ``'0'``, this operation has no effect on the
        source image.

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.

    * **xChannelSelector** -- ``'R | G | B | A'``

        Indicates which channel from **in2** to use to displace the pixels in **in**
        along the x-axis. If attribute **xChannelSelector** is not specified, then
        the effect is as if a value of ``'A'`` were specified.

    * **yChannelSelector** -- ``'R | G | B | A'``

        Indicates which channel from **in2** to use to displace the pixels in **in**
        along the y-axis. If attribute **yChannelSelector** is not specified, then
        the effect is as if a value of ``'A'`` were specified.

