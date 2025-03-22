.. _feConvolveMatrix:

feConvolveMatrix 滤镜元素
===============================

feConvolveMatrix Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feConvolveMatrixElement

.. tab:: 中文

    **feConvolveMatrix** 应用矩阵卷积滤镜效果。卷积将输入图像中的像素与邻近像素结合，以产生结果图像。通过卷积可以实现多种成像操作，包括模糊、边缘检测、锐化、浮雕和倒角等。

    有关常见属性，请参阅： :ref:`filter_primitive`

.. tab:: 英文

    **feConvolveMatrix** applies a matrix convolution filter effect. A convolution
    combines pixels in the input image with neighboring pixels to produce a resulting
    image. A wide variety of imaging operations can be achieved through convolutions,
    including blurring, edge detection, sharpening, embossing and beveling.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (见 :ref:`in <in_attr>` 属性)

    * **order** -- `<number-optional-number>`

    指定 **kernelMatrix** 中每个维度的单元格数量。提供的值必须是大于零的 `<integer>`。第一个数字 `<orderX>` 表示矩阵中的列数，第二个数字 `<orderY>` 表示矩阵中的行数。如果未提供 `<orderY>`，则默认为 `<orderX>`。

    如果未指定此属性，则效果等同于指定值为 3。

    * **kernelMatrix** -- `<list of numbers>`

    构成卷积的 **kernelMatrix** 数字列表。值通过空格字符和/或逗号分隔。列表中的条目数量必须等于 `<orderX>` 乘以 `<orderY>`。

    * **divisor** -- `<number>`

    将 **kernelMatrix** 应用到输入图像以得到一个数值后，该数值将被除以 **divisor**，得到最终的目标颜色值。默认值为 **kernelMatrix** 中所有值的总和，除非总和为零，则将 **divisor** 设置为 1。

    * **bias** = `<number>`

    在将 **kernelMatrix** 应用到输入图像得到一个数值并应用 **divisor** 后，将 **bias** 属性的值加到每个分量上。

    * **targetX** -- `<integer>`

    确定卷积矩阵在 X 方向上相对于输入图像中给定目标像素的位置。矩阵的最左边列为零列。该值必须满足：0 <= targetX < orderX。默认情况下，卷积矩阵在 X 方向上会相对于输入图像的每个像素居中（即，targetX = floor(orderX / 2)）。

    * **targetY** -- `<integer>`

    确定卷积矩阵在 Y 方向上相对于输入图像中给定目标像素的位置。矩阵的最上面一行是零行。该值必须满足：0 <= targetY < orderY。默认情况下，卷积矩阵在 Y 方向上会相对于输入图像的每个像素居中（即，targetY = floor(orderY / 2)）。

    * **edgeMode** -- ``'duplicate | wrap | none'``

    确定如何根据需要扩展输入图像的颜色值，以便在卷积矩阵位于输入图像的边缘时能够应用矩阵操作。

    * ``'duplicate'`` 表示按需要通过复制输入图像边缘处的颜色值来扩展图像。
    * ``'wrap'`` 表示通过从图像的相对边缘获取颜色值来扩展输入图像。
    * ``'none'`` 表示通过为 R、G、B 和 A 分量的像素值设置为零来扩展输入图像。

    如果未指定 **edgeMode** 属性，则效果等同于指定值为 ``'duplicate'``。

    * **kernelUnitLength** -- `<number-optional-number>`

    第一个数字是 `<dx>` 值，第二个数字是 `<dy>` 值。如果未提供 `<dy>`，则默认为与 `<dx>` 相同的值。表示在当前滤镜单位（即由 **primitiveUnits** 属性确定的单位）中，**kernelMatrix** 中每列和每行之间的预期距离。通过为 **kernelUnitLength** 指定值，可以在一个可缩放的抽象坐标系统中定义内核。如果未指定 **kernelUnitLength**，则默认值为一个像素，这就是离屏位图中的像素坐标系统，因此可能不可缩放。为了在显示媒体和用户代理之间实现一致性，需要至少为 **filterRes** 或 **kernelUnitLength** 提供一个值。在某些实现中，最佳的结果和最快的性能通常是在临时离屏图像的像素网格与内核的像素网格对齐时实现的。负数或零值是错误的。

    * **preserveAlpha** -- ``'false | true'``

    值为 false 表示卷积将应用于所有通道，包括 alpha 通道。

    值为 true 表示卷积只应用于颜色通道。在这种情况下，滤镜将临时取消预乘颜色分量值，应用内核后再重新预乘。

    如果未指定 **preserveAlpha**，则效果等同于指定值为 ``'false'``。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **order** -- `<number-optional-number>`

        Indicates the number of cells in each dimension for **kernelMatrix**. The
        values provided must be `<integer>`s greater than zero. The first number,
        `<orderX>`, indicates the number of columns in the matrix. The second number,
        `<orderY>`, indicates the number of rows in the matrix. If `<orderY>` is not
        provided, it defaults to <orderX>.

        If the attribute is not specified, the effect is as if a value of 3 were
        specified.

    * **kernelMatrix** -- `<list of numbers>`

        The list of `<number>`s that make up the kernel matrix for the convolution.
        Values are separated by space characters and/or a comma. The number of
        entries in the list must equal `<orderX>` times `<orderY>`.

    * **divisor** -- `<number>`

        After applying the **kernelMatrix** to the input image to yield a number,
        that number is divided by **divisor** to yield the final destination color
        value. The default value is the sum of all values in **kernelMatrix**, with
        the exception that if the sum is zero, then the divisor is set to 1.

    * **bias** = `<number>`

        After applying the **kernelMatrix** to the input image to yield a number and
        applying the **divisor**, the **bias** attribute is added to each component.

    * **targetX** -- `<integer>`

        Determines the positioning in X of the convolution matrix relative to a
        given target pixel in the input image. The leftmost column of the matrix is
        column number zero. The value must be such that: 0 <= targetX < orderX. By
        default, the convolution matrix is centered in X over each pixel of the
        input image (i.e., targetX = floor ( orderX / 2 )).

    * **targetY** -- `<integer>`
        Determines the positioning in Y of the convolution matrix relative to a
        given target pixel in the input image. The topmost row of the matrix is
        row number zero. The value must be such that: 0 <= targetY < orderY. By
        default, the convolution matrix is centered in Y over each pixel of the
        input image (i.e., targetY = floor ( orderY / 2 )).

    * **edgeMode** -- ``'duplicate | wrap | none'``

        Determines how to extend the input image as necessary with color values so
        that the matrix operations can be applied when the kernel is positioned at
        or near the edge of the input image.

        * ``'duplicate'`` indicates that the input image is extended along each of its
        borders as necessary by duplicating the color values at the given edge of
        the input image.

        * ``'wrap'`` indicates that the input image is extended by taking the color
        values from the opposite edge of the image.

        * ``'none'`` indicates that the input image is extended with pixel values of
        zero for R, G, B and A.

        If attribute **edgeMode** is not specified, then the effect is as if a value
        of ``'duplicate'`` were specified.

    * **kernelUnitLength** -- `<number-optional-number>`

        The first number is the `<dx>` value. The second number is the `<dy>` value.
        If the `<dy>` value is not specified, it defaults to the same value as `<dx>`.
        Indicates the intended distance in current filter units (i.e., units as
        determined by the value of attribute **primitiveUnits**) between successive
        columns and rows, respectively, in the **kernelMatrix**. By specifying
        value(s) for **kernelUnitLength**, the kernel becomes defined in a scalable,
        abstract coordinate system. If **kernelUnitLength** is not specified, the
        default value is one pixel in the offscreen bitmap, which is a pixel-based
        coordinate system, and thus potentially not scalable. For some level of
        consistency across display media and user agents, it is necessary that a
        value be provided for at least one of **filterRes** and **kernelUnitLength**.
        In some implementations, the most consistent results and the fastest performance
        will be achieved if the pixel grid of the temporary offscreen images aligns
        with the pixel grid of the kernel. A negative or zero value is an error.

    * **preserveAlpha** -- ``'false | true'``

        A value of false indicates that the convolution will apply to all channels,
        including the alpha channel.

        A value of true indicates that the convolution will only apply to the color
        channels. In this case, the filter will temporarily unpremultiply the color
        component values, apply the kernel, and then re-premultiply at the end.

        If **preserveAlpha** is not specified, then the effect is as if a value of
        ``'false'`` were specified.
