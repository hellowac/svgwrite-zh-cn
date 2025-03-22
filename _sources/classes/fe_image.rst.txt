.. _feImage:

feImage 滤镜元素
======================

feImage Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feImageElement

.. tab:: 中文

    这个滤镜原语引用了此滤镜元素外部的图形，该图形被加载或呈现为一个 RGBA 光栅，并成为滤镜原语的结果。

    这个滤镜原语可以引用外部图像，也可以是对另一个 SVG 片段的引用。它产生的图像类似于内建的图像源 ``'SourceGraphic'``，不同之处在于图形来自外部源。

    如果 **xlink:href** 引用的是独立的图像资源（如 JPEG、PNG 或 SVG 文件），那么该图像资源会根据 **image** 元素的行为呈现；否则，引用的资源会根据 **use** 元素的行为呈现。在任何情况下，当前的用户坐标系统都取决于 **filter** 元素上的 **primitiveUnits** 属性的值。 **feImage** 元素上 **preserveAspectRatio** 属性的处理方式与 **image** 元素的处理方式相同。

    当引用的图像需要重新采样以匹配设备坐标系统时，建议高质量的查看器使用适当的插值技术，例如双线性或三次插值。根据可用插值器的速度，这个选择可能会受到 **image-rendering** 属性设置的影响。

    对于常见属性，参见： :ref:`filter_primitive`

.. tab:: 英文

    This filter primitive refers to a graphic external to this filter element, which
    is loaded or rendered into an RGBA raster and becomes the result of the filter
    primitive.

    This filter primitive can refer to an external image or can be a reference to
    another piece of SVG. It produces an image similar to the built-in image source
    ``'SourceGraphic'`` except that the graphic comes from an external source.

    If the **xlink:href** references a stand-alone image resource such as a
    JPEG, PNG or SVG file, then the image resource is rendered according to the
    behavior of the **image** element; otherwise, the referenced resource is rendered
    according to the behavior of the **use** element. In either case, the current
    user coordinate system depends on the value of attribute **primitiveUnits** on
    the **filter** element. The processing of the **preserveAspectRatio** attribute
    on the **feImage** element is identical to that of the **image** element.

    When the referenced image must be resampled to match the device coordinate system,
    it is recommended that high quality viewers make use of appropriate interpolation
    techniques, for example bilinear or bicubic. Depending on the speed of the
    available interpolents, this choice may be affected by the **image-rendering**
    property setting.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

    * **xlink:href** -- `<iri>`

        指向图像源的 IRI 引用。

    * **preserveAspectRatio** -- ``'[defer] <align> [<meetOrSlice>]'``

        如果未指定 **preserveAspectRatio** 属性，则其效果等同于指定了 ``'xMidYMid'`` meet 的值。

.. tab:: 英文

    * **xlink:href** -- `<iri>`

        A IRI reference to the image source.

    * **preserveAspectRatio** -- ``'[defer] <align> [<meetOrSlice>]'``

        If attribute **preserveAspectRatio** is not specified, then the effect is
        as if a value of ``'xMidYMid'`` meet were specified.