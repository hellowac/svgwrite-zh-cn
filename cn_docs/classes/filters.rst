Introduction
============

.. tab:: 中文

   本章介绍了SVG的声明式滤镜效果功能集，当与SVG的二维图形能力结合时，可以以一种方式描述Web上常见的许多艺术作品，使得客户端生成和修改变得容易。此外，将滤镜效果应用于SVG图形元素和容器元素，有助于保持文档的语义结构，而不是使用图像，因为图像通常具有固定的分辨率，并且往往会掩盖它们所替代元素的原始语义。这在应用于文本的效果时尤为显著。

   滤镜效果是通过 **filter** 元素定义的。要将滤镜效果应用于 **图形元素** 或 **容器元素** ，您需要在给定元素上设置 **filter** 属性的值，使其引用滤镜效果。

.. tab:: 英文

   This chapter describes SVG's declarative filter effects feature set, which
   when combined with the 2D power of SVG can describe much of the common
   artwork on the Web in such a way that client-side generation and alteration
   can be performed easily. In addition, the ability to apply filter effects to
   SVG graphics elements and container elements helps to maintain the semantic
   structure of the document, instead of resorting to images which aside from
   generally being a fixed resolution tend to obscure the original semantics
   of the elements they replace. This is especially true for effects applied to
   text.

   Filter effects are defined by **filter** elements. To apply a filter effect
   to a **graphics element** or a **container element**, you set the value of
   the **filter** property on the given element such that it references the
   filter effect.

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#Introduction

Filter Element
==============

.. autoclass:: svgwrite.filters.Filter

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#FilterElement

Parent Classes
--------------

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.mixins.Presentation`

Methods
-------

.. automethod:: svgwrite.filters.Filter.__init__

.. method:: Filter.feBlend(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feBlend`

