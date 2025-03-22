.. _feGaussianBlur:

feGaussianBlur 滤镜元素
=============================

feGaussianBlur Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feGaussianBlurElement

.. tab:: 中文

    这个滤镜原语对输入图像执行高斯模糊操作。

    通常，这个操作会应用于仅包含 alpha 通道的图像，比如由内建输入 ``'SourceAlpha'`` 产生的图像。实现可能会识别到这一点，并对单通道的情况进行优化。如果输入具有无限的范围并且是常量，则此操作没有效果。如果输入具有无限的范围并且是平铺的，则滤镜会在周期性边界条件下进行评估。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive performs a Gaussian blur on the input image.

    Frequently this operation will take place on alpha-only images, such as that
    produced by the built-in input, ``'SourceAlpha'``. The implementation may notice
    this and optimize the single channel case. If the input has infinite extent and
    is constant, this operation has no effect. If the input has infinite extent and
    is a tile, the filter is evaluated with periodic boundary conditions.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (参见 :ref:`in <in_attr>` 属性)

    * **stdDeviation** -- `<number-optional-number>`

        高斯模糊操作的标准偏差。如果提供了两个 `<number>`，第一个数字表示在由 **filter** 元素上的 **primitiveUnits** 属性建立的坐标系统中，x 轴的标准偏差值。第二个值表示 y 轴的标准偏差。如果只提供一个数字，则该值将用于 x 和 y 轴。

        负值是错误。值为零会禁用给定滤镜原语的效果（即结果是滤镜输入图像）。

        如果未指定该属性，则效果就像指定了 ``'0'`` 一样。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **stdDeviation** -- `<number-optional-number>`

        The standard deviation for the blur operation. If two `<number>s` are
        provided, the first number represents a standard deviation value along the
        x-axis of the coordinate system established by attribute **primitiveUnits**
        on the **filter** element. The second value represents a standard deviation
        in Y. If one number is provided, then that value is used for both X and Y.

        A negative value is an error. A value of zero disables the effect of the
        given filter primitive (i.e., the result is the filter input image).

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.