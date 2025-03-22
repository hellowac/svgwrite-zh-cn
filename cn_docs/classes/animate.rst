animate 模块
==============

animate module

.. tab:: 中文

  由于 Web 是一种动态媒介，因此 SVG 支持随时间改变矢量图形的能力。

.. tab:: 英文

  Because the Web is a dynamic medium, SVG supports the ability to change
  vector graphics over time.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html

Set
===

.. autoclass:: svgwrite.animate.Set

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#SetElement

Parent Classes
--------------

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`

Methods
-------

.. automethod:: svgwrite.animate.Set.__init__

.. method:: Animate.set_href(element)

  :param element: set target svg element to `element`

.. automethod:: svgwrite.animate.Animate.set_target

.. automethod:: svgwrite.animate.Animate.set_event

.. automethod:: svgwrite.animate.Animate.set_timing

.. automethod:: svgwrite.animate.Animate.freeze

SVG 动画属性
------------------------

SVG Animation Attributes

.. tab:: 中文

  * onbegin、onend、onrepeat、onload (:doc:`动画事件属性 </attributes/animation_events>`)
  * attributeType、attributeName (:doc:`动画目标属性 </attributes/animation_target>`)
  * begin、dur、end、min、max、restart、repeatCount、repeatDur、fill (:doc:`动画计时属性 </attributes/animation_timing>`)

.. tab:: 英文

  * onbegin, onend, onrepeat, onload (:doc:`Animation Event Attributes </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`Animation Target Attributes </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`Animation Timing Attributes </attributes/animation_timing>`)

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **externalResourcesRequired** -- `bool`

    `False`：如果外部资源不可用，文档渲染仍然可以继续；否则： `True`。

  * **to** -- `<value>`

    指定在 **set** 元素持续时间内该属性的值。参数值必须与属性类型匹配。

.. tab:: 英文


  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **to** -- `<value>`
    Specifies the value for the attribute during the duration of the **set**
    element. The argument value must match the attribute type.

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`XLink Attributes </attributes/xlink>`

AnimateMotion
=============

.. autoclass:: svgwrite.animate.AnimateMotion

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AnimateMotionElement

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.animate.Set`

方法
-------

Methods

.. automethod:: svgwrite.animate.AnimateMotion.__init__

.. automethod:: svgwrite.animate.AnimateMotion.set_value

SVG 动画属性
------------------------

SVG Animation Attributes

.. tab:: 中文

  * onbegin、onend、onrepeat、onload (:doc:`动画事件属性 </attributes/animation_events>`)
  * begin、dur、end、min、max、restart、repeatCount、repeatDur、fill (:doc:`动画计时属性 </attributes/animation_timing>`)
  * calcMode、values、keyTimes、keySplines、from、to、by (:doc:`动画值属性 </attributes/animation_value>`)
  * addition、accumulate (:doc:`动画添加属性 </attributes/animation_addition>`)

.. tab:: 英文


  * onbegin, onend, onrepeat, onload (:doc:`Animation Event Attributes </attributes/animation_events>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`Animation Timing Attributes </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`Animation Value Attributes </attributes/animation_value>`)
  * additive, accumulate (:doc:`Animation Addition Attributes </attributes/animation_addition>`)

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **externalResourcesRequired** -- `bool`

    `False`：如果外部资源不可用，文档渲染仍然可以继续；否则：`True`。

  * **calcMode** -- ``'discrete | linear | paced | spline'``

    指定动画的插值模式。

  * **path** -- `<path-data>` -- **path** 参数

    运动路径，以与 **Path** 元素的 :ref:`d <pathCommands>` 属性相同的格式表示，并以相同方式解释。运动路径动画的效果是将一个附加的转换矩阵添加到目标对象的 CTM 中，从而在当前用户坐标系统的 x 轴和 y 轴上进行平移，平移的 X 和 Y 值是根据时间计算得出的。

  * **keyPoints** -- `<list-of-numbers>`

    **keyPoints** 接受一个用分号分隔的浮动值列表，值范围在 0 到 1 之间，表示在由对应的 **keyTimes** 值指定的时间点上，物体在运动路径上移动的距离。距离计算使用用户代理的路径上距离算法。列表中的每个进度值对应于 **keyTimes** 属性列表中的一个值。

    如果指定了 **keyPoints** 列表，则 **keyPoints** 列表中的值必须与 **keyTimes** 列表中的值数量相同。

    如果 **keyPoints** 指定有任何错误（错误值、值太多或太少），则文档会出错。

  * **rotate** -- `<number>` | ``'auto'`` | ``'auto-reverse'``

    **rotate** 属性会将一个附加的转换矩阵后乘到目标元素的 CTM 中，以便在当前用户坐标系统的原点周围应用旋转转换。旋转转换在由于 **path** 属性计算出的附加平移转换之后应用。

    * ``'auto'``

      表示物体随着时间变化根据运动路径的方向（即方向切线向量）旋转。

    * ``'auto-reverse'``

      表示物体随着时间变化根据运动路径的方向（即方向切线向量）旋转，并加上 180 度。

    * `<number>`

      表示目标元素应用一个恒定的旋转转换，旋转角度为指定的度数。

      默认值为 ``'0'``。

