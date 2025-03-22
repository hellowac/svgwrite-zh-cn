.. _feMerge:

feMerge 滤镜元素
======================

feMerge Filter Element

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feMergeElement

.. tab:: 中文

   此过滤原语通过使用 `over` 运算符将输入图像层叠加在一起，其中 `Input1`（对应第一个 **feMergeNode** 子元素）位于底部，最后指定的输入 `InputN`（对应最后一个 **feMergeNode** 子元素）位于顶部。

   许多效果会生成多个中间层，以创建最终的输出图像。这个过滤器允许我们将这些层合并成一个单一的图像。虽然这可以通过使用 n-1 个 Composite 过滤器来完成，但将这一常见操作以这种形式提供，更为方便，并且为实现提供了更多的灵活性。

   每个 **feMerge** 元素可以包含任意数量的 **feMergeNode** 子元素，每个子元素都有一个 **in** 属性。

   feMerge 的标准实现是将整个效果渲染到一个 RGBA 层中，然后将结果层渲染到输出设备上。在某些情况下（特别是当输出设备本身是一个连续色调设备时），由于合并是结合性的，因此逐层评估效果并将每一层从底部到顶部单独渲染到输出设备上，可能是一个足够的近似。

   如果最顶部的图像输入是 ``'SourceGraphic'`` 且此 **feMerge** 是最后一个过滤器原语，那么实现应该鼓励在此之前渲染各层，然后直接从其矢量描述中将 SourceGraphic 渲染到顶部。

   常见属性请参见：:ref:`filter_primitive`

   .. method:: Filter.feMerge(layernames, **extra)
      :noindex:

      :param list layernames: layernames 作为 `strings`

      创建一个 **feMerge** 过滤器，其中包含多个 **feMergeNode** 子元素，输入源由 **layernames** 指定。

.. tab:: 英文

   This filter primitive composites input image layers on top of each other using
   the over operator with `Input1` (corresponding to the first **feMergeNode** child
   element) on the bottom and the last specified input, `InputN` (corresponding to
   the last **feMergeNode** child element), on top.

   Many effects produce a number of intermediate layers in order to create the final
   output image. This filter allows us to collapse those into a single image.
   Although this could be done by using n-1 Composite-filters, it is more
   convenient to have this common operation available in this form, and
   offers the implementation some additional flexibility.

   Each **feMerge** element can have any number of **feMergeNode** subelements,
   each of which has an **in** attribute.

   The canonical implementation of feMerge is to render the entire effect into one
   RGBA layer, and then render the resulting layer on the output device. In certain
   cases (in particular if the output device itself is a continuous tone device),
   and since merging is associative, it might be a sufficient approximation to
   evaluate the effect one layer at a time and render each layer individually onto
   the output device bottom to top.

   If the topmost image input is ``'SourceGraphic'`` and this **feMerge** is the
   last filter primitive in the filter, the implementation is encouraged to render
   the layers up to that point, and then render the SourceGraphic directly from its
   vector description on top.

   For common properties see: :ref:`filter_primitive`

   .. method:: Filter.feMerge(layernames, **extra)
      :noindex:

      :param list layernames: layernames as `strings`

      Create a **feMerge** filter, containing several **feMergeNode** subelements,
      with the input sources specified by **layernames**.

Methods
-------

.. method:: feMerge.feMergeNode(layernames)

.. tab:: 中文

   :param list layernames: layernames 作为 `strings`

   添加多个 **feMergeNode** 子元素，输入源由 **layernames** 指定。

.. tab:: 英文

   :param list layernames: layernames as `strings`

   Add several **feMergeNode** subelements, with the input sources specified by
   **layernames**.
