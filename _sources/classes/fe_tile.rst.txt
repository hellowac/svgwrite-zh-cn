.. _feTile:

feTile 滤镜元素
=======================

feTile Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feTileElement

.. tab:: 中文

    此滤镜原语使用输入图像的重复拼贴图案填充目标矩形。目标矩形的大小与在 **feTile** 元素上由 **x**、 **y**、 **width** 和 **height** 属性建立的滤镜原语子区域相同。

    通常，输入图像已使用其自身的滤镜原语子区域来定义参考瓦片。 **feTile** 将在X和Y方向上复制该参考瓦片，以完全填充目标矩形。每个瓦片的左上角位置为 (x+i*width, y+j*height)，其中(x, y) 表示输入图像滤镜原语子区域的左上角，width和height表示输入图像滤镜原语子区域的宽度和高度，而i和j可以是任何整数值。在大多数情况下，输入图像的滤镜原语子区域将比 **feTile** 的子区域小，从而实现重复图案效果。

    实现者在构建拼贴图像时必须采取适当的措施，以避免瓦片之间的伪影，尤其是在用户到设备的变换包括剪切和/或旋转的情况下。如果不小心，插值可能导致瓦片的边缘像素具有比预期更低或更高的透明度值，这是由于相邻瓦片的绘制相互重叠而导致的，特别是在某些像素处。

    有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

    This filter primitive fills a target rectangle with a repeated, tiled pattern of
    an input image. The target rectangle is as large as the filter primitive subregion
    established by the **x**, **y**, **width** and **height** attributes on the
    **feTile** element.

    Typically, the input image has been defined with its own filter primitive
    subregion in order to define a reference tile. **feTile** replicates the
    reference tile in both X and Y to completely fill the target rectangle. The
    top/left corner of each given tile is at location (x+i*width,y+j*height),
    where (x,y) represents the top/left of the input image's filter primitive
    subregion, width and height represent the width and height of the input
    image's filter primitive subregion, and i and j can be any integer value.
    In most cases, the input image will have a smaller filter primitive subregion
    than the **feTile** in order to achieve a repeated pattern effect.

    Implementers must take appropriate measures in constructing the tiled image to
    avoid artifacts between tiles, particularly in situations where the user to
    device transform includes shear and/or rotation. Unless care is taken,
    interpolation can lead to edge pixels in the tile having opacity values lower or
    higher than expected due to the interaction of painting adjacent tiles which
    each have partial overlap with particular pixels.

    For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

* **in** -- (see :ref:`in <in_attr>` attribute)
