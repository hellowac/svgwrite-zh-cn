.. _feFlood:

feFlood 滤镜元素
======================

feFlood Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feFloodElement

.. tab:: 中文

  这个滤镜原语创建一个矩形，并填充来自 **flood-color** 和 **flood-opacity** 属性的颜色和不透明度值。该矩形的大小与 **feFlood** 元素上 **x**、 **y**、 **width** 和 **height** 属性所设定的滤镜原语子区域相同。

  有关常见属性，请参见：:ref:`filter_primitive`

.. tab:: 英文

  This filter primitive creates a rectangle filled with the color and opacity
  values from properties **flood-color** and **flood-opacity**. The rectangle is
  as large as the filter primitive subregion established by the **x**, **y**,
  **width** and **height** attributes on the **feFlood** element.

  For common properties see: :ref:`filter_primitive`

SVG Attributes
--------------

* **flood-color** -- ``'currentColor'`` | `<color>` [`<icccolor>`] | ``' inherit'``

  initial value is ``'black'``

* **flood-opacity** -- 	`<opacity-value>` | ``'inherit'``

  initial value is ``'1'``