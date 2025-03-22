.. _feTurbulence:

feTurbulence 滤镜元素
===========================

feTurbulence Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feTurbulenceElement

.. tab:: 中文

    此滤镜原语使用Perlin湍流函数创建图像。它允许合成人工纹理，如云彩或大理石。有关Perlin湍流函数的详细描述，请参阅《Texturing and Modeling》，Ebert等，AP Professional，1994。生成的图像将填充该滤镜原语的整个子区域。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive creates an image using the Perlin turbulence function. It
    allows the synthesis of artificial textures like clouds or marble. For a
    detailed description the of the Perlin turbulence function, see "Texturing and
    Modeling", Ebert et al, AP Professional, 1994. The resulting image will fill the
    entire filter primitive subregion for this filter primitive.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (请参见 :ref:`in <in_attr>` 属性)

    * **baseFrequency** -- `<number-optional-number>`

        噪声函数的基本频率（频率）参数。如果提供了两个 `<number>`，第一个数字表示X方向的基本频率，第二个数字表示Y方向的基本频率。如果只提供一个数字，则该值将用于X和Y方向。

        基本频率的负值是错误的。

        如果未指定该属性，则效果相当于指定了值 ``'0'``。

    * **numOctaves** -- `<integer>`

        噪声函数的 numOctaves 参数。

        如果未指定该属性，则效果相当于指定了值 ``'1'``。

    * **seed** -- `<number>`

        伪随机数生成器的起始数字。

        如果未指定该属性，则效果相当于指定了值 ``'0'``。当种子数字传递给上述算法时，必须首先将其截断，即四舍五入到最接近零的整数值。

    * **stitchTiles** -- ``'stitch | noStitch'``

        * ``'noStitch'`` -- 不尝试在包含湍流函数的瓦片边界处实现平滑过渡。结果有时会在瓦片边界显示明显的断裂。

        * ``'stitch'`` -- 用户代理会自动调整 baseFrequency-x 和 baseFrequency-y 值，以使 **feTurbulence** 节点的宽度和高度（即当前子区域的宽度和高度）包含第一个 octave 的 Perlin 瓦片宽度和高度的整数倍。baseFrequency 将根据哪种方向具有较小的相对（而非绝对）变化进行调整，如下所示：给定频率，计算 lowFreq=floor(width*frequency)/width 和 hiFreq=ceil(width*frequency)/width。如果 frequency/lowFreq < hiFreq/frequency，则使用 lowFreq，否则使用 hiFreq。在生成湍流值时，像通常一样生成 Perlin Noise 的格点向量，除了那些位于活动区域右边或底边的格点（即结果瓦片的大小）。在这些情况下，从活动区域的相对边缘复制格点向量。

        如果未指定 **stitchTiles** 属性，则效果相当于指定了值 ``'noStitch'``。

    * **type** -- ``'fractalNoise | turbulence'``

        指示滤镜原语是否应执行噪声或湍流函数。如果未指定 **type** 属性，则效果相当于指定了值 ``'turbulence'``。


.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **baseFrequency** -- `<number-optional-number>`

        The base frequency (frequencies) parameter(s) for the noise function. If two
        `<number>s` are provided, the first number represents a base frequency in
        the X direction and the second value represents a base frequency in the Y
        direction. If one number is provided, then that value is used for both X
        and Y.

        A negative value for base frequency is an error.

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified.

    * **numOctaves** -- `<integer>`

        The numOctaves parameter for the noise function.

        If the attribute is not specified, then the effect is as if a value of ``'1'``
        were specified.

    * **seed** -- `<number>`

        The starting number for the pseudo random number generator.

        If the attribute is not specified, then the effect is as if a value of ``'0'``
        were specified. When the seed number is handed over to the algorithm above
        it must first be truncated, i.e. rounded to the closest integer value
        towards zero.

    * **stitchTiles** -- ``'stitch | noStitch'``

        * ``'noStitch'`` -- no attempt it made to achieve smooth transitions at the
        border of tiles which contain a turbulence function. Sometimes the result
        will show clear discontinuities at the tile borders.

        * ``'stitch'`` -- then the user agent will automatically adjust
        baseFrequency-x and baseFrequency-y values such that the **feTurbulence**
        node's width and height (i.e., the width and height of the current
        subregion) contains an integral number of the Perlin tile width and
        height for the first octave. The baseFrequency will be adjusted up or
        down depending on which way has the smallest relative (not absolute)
        change as follows: Given the frequency, calculate
        lowFreq=floor(width*frequency)/width and hiFreq=ceil(width*frequency)/width.
        If frequency/lowFreq < hiFreq/frequency then use lowFreq, else use hiFreq.
        While generating turbulence values, generate lattice vectors as normal for
        Perlin Noise, except for those lattice points that lie on the right or
        bottom edges of the active area (the size of the resulting tile). In
        those cases, copy the lattice vector from the opposite edge of the active
        area.

        If attribute **stitchTiles** is not specified, then the effect is as if
        a value of ``'noStitch'`` were specified.

    * **type** -- ``'fractalNoise | turbulence'``

        Indicates whether the filter primitive should perform a noise or turbulence
        function. If attribute **type** is not specified, then the effect is as if
        a value of ``'turbulence'`` were specified.
