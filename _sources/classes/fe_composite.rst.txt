.. _feComposite:

feComposite 滤镜元素
==========================

feComposite Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feCompositeElement

.. tab:: 中文

  此滤镜执行两个输入图像在图像空间中的像素级组合，使用 Porter-Duff 合成操作之一： `over`、 `in`、 `atop`、 `out`、 `xor`。此外，还可以应用分量级的算术操作（结果被限制在 [0..1] 之间）。

  算术操作对于将 **feDiffuseLighting** 和 **feSpecularLighting** 滤镜的输出与纹理数据结合非常有用。它还可以用于实现溶解效果。如果选择算术操作，则每个结果像素使用以下公式计算：

    result = k1 * i1 * i2 + k2 * i1 + k3 * i2 + k4

  对于此滤镜原语，结果图像的范围可能会扩展，如描述滤镜原语子区域的部分所述。

  有关常见属性，请参见： :ref:`filter_primitive`

.. tab:: 英文

  This filter performs the combination of the two input images pixel-wise in image
  space using one of the Porter-Duff compositing operations: over, in, atop, out,
  xor. Additionally, a component-wise arithmetic operation (with the result clamped
  between [0..1]) can be applied.

  The arithmetic operation is useful for combining the output from the
  **feDiffuseLighting** and **feSpecularLighting** filters with texture data.
  It is also useful for implementing dissolve. If the arithmetic operation is
  chosen, each result pixel is computed using the following formula::

    result = k1*i1*i2 + k2*i1 + k3*i2 + k4

  For this filter primitive, the extent of the resulting image might grow as
  described in the section that describes the filter primitive subregion.

  For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

.. tab:: 中文

  * **in** -- (请参阅 :ref:`in <in_attr>` 属性)

  * **operator** -- ``'over | in | out | atop | xor | arithmetic'``

    要执行的合成操作。除算术运算符外，所有 **operator** 类型都对应 [PORTERDUFF] 中描述的操作。算术运算符如上所述。如果未指定 **operator** 属性，则效果相当于指定了值 ``'over'``。

  * **k1**, **k2**, **k3**, **k4** -- `<number>`

      仅在 **operator** = ``'arithmetic'`` 时适用。如果未指定此属性，则效果相当于指定了值 0。

  * **in2** -- (请参阅 :ref:`in <in_attr>` 属性)

      用于合成操作的第二个输入图像。此属性可以采用与 **in** 属性相同的值。

.. tab:: 英文

  * **in** -- (see :ref:`in <in_attr>` attribute)

  * **operator** -- ``'over | in | out | atop | xor | arithmetic``

    The compositing operation that is to be performed. All of the **operator**
    types except arithmetic match the correspond operation as described in [PORTERDUFF].
    The arithmetic operator is described above. If attribute **operator** is not
    specified, then the effect is as if a value of ``'over'`` were specified.

  * **k1**, **k2**, **k3**, **k4** -- `<number>`

      Only applicable if **operator** = ``'arithmetic'``.
      If the attribute is not specified, the effect is as if a value of 0 were specified.

  * **in2** -- (see :ref:`in <in_attr>` attribute)

      The second input image to the compositing operation. This attribute can
      take on the same values as the **in** attribute.

