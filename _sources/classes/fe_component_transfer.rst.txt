.. _feComponentTransfer:

feComponentTransfer 滤镜元素
==================================

feComponentTransfer Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feComponentTransferElement

.. tab:: 中文

  这个滤镜原语对数据进行分量级的重新映射：

    R' = feFuncR( R )
    G' = feFuncG( G )
    B' = feFuncB( B )
    A' = feFuncA( A )

  对每个像素进行操作。它允许执行诸如亮度调整、对比度调整、颜色平衡或阈值处理等操作。

  计算在非预乘的颜色值上进行。如果输入图形是预乘的颜色值，这些值会在此操作中自动转换为非预乘的颜色值。（请注意，如果 feFuncA 是恒等变换并且源图形的所有 alpha 值都设置为 1，则可以避免撤销和重新进行预乘操作。）

  有关常见属性，请参见： :ref:`filter_primitive`

.. tab:: 英文

  This filter primitive performs component-wise remapping of data::

    R' = feFuncR( R )
    G' = feFuncG( G )
    B' = feFuncB( B )
    A' = feFuncA( A )

  for every pixel. It allows operations like brightness adjustment, contrast
  adjustment, color balance or thresholding.

  The calculations are performed on non-premultiplied color values. If the
  input graphics consists of premultiplied color values, those values are
  automatically converted into non-premultiplied color values for this operation.
  (Note that the undoing and redoing of the premultiplication can be avoided if
  feFuncA is the identity transform and all alpha values on the source graphic
  are set to 1.)

  For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

* **in** -- (see :ref:`in <in_attr>` attribute)

Methods
-------

.. method:: feFuncR(type_, \*\*extra)

   create and add a transfer function for the **red** component of the input graphic

.. method:: feFuncG(type_, \*\*extra)

   create and add a transfer function for the **green** component of the input graphic

.. method:: feFuncB(type_, \*\*extra)

   create and add a transfer function for the **blue** component of the input graphic

.. method:: feFuncA(type_, \*\*extra)

   create and add a transfer function for the **alpha** component of the input graphic

Parameters for feFuncX() Methods
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **type** -- ``'identity | table | discrete | linear | gamma'``

  see: http://www.w3.org/TR/SVG11/filters.html#feComponentTransferTypeAttribute

* **tableValues** -- `(list of <number>s)`

  When **type** = ``'table'``, the list of `<number>s` v0,v1,...vn, separated
  by white space and/or a comma, which define the lookup table. An empty list
  results in an identity transfer function.

* **slope** -- `<number>`

  When **type** = ``'linear'``, the slope of the linear function.

* **intercept** -- `<number>`

  When **type** = ``'linear'``, the intercept of the linear function.

* **amplitude** -- `<number>`

  When **type** = ``'gamma'``, the amplitude of the gamma function.

* **exponent** -- `<number>`

  When **type** = ``'gamma'``, the exponent of the gamma function.

* **offset** -- `<number>`

  When **type** = ``'gamma'``, the offset of the gamma function.