.. tab:: 英文


  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **calcMode** -- ``'discrete | linear | paced | spline'``

    Specifies the interpolation mode for the animation.

  * **path** -- `<path-data>` -- **path** parameter

    The motion path, expressed in the same format and interpreted the same way
    as the :ref:`d <pathCommands>` attribute on the **Path** element.
    The effect of a motion path animation is to add a supplemental
    transformation matrix onto the CTM for the referenced object which causes a
    translation along the x- and y-axes of the current user coordinate system
    by the computed X and Y values computed over time.

  * **keyPoints** -- `<list-of-numbers>`

    **keyPoints** takes a semicolon-separated list of floating point values
    between 0 and 1 and indicates how far along the motion path the object
    shall move at the moment in time specified by corresponding **keyTimes**
    value. Distance calculations use the user agent's distance along the path
    algorithm. Each progress value in the list corresponds to a value in the
    **keyTimes** attribute list.

    If a list of **keyPoints** is specified, there must be exactly as many
    values in the **keyPoints** list as in the **keyTimes** list.

    If there are any errors in the **keyPoints** specification (bad values,
    too many or too few values), then the document is in error.

  * **rotate** -- `<number>` | ``'auto'`` | ``'auto-reverse'``

    The **rotate** attribute post-multiplies a supplemental transformation
    matrix onto the CTM of the target element to apply a rotation
    transformation about the origin of the current user coordinate system.
    The rotation transformation is applied after the supplemental translation
    transformation that is computed due to the **path** attribute.

    * ``'auto'``

      Indicates that the object is rotated over time by the angle of the
      direction (i.e., directional tangent vector) of the motion path.

    * ``'auto-reverse'``

      Indicates that the object is rotated over time by the angle of the
      direction (i.e., directional tangent vector) of the motion path plus
      180 degrees.

    * `<number>`

      Indicates that the target element has a constant rotation transformation
      applied to it, where the rotation angle is the specified number of
      degrees.

      Default value is ``'0'``.

* **origin** -- ``'default'``

  The **origin** attribute is defined in the
  `SMIL Animation specification <http://www.w3.org/TR/2001/REC-smil-animation-20010904/#MotionOriginAttribute>`_

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`XLink Attributes </attributes/xlink>`

Animate
=======

.. autoclass:: svgwrite.animate.Animate

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AnimateElement

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.animate.Set`

方法
-------

Methods

.. automethod:: svgwrite.animate.Animate.__init__

.. automethod:: svgwrite.animate.Animate.set_value

SVG 动画属性
------------------------

SVG Animation Attributes

.. tab:: 中文

  * onbegin、onend、onrepeat、onload (:doc:`动画事件属性 </attributes/animation_events>`)
  * attributeType、attributeName (:doc:`动画目标属性 </attributes/animation_target>`)
  * begin、dur、end、min、max、restart、repeatCount、repeatDur、fill (:doc:`动画计时属性 </attributes/animation_timing>`)
  * calcMode、values、keyTimes、keySplines、from、to、by (:doc:`动画值属性 </attributes/animation_value>`)
  * addition、accumulate (:doc:`动画添加属性 </attributes/animation_addition>`)

.. tab:: 英文


  * onbegin, onend, onrepeat, onload (:doc:`Animation Event Attributes </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`Animation Target Attributes </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`Animation Timing Attributes </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`Animation Value Attributes </attributes/animation_value>`)
  * additive, accumulate (:doc:`Animation Addition Attributes </attributes/animation_addition>`)

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **externalResourcesRequired** -- `bool`

    *False*: 如果即使外部资源不可用，文档渲染仍可继续，否则： *True*

.. tab:: 英文

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`XLink Attributes </attributes/xlink>`

AnimateColor
============


.. autoclass:: svgwrite.animate.AnimateColor

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AnimateColorElement

.. tab:: 中文

  **from**、**by** 和 **to** 属性接受颜色值，其中每个颜色值使用以下语法表示（与 SVG 中可以接受颜色值的属性使用的语法相同）：

      <color> <icccolor>?

  **animateColor** 元素的 **values** 属性包含一个用分号分隔的颜色值列表，每个颜色值都按上述语法表示。

  可以提供超出范围的颜色值，但用户代理的处理将依赖于实现。用户代理应该尽可能推迟对颜色值的限制，但请注意，系统差异可能会导致不同系统之间的一致性行为问题。

  **color-interpolation** 属性应用于由 **animateColor** 动画产生的颜色插值。

