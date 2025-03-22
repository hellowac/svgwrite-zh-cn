.. _filter_primitive:

滤镜原语概述
==========================
Filter Primitives Overview

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#FilterPrimitivesOverview

.. tab:: 中文

  除非另有说明，所有图像滤镜都作用于预乘RGBA样本。对于那些在非预乘数据上更自然工作的滤镜（如 **feColorMatrix** 和 **feComponentTransfer**），会临时撤销和重新执行预乘操作，按照规定进行。所有光栅效果的过滤操作接受 1 到 N 个输入 RGBA 图像，额外的属性作为参数，并生成单个输出 RGBA 图像。

  每个滤镜原语的 RGBA 结果将被限制在颜色和透明度值的允许范围内。因此，例如，来自某个滤镜原语的结果会将任何负值的颜色值或透明度值调整为零（颜色/透明度）。

  特定滤镜原语执行其操作的颜色空间由给定滤镜原语上的 **color-interpolation-filters** 属性的值决定。另一个属性， **color-interpolation**，决定其他颜色操作的颜色空间。因为这两个属性具有不同的初始值（ **color-interpolation-filters** 的初始值为 linearRGB，而 **color-interpolation** 的初始值为 sRGB），在某些情况下，为了实现特定的结果（例如，在与滤镜操作协调渐变插值时），可能需要显式地将 **color-interpolation** 设置为 linearRGB 或将 **color-interpolation-filters** 设置为 sRGB。请注意，下面的示例没有显式地设置 **color-interpolation** 或 **color-interpolation-filters**，因此这些属性的初始值适用于示例。

.. tab:: 英文


  Unless otherwise stated, all image filters operate on premultiplied RGBA
  samples. Filters which work more naturally on non-premultiplied data
  (feColorMatrix and feComponentTransfer) will temporarily undo and redo
  premultiplication as specified. All raster effect filtering operations take
  1 to N input RGBA images, additional attributes as parameters, and produce a
  single output RGBA image.

  The RGBA result from each filter primitive will be clamped into the allowable
  ranges for colors and opacity values. Thus, for example, the result from a
  given filter primitive will have any negative color values or opacity values
  adjusted up to color/opacity of zero.

  The color space in which a particular filter primitive performs its operations
  is determined by the value of property **color-interpolation-filters** on the
  given filter primitive. A different property, **color-interpolation** determines
  the color space for other color operations. Because these two properties have
  different initial values (**color-interpolation-filters** has an initial value
  of linearRGB whereas **color-interpolation** has an initial value of sRGB),
  in some cases to achieve certain results (e.g., when coordinating gradient
  interpolation with a filtering operation) it will be necessary to explicitly
  set **color-interpolation** to linearRGB or **color-interpolation-filters**
  to sRGB on particular elements. Note that the examples below do not explicitly
  set either **color-interpolation** or **color-interpolation-filters**, so the
  initial values for these properties apply to the examples.

滤镜原语的通用svg属性
===========================================

Common SVG Attributes for Filter Primitives

.. tab:: 中文

  除了 **in** 属性之外，以下所有属性都可用于所有滤镜原语元素：

  * **x** -- `<coordinate>`

    给定滤镜原语的子区域的最小 x 坐标，用于限制该滤镜原语的计算和渲染。请参阅滤镜原语子区域。

  * **y** -- `<coordinate>`

    给定滤镜原语的子区域的最小 y 坐标，用于限制该滤镜原语的计算和渲染。请参阅滤镜原语子区域。

  * **width** -- `<length>`

    给定滤镜原语的子区域的宽度，用于限制该滤镜原语的计算和渲染。请参阅滤镜原语子区域。

  * **height** -- `<length>`

    给定滤镜原语的子区域的高度，用于限制该滤镜原语的计算和渲染。请参阅滤镜原语子区域。

  * **result** -- `<filter-primitive-reference>`

    为该滤镜原语分配的名称。如果提供该属性，则通过处理该滤镜原语产生的图形可以通过同一 **filter** 元素中的后续滤镜原语的 **in** 属性进行引用。如果没有提供值，则输出仅在下一个滤镜原语没有为其 **in** 属性提供值的情况下，作为隐式输入重新用于该滤镜原语。

.. tab:: 英文

  With the exception of the **in** attribute, all of the following attributes
  are available on all filter primitive elements:

  * **x** -- `<coordinate>`

    The minimum x coordinate for the subregion which restricts calculation and
    rendering of the given filter primitive. See filter primitive subregion.

  * **y** -- `<coordinate>`

    The minimum y coordinate for the subregion which restricts calculation and
    rendering of the given filter primitive. See filter primitive subregion.

  * **width** -- `<length>`

    The width of the subregion which restricts calculation and rendering of the
    given filter primitive. See filter primitive subregion.

  * **height** -- `<length>`

    The height of the subregion which restricts calculation and rendering of
    the given filter primitive. See filter primitive subregion.

  * **result** -- `<filter-primitive-reference>`

    Assigned name for this filter primitive. If supplied, then graphics that
    result from processing this filter primitive can be referenced by an **in**
    attribute on a subsequent filter primitive within the same **filter** element.
    If no value is provided, the output will only be available for re-use as
    the implicit input into the next filter primitive if that filter primitive
    provides no value for its **in** attribute.

