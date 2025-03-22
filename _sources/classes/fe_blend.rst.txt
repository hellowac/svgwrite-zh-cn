.. _feBlend:

feBlend 滤镜元素
======================

feBlend Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feBlendElement

.. tab:: 中文

  此滤镜使用常用的图像处理软件混合模式将两个对象合成在一起。它执行对两个输入图像的逐像素组合。

  有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

  This filter composites two objects together using commonly used imaging
  software blending modes. It performs a pixel-wise combination of two input
  images.

  For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文



.. tab:: 英文


* **mode** -- ``'normal | multiply | screen | darken | lighten'``

  One of the image blending modes. If attribute **mode** is not specified,
  then the effect is as if a value of ``'normal'`` were specified.

  see also: http://www.w3.org/TR/SVG11/filters.html#feBlendModeAttribute

* **in** -- (see :ref:`in <in_attr>` attribute)

* **in2** -- (see :ref:`in <in_attr>` attribute)

  The second input image to the blending operation. This attribute can take
  on the same values as the **in** attribute.