.. tab:: 英文

  The **from**, **by** and **to** attributes take color values, where each
  color value is expressed using the following syntax (the same syntax as used
  in SVG's properties that can take color values):

      <color> <icccolor>?

  The **values** attribute for the **animateColor** element consists of a
  semicolon-separated list of color values, with each color value expressed in
  the above syntax.

  Out of range color values can be provided, but user agent processing will be
  implementation dependent. User agents should clamp color values to allow
  color range values as late as possible, but note that system differences
  might preclude consistent behavior across different systems.

  The **color-interpolation** property applies to color interpolations that
  result from **animateColor** animations.

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.animate.Animate`

SVG 动画属性
------------------------

SVG Animation Attributes

.. tab:: 中文

  * onbegin, onend, onrepeat, onload (:doc:`动画事件属性 </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`动画目标属性 </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`动画时间属性 </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`动画值属性 </attributes/animation_value>`)
  * additive, accumulate (:doc:`动画附加属性 </attributes/animation_addition>`)

.. tab:: 英文

  * onbegin, onend, onrepeat, onload (:doc:`Animation Event Attributes </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`Animation Target Attributes </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`Animation Timing Attributes </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`Animation Value Attributes </attributes/animation_value>`)
  * additive, accumulate (:doc:`Animation Addition Attributes </attributes/animation_addition>`)

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`XLink Attributes </attributes/xlink>`

AnimateTransform
================

.. autoclass:: svgwrite.animate.AnimateTransform

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AnimateTransformElement

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.XLink`
* :class:`svgwrite.animate.Animate`

方法
-------

Methods

.. automethod:: svgwrite.animate.AnimateTransform.__init__

SVG 动画属性
------------------------

SVG Animation Attributes

.. tab:: 中文

  * onbegin, onend, onrepeat, onload (:doc:`动画事件属性 </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`动画目标属性 </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`动画时间属性 </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`动画值属性 </attributes/animation_value>`)
  * additive, accumulate (:doc:`动画附加属性 </attributes/animation_addition>`)

.. tab:: 英文

  * onbegin, onend, onrepeat, onload (:doc:`Animation Event Attributes </attributes/animation_events>`)
  * attributeType, attributeName (:doc:`Animation Target Attributes </attributes/animation_target>`)
  * begin, dur, end, min, max, restart, repeatCount, repeatDur, fill (:doc:`Animation Timing Attributes </attributes/animation_timing>`)
  * calcMode, values, keyTimes, keySplines, from, to, by (:doc:`Animation Value Attributes </attributes/animation_value>`)
  * additive, accumulate (:doc:`Animation Addition Attributes </attributes/animation_addition>`)

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **externalResourcesRequired** -- `bool`

    *False*: 如果文档渲染可以在外部资源不可用的情况下继续，否则：*True*

  * **type** -- ``'translate | scale | rotate | skewX | skewY'``

    指示要随时间变化的变换类型。如果未指定该属性，则效果就像指定了 **translate** 的值一样。

  **from**、**by** 和 **to** 属性接受一个值，该值使用适用于给定变换类型的相同语法表示：

  * 对于 type = ``'translate'``，每个单独的值表示为 `<tx> [,<ty>]`。

  * 对于 type = ``'scale'``，每个单独的值表示为 `<sx> [,<sy>]`。

  * 对于 type = ``'rotate'``，每个单独的值表示为 `<rotate-angle> [<cx> <cy>]`。

  * 对于 type = ``'skewX'`` 和 type = ``'skewY'``，每个单独的值表示为 `<skew-angle>`。

.. tab:: 英文

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed even if external resources are
    unavailable else: *True*

  * **type** -- ``'translate | scale | rotate | skewX | skewY'``

    Indicates the type of transformation which is to have its values change
    over time. If the attribute is not specified, then the effect is as if a
    value of **translate** were specified.

  The **from**, **by** and **to** attributes take a value expressed using the
  same syntax that is available for the given transformation type:

  * For a type = ``'translate'``, each individual value is expressed as
    `<tx> [,<ty>]`.

  * For a type = ``'scale'``, each individual value is expressed as
    `<sx> [,<sy>].`

  * For a type = ``'rotate'``, each individual value is expressed as
    `<rotate-angle> [<cx> <cy>].`

  * For a type = ``'skewX'`` and type = ``'skewY'``, each individual value is
    expressed as `<skew-angle>.`

标准 SVG 属性
-----------------------

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`XLink Attributes </attributes/xlink>`

SVG 动画属性
========================

.. toctree::
   :maxdepth: 2

   /attributes/animation_events
   /attributes/animation_target
   /attributes/animation_timing
   /attributes/animation_value
   /attributes/animation_addition
