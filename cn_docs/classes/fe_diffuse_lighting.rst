.. _feDiffuseLighting:

feDiffuseLighting 滤镜元素
================================

feDiffuseLighting Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feDiffuseLightingElement

.. tab:: 中文

    这个滤镜原语使用 alpha 通道作为凸起图（bump map）来为图像提供光照。生成的图像是一个 RGBA 不透明图像，基于光的颜色，且 alpha 通道的值在整个图像中为 1.0。光照计算遵循 Phong 光照模型的标准漫反射分量。生成的图像依赖于光的颜色、光源位置以及输入凸起图的表面几何形状。

    此滤镜原语生成的光照图可以通过算术 **feComposite** 合成方法中的乘法项与纹理图像结合。在将光照图应用到纹理图像之前，可以通过将多个光照图合成来模拟多个光源。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive lights an image using the alpha channel as a bump map. The
    resulting image is an RGBA opaque image based on the light color with alpha = 1.0
    everywhere. The lighting calculation follows the standard diffuse component of
    the Phong lighting model. The resulting image depends on the light color, light
    position and surface geometry of the input bump map.

    The light map produced by this filter primitive can be combined with a texture
    image using the multiply term of the arithmetic **feComposite** compositing method.
    Multiple light sources can be simulated by adding several of these light maps
    together before applying it to the texture image.

    For common properties see: :ref:`filter_primitive`

Methods
-------

.. method:: feDiffuseLighting.feDistantLight(azimuth=0, elevation=0, **extra)

    create and add a light source: :ref:`feDistantLight`

.. method:: feDiffuseLighting.fePointLight(source=(0, 0, 0), **extra)

    :param source: source 3D point (**x**, **y**, **z**)

    create and add a light source: :ref:`fePointLight`

.. method:: feDiffuseLighting.feSpotLight(source=(0, 0, 0), target=(0, 0, 0), **extra)

    :param source: source 3D point (**x**, **y**, **z**)
    :param target: target 3D point (**pointsAtX**, **pointsAtY**, **pointsAtZ**)

    create and add a light source: :ref:`feSpotLight`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (见 :ref:`in <in_attr>` 属性)

    * **surfaceScale** -- `<number>`

        表示当 Ain = 1 时的表面高度。

        如果未指定该属性，则默认值为 1。

    * **diffuseConstant** -- `<number>`

        Phong 光照模型中的 kd。在 SVG 中，这可以是任何非负数。

        如果未指定该属性，则默认值为 1。

    * **kernelUnitLength** -- `<number-optional-number>`

        第一个数字是 `<dx>` 值，第二个数字是 `<dy>` 值。如果未指定 `<dy>`，则默认为与 `<dx>` 相同的值。
        表示在当前滤镜单位（即由 **primitiveUnits** 属性确定的单位）下，**kernelMatrix** 中连续列和行之间的预期距离。
        通过为 **kernelUnitLength** 提供值，内核将被定义为一个可缩放的抽象坐标系统。如果未指定 **kernelUnitLength**，则默认值为一个像素，基于屏幕外位图，这是一个基于像素的坐标系统，因此可能不可缩放。
        为了在不同显示介质和用户代理之间保持一定的一致性，必须为 **filterRes** 或 **kernelUnitLength** 中至少提供一个值。
        在某些实现中，最一致的结果和最快的性能将通过使临时屏幕外图像的像素网格与内核的像素网格对齐来实现。负值或零值是错误的。

    * **lighting-color** -- ``'currentColor'`` | `<color>` [`<icccolor>`] | ``'inherit'``

        **lighting-color** 属性定义了 **feDiffuseLighting** 和 **feSpecularLighting** 滤镜原语的光源颜色。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **surfaceScale** -- `<number>`

        height of surface when Ain = 1.

        If the attribute is not specified, then the effect is as if a value of 1
        were specified.

    * **diffuseConstant** -- `<number>`

        kd in Phong lighting model. In SVG, this can be any non-negative number.

        If the attribute is not specified, then the effect is as if a value of 1
        were specified.

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

    * **lighting-color** -- ``'currentColor'`` | `<color>` [`<icccolor>`] | ``'inherit'``

        The **lighting-color** property defines the color of the light source for
        filter primitives **feDiffuseLighting** and **feSpecularLighting**.
