.. _feSpecularLighting:

feSpecularLighting 滤镜元素
=================================

feSpecularLighting Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feSpecularLightingElement

.. tab:: 中文

    此滤镜原语使用 alpha 通道作为凹凸贴图来照亮源图形。结果图像是一个基于光照颜色的 RGBA 图像。光照计算遵循 Phong 光照模型的标准镜面分量。结果图像取决于光照颜色、光照位置以及输入凹凸贴图的表面几何形状。光照计算的结果被加到图像中。滤镜原语假设观察者位于 z 方向上的无限远处（即眼睛方向的单位向量为 (0,0,1)）。

    该滤镜原语生成的图像包含光照计算中的镜面反射部分。此类图像应与纹理结合，使用算术 **feComposite** 方法的加法项。多个光源可以通过在应用到纹理图像之前，将多个光照图层相加来模拟。

    与 **feDiffuseLighting** 不同， **feSpecularLighting** 滤镜生成的图像是非不透明的。这是因为镜面反射结果旨在添加到纹理图像中。结果图像的 alpha 通道是颜色分量中的最大值，因此当镜面反射光为零时，不会向图像中添加额外的覆盖，并且完全白色的高光将增加不透明度。

    **feDiffuseLighting** 和 **feSpecularLighting** 滤镜通常一起使用。实现可以检测到这一点，并在一次处理过程中同时计算这两个图层，而不是两次。

    常见属性请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive lights a source graphic using the alpha channel as a bump
    map. The resulting image is an RGBA image based on the light color. The lighting
    calculation follows the standard specular component of the Phong lighting model.
    The resulting image depends on the light color, light position and surface
    geometry of the input bump map. The result of the lighting calculation is added.
    The filter primitive assumes that the viewer is at infinity in the z direction
    (i.e., the unit vector in the eye direction is (0,0,1) everywhere).

    This filter primitive produces an image which contains the specular reflection
    part of the lighting calculation. Such a map is intended to be combined with a
    texture using the add term of the arithmetic **feComposite** method. Multiple
    light sources can be simulated by adding several of these light maps before
    applying it to the texture image.

    Unlike the **feDiffuseLighting**, the **feSpecularLighting** filter produces a
    non-opaque image. This is due to the fact that the specular result is meant to be
    added to the textured image. The alpha channel of the result is the max of the
    color components, so that where the specular light is zero, no additional
    coverage is added to the image and a fully white highlight will add opacity.

    The **feDiffuseLighting** and **feSpecularLighting** filters will often be
    applied together. An implementation may detect this and calculate both maps
    in one pass, instead of two.

    For common properties see: :ref:`filter_primitive`

Methods
-------

.. method:: feSpecularLighting.feDistantLight(azimuth=0, elevation=0, **extra)

    create and add a light source: :ref:`feDistantLight`

.. method:: feSpecularLighting.fePointLight(source=(0, 0, 0), **extra)

    :param source: source 3D point (**x**, **y**, **z**)

    create and add a light source: :ref:`fePointLight`

.. method:: feSpecularLighting.feSpotLight(source=(0, 0, 0), target=(0, 0, 0), **extra)

    :param source: source 3D point (**x**, **y**, **z**)
    :param target: target 3D point (**pointsAtX**, **pointsAtY**, **pointsAtZ**)

    create and add a light source: :ref:`feSpotLight`

SVG Attributes
--------------

.. tab:: 中文

    * **in** -- (请参见 :ref:`in <in_attr>` 属性)

    * **surfaceScale** -- `<number>`

        表示当 Ain = 1 时表面的高度。

        如果未指定此属性，则效果与指定值为 ``'1'`` 时相同。

    * **specularConstant** -- `<number>`

        Phong 光照模型中的 ks。在 SVG 中，这可以是任何非负数。

        如果未指定此属性，则效果与指定值为 ``'1'`` 时相同。

    * **specularExponent** -- `<number>`

        镜面反射项的指数，数值越大越“光亮”。范围为 1.0 到 128.0。

        如果未指定此属性，则效果与指定值为 ``'1'`` 时相同。

    * **kernelUnitLength** -- `<number-optional-number>`

        第一个数字是 `<dx>` 值，第二个数字是 `<dy>` 值。如果未指定 `<dy>` 值，则默认为与 `<dx>` 相同的值。
        指定当前滤镜单位（即根据 **primitiveUnits** 属性值确定的单位）中相邻列和行之间的距离，分别在 **kernelMatrix** 中。通过为 **kernelUnitLength** 指定值，内核可以在可缩放的抽象坐标系中定义。如果未指定 **kernelUnitLength**，则默认值是屏幕外位图中的一个像素，这是基于像素的坐标系，因此可能不可缩放。为了在显示媒体和用户代理之间实现某种一致性，必须为 **filterRes** 和 **kernelUnitLength** 至少提供一个值。在某些实现中，如果临时屏幕外图像的像素网格与内核的像素网格对齐，可能会获得最一致的结果和最快的性能。负值或零值是错误。

    * **lighting-color** -- ``'currentColor'`` | `<color>` [`<icccolor>`] | ``'inherit'``

        **lighting-color** 属性定义了 **feDiffuseLighting** 和 **feSpecularLighting** 滤镜原语的光源颜色。

.. tab:: 英文

    * **in** -- (see :ref:`in <in_attr>` attribute)

    * **surfaceScale** -- `<number>`

        height of surface when Ain = 1.

        If the attribute is not specified, then the effect is as if a value of ``'1'``
        were specified.

    * **specularConstant** -- `<number>`

        ks in Phong lighting model. In SVG, this can be any non-negative number.

        If the attribute is not specified, then the effect is as if a value of ``'1'``
        were specified.

    * **specularExponent** -- `<number>`

        Exponent for specular term, larger is more "shiny". Range 1.0 to 128.0.

        If the attribute is not specified, then the effect is as if a value of ``'1'``
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
