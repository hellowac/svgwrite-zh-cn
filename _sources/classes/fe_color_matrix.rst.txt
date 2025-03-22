.. _feColorMatrix:

feColorMatrix 滤镜元素
============================

feColorMatrix Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feColorMatrixElement

For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

  * **in** -- (参见 :ref:`in <in_attr>` 属性)

  * **type** -- ``'matrix | saturate | hueRotate | luminanceToAlpha'``

    指定矩阵操作的类型。关键字 **matrix** 表示将提供一个完整的 5x4 矩阵值。其他关键字是便捷的快捷方式，允许执行常用的颜色操作，而无需指定完整的矩阵。如果未指定 **type** 属性，则效果就像指定了 **matrix** 的值。

  * **values** = `数字列表`

    **values** 的内容取决于 **type** 属性的值，详见：http://www.w3.org/TR/SVG11/filters.html#feColorMatrixValuesAttribute

.. tab:: 英文

  * **in** -- (see :ref:`in <in_attr>` attribute)

  * **type** -- ``'matrix | saturate | hueRotate | luminanceToAlpha'``

    Indicates the type of matrix operation. The keyword **matrix** indicates
    that a full 5x4 matrix of values will be provided. The other keywords
    represent convenience shortcuts to allow commonly used color operations to
    be performed without specifying a complete matrix. If attribute **type**
    is not specified, then the effect is as if a value of matrix were specified.

  * **values** = `list of <number>s`

    The contents of **values** depends on the value of attribute **type** see:
    http://www.w3.org/TR/SVG11/filters.html#feColorMatrixValuesAttribute