.. _in_attr:

.. tab:: 中文

  * **in** -- ``'SourceGraphic | SourceAlpha | BackgroundImage | BackgroundAlpha | FillPaint | StrokePaint'`` | `<filter-primitive-reference>`

    标识给定滤镜原语的输入。值可以是六个关键字之一，或者是与同一 **filter** 元素中之前的 **result** 属性值匹配的字符串。如果没有提供值，并且这是第一个滤镜原语，则该滤镜原语将使用 ``'SourceGraphic'`` 作为其输入。如果没有提供值，并且这是后续滤镜原语，则该滤镜原语将使用上一个滤镜原语的结果作为输入。

    * **SourceGraphic**

      此关键字表示作为 **filter** 元素的原始输入的图形元素。对于光栅效果滤镜原语，图形元素将被光栅化为初始透明的 RGBA 光栅图像（图像空间）。未被原始图形触及的像素将保持透明。图像被指定为在线性 RGBA 像素中呈现。此图像的 alpha 通道捕获了 SVG 中指定的任何抗锯齿效果。（由于光栅是线性的，此图像的 alpha 通道将表示每个像素的实际覆盖百分比。）

    * **SourceAlpha**

      此关键字表示作为 **filter** 元素的原始输入的图形元素。SourceAlpha 与 SourceGraphic 具有相同的规则，唯一的区别是仅使用 alpha 通道。输入图像是一个 RGBA 图像，其中 RGB 通道的颜色值默认为黑色，但其 alpha 通道与 SourceGraphic 相同。如果使用此选项，则某些实现可能需要将图形元素光栅化以提取 alpha 通道。

    * **BackgroundImage**

      此关键字表示 **filter** 元素被调用时，在滤镜区域下的画布图像快照。请参阅访问背景图像。

    * **BackgroundAlpha**

      与 BackgroundImage 相同，但仅使用 alpha 通道。请参阅 SourceAlpha 和访问背景图像。

    * **FillPaint**

      此关键字表示目标元素上 **fill** 属性的值，用于滤镜效果。FillPaint 图像在概念上具有无限的扩展性。通常，此图像在所有区域都是不透明的，但如果 `"paint"` 本身具有 alpha 值（例如，渐变或图案），则该图像可能在某些区域具有透明或半透明部分。

    * **StrokePaint**

      此关键字表示目标元素上 **stroke** 属性的值，用于滤镜效果。StrokePaint 图像在概念上具有无限的扩展性。通常，此图像在所有区域都是不透明的，但如果 `"paint"` 本身具有 alpha 值（例如，渐变或图案），则该图像可能在某些区域具有透明或半透明部分。

.. tab:: 英文

  * **in** -- ``'SourceGraphic | SourceAlpha | BackgroundImage | BackgroundAlpha
    | FillPaint | StrokePaint'`` | `<filter-primitive-reference>`

    Identifies input for the given filter primitive. The value can be either
    one of six keywords or can be a string which matches a previous **result**
    attribute value within the same **filter** element. If no value is provided
    and this is the first filter primitive, then this filter primitive will use
    ``'SourceGraphic'`` as its input. If no value is provided and this is a subsequent
    filter primitive, then this filter primitive will use the result from the
    previous filter primitive as its input.

    * **SourceGraphic**

      This keyword represents the graphics elements that were the original input
      into the **filter** element. For raster effects filter primitives, the
      graphics elements will be rasterized into an initially clear RGBA raster
      in image space. Pixels left untouched by the original graphic will be left
      clear. The image is specified to be rendered in linear RGBA pixels. The
      alpha channel of this image captures any anti-aliasing specified by SVG.
      (Since the raster is linear, the alpha channel of this image will represent
      the exact percent coverage of each pixel.)

    * **SourceAlpha**

      This keyword represents the graphics elements that were the original
      input into the **filter** element. SourceAlpha has all of the same rules
      as SourceGraphic except that only the alpha channel is used. The input
      image is an RGBA image consisting of implicitly black color values for
      the RGB channels, but whose alpha channel is the same as SourceGraphic.
      If this option is used, then some implementations might need to rasterize
      the graphics elements in order to extract the alpha channel.

    * **BackgroundImage**

      This keyword represents an image snapshot of the canvas under the filter
      region at the time that the **filter** element was invoked. See Accessing
      the background image.

    * **BackgroundAlpha**

      Same as BackgroundImage except only the alpha channel is used. See
      SourceAlpha and Accessing the background image.

    * **FillPaint**

      This keyword represents the value of the **fill** property on the target
      element for the filter effect. The FillPaint image has conceptually
      infinite extent. Frequently this image is opaque everywhere, but it might
      not be if the `"paint"` itself has alpha, as in the case of a gradient or
      pattern which itself includes transparent or semi-transparent parts.

    * **StrokePaint**

      This keyword represents the value of the **stroke** property on the target
      element for the filter effect. The StrokePaint image has conceptually
      infinite extent. Frequently this image is opaque everywhere, but it might
      not be if the `"paint"` itself has alpha, as in the case of a gradient or
      pattern which itself includes transparent or semi-transparent parts.