.. method:: Filter.feColorMatrix(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feColorMatrix`

.. method:: Filter.feComponentTransfer(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feComponentTransfer`

.. method:: Filter.feComposite(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feComposite`

.. method:: Filter.feConvolveMatrix(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feConvolveMatrix`

.. method:: Filter.feDiffuseLighting(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feDiffuseLighting`

.. method:: Filter.feDisplacementMap(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feDisplacementMap`

.. method:: Filter.feFlood(start=None, size=None, \*\*extra)

   create and add a :ref:`feFlood`

.. method:: Filter.feGaussianBlur(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feGaussianBlur`

.. method:: Filter.feImage(href, start=None, size=None, \*\*extra)

   create and add a :ref:`feImage`

.. method:: Filter.feMerge(start=None, size=None, \*\*extra)

   create and add a :ref:`feMerge`

.. method:: Filter.feMorphology(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feMorphology`

.. method:: Filter.feOffset(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feOffset`

.. method:: Filter.feSpecularLighting(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feSpecularLighting`

.. method:: Filter.feTile(in_, start=None, size=None, \*\*extra)

   create and add a :ref:`feTile`

.. method:: Filter.feTurbulence(start=None, size=None, \*\*extra)

   create and add a :ref:`feTurbulence`

SVG Attributes
--------------

.. tab:: 中文

  * **filterUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **primitiveUnits** -- ``'userSpaceOnUse | objectBoundingBox'``  
    指定滤镜原语内部各种长度值的坐标系统，以及定义滤镜原语子区域的属性。

    如果 **primitiveUnits** = ``'userSpaceOnUse'``，则滤镜定义中的任何长度值都代表当前用户坐标系统中的值，这个坐标系统在引用 **filter** 元素时存在（即引用 **filter** 元素的元素的用户坐标系统，通过 **filter** 属性引用）。

    如果 **primitiveUnits** = ``'objectBoundingBox'``，则滤镜定义中的任何长度值都代表引用元素的边界框的分数或百分比（参见对象边界框单位）。请注意，如果在 `<number-optional-number>` 值中只指定了一个数字，那么这个数字会在进行 **primitiveUnits** 计算之前进行扩展。

    如果没有指定 **primitiveUnits** 属性，则效果相当于指定了``'userSpaceOnUse'``。

  * **x** -- `<coordinate>` -- **start** 参数

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **y** -- `<coordinate>` -- **start** 参数

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **width** -- `<length>` -- **size** 参数

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **height** -- `<length>` -- **size** 参数

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **filterRes** -- `<number-optional-number>` -- **resolution** 参数

    参见 `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **xlink:href** -- `<iri>` -- **inherit** 参数

    指向当前SVG文档片段中另一个 **filter** 元素的IRI引用。任何在引用的 **filter** 元素中定义，但在此元素中未定义的属性，都将由此元素继承。

.. tab:: 英文

  * **filterUnits** -- ``'userSpaceOnUse | objectBoundingBox'``

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **primitiveUnits** -- ``'userSpaceOnUse | objectBoundingBox'``
    Specifies the coordinate system for the various length values within the
    filter primitives and for the attributes that define the filter primitive
    subregion.

    If **primitiveUnits** = ``'userSpaceOnUse'``, any length values within the
    filter definitions represent values in the current user coordinate system
    in place at the time when the **filter** element is referenced (i.e., the
    user coordinate system for the element referencing the **filter** element
    via a **filter** property).

    If **primitiveUnits** = ``'objectBoundingBox'``, then any length values
    within the filter definitions represent fractions or percentages of the
    bounding box on the referencing element (see Object bounding box units).
    Note that if only one number was specified in a `<number-optional-number>`
    value this number is expanded out before the **primitiveUnits** computation
    takes place.

    If attribute **primitiveUnits** is not specified, then the effect is as if
    a value of ``'userSpaceOnUse'`` were specified.

  * **x** -- `<coordinate>` -- **start** parameter

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **y** -- `<coordinate>` -- **start** parameter

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **width** -- `<length>` -- **size** parameter

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **height** -- `<length>` -- **size** parameter

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **filterRes** -- `<number-optional-number>` -- **resolution** parameter

    See `Filter effects region. <http://www.w3.org/TR/SVG11/filters.html#FilterEffectsRegion>`_

  * **xlink:href** -- `<iri>` -- **inherit** parameter

    A IRI reference to another **filter** element within the current SVG document
    fragment. Any attributes which are defined on the referenced **filter** element
    which are not defined on this element are inherited by this element.

Standard SVG Attributes
-----------------------

* :doc:`Core Attributes </attributes/core>`
* :doc:`Presentation Attributes </attributes/presentation>`
* :doc:`XLink Attributes </attributes/xlink>`

Example
-------

Source: https://secure.wikimedia.org/wikibooks/de/wiki/SVG/_Effekte#Urfilter_fePointLight.2C_Punktlichtquelle

.. literalinclude:: ../../examples/fePointLight.py
   :lines: 8-

and the XML result (with manual reformatting):

.. code-block:: xml

  <?xml version="1.0" encoding="utf-8" ?>
  <svg baseProfile="full" height="100%" version="1.1" width="100%"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:ev="http://www.w3.org/2001/xml-events"
    xmlns:xlink="http://www.w3.org/1999/xlink">
      <defs>
          <filter id="DL" filterUnits="userSpaceOnUse"
            x="0" y="0" width="500" height="500" >
              <feDiffuseLighting diffuseConstant="1"
                x="0" y="0" width="500" height="500"
                in="SourceGraphic"
                kernelUnitLength="1"
                lighting-color="#f8f"
                surfaceScale="10">
                  <fePointLight x="500" y="250" z="250">
                      <animate attributeName="x"
                        dur="30s"
                        repeatDur="indefinite"
                        values="0;100;500;100;0" />
                      <animate attributeName="y"
                        dur="31s"
                        repeatDur="indefinite"
                        values="0;500;400;-100;0" />
                      <animate attributeName="z"
                        dur="37s"
                        repeatDur="indefinite"
                        values="0;1000;500;-100;0" />
                  </fePointLight>
              </feDiffuseLighting>
          </filter>
      </defs>
  </svg>