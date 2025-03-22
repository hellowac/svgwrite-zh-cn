Animation Value Attributes
==========================

.. _calcMode:

calcMode
--------

.. tab:: 中文

  **calcMode** = ``'discrete | linear | paced | spline'``

  指定动画的插值模式。此属性可以具有以下值。默认模式是 ``'linear'`` ，但是如果该属性不支持线性插值（例如，对于字符串），则 **calcMode** 属性将被忽略，使用离散插值。

  ============== ==============================================================
  值             描述
  ============== ==============================================================
  ``'discrete'`` 这指定动画函数将从一个值跳到下一个值，且不进行任何插值。  
  ``'linear'``   使用简单的线性插值来计算动画函数。除 **animateMotion** 外，这是默认的 **calcMode**。  
  ``'paced'``    定义插值以产生跨动画的均匀变化速度。仅支持定义线性数值范围并且可以计算“距离”概念的值（例如位置、宽度、高度等）。如果指定 ``'paced'`` ，则任何 **keyTimes** 或 **keySplines** 将被忽略。对于 **animateMotion** ，这是默认的 **calcMode** 。  
  ``'spline'``   根据由立方贝塞尔曲线定义的时间函数，从 **values** 列表中的一个值插值到下一个值。插值的关键点在 **keyTimes** 属性中定义，每个区间的控制点在 **keySplines** 属性中定义。  
  ============== ==============================================================

.. tab:: 英文

  calcMode = ``'discrete | linear | paced | spline'``

  Specifies the interpolation mode for the animation. This can take any of the
  following values. The default mode is ``'linear'``, however if the attribute
  does not support linear interpolation (e.g. for strings), the **calcMode**
  attribute is ignored and discrete interpolation is used.

  ============== ==============================================================
  value          description
  ============== ==============================================================
  ``'discrete'`` This specifies that the animation function will jump from one
                 value to the next without any interpolation.
  ``'linear'``   Simple linear interpolation between values is used to
                 calculate the animation function. Except for
                 **animateMotion**, this is the default **calcMode**.
  ``'paced'``    Defines interpolation to produce an even pace of change across
                 the animation. This is only supported for values that define
                 a linear numeric range, and for which some notion of
                 "distance" between points can be calculated (e.g. position,
                 width, height, etc.). If ``'paced'`` is specified, any
                 **keyTimes** or **keySplines** will be ignored. For
                 **animateMotion**, this is the default **calcMode**.
  ``'spline'``   Interpolates from one value in the **values** list to the
                 next according to a time function defined by a cubic Bézier
                 spline. The points of the spline are defined in the
                 **keyTimes** attribute, and the control points for each
                 interval are defined in the **keySplines** attribute.
  ============== ==============================================================

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#CalcModeAttribute

.. _values:

values
------

.. tab:: 中文

  **values** = `<list>`

  一个由一个或多个值组成的分号分隔的列表。向量值属性使用 **attributeType** 域的向量语法进行支持。根据SMIL规范，允许存在前导和尾随的空格，以及分号分隔符前后的空格，这些空格将被忽略。

.. tab:: 英文

  values = `<list>`

  A semicolon-separated list of one or more values. Vector-valued attributes
  are supported using the vector syntax of the **attributeType** domain.
  Per the SMIL specification, leading and trailing white space, and white
  space before and after semicolon separators, is allowed and will be ignored.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#ValuesAttribute

.. _keyTimes:

keyTimes
--------

.. tab:: 中文

  **keyTimes** = `<list>`

  这是一个以分号分隔的时间值列表，用于控制动画的节奏。列表中的每个时间值对应于 **values** 属性列表中的一个值，并定义了在动画函数中何时使用该值。

  每个 **keyTimes** 列表中的时间值必须是介于0到1之间的浮动值（包括0和1），表示动画元素简单持续时间的比例偏移。

  如果指定了 **keyTimes** 列表，则该列表中的值必须与 **values** 列表中的值数量相同。

  每个后续的时间值必须大于或等于前一个时间值。

  **keyTimes** 列表的语义依赖于插值模式：

  - 对于线性和样条动画，列表中的第一个时间值必须为0，最后一个时间值必须为1。与每个值关联的关键时间定义了该值何时被设置；值在关键时间之间插值。
  - 对于离散动画，列表中的第一个时间值必须为0。与每个值关联的时间定义了该值何时被设置；动画函数使用该值，直到 **keyTimes** 中定义的下一个时间。
    
  如果插值模式是 **'paced'**，则 **keyTimes** 属性会被忽略。

  如果 **keyTimes** 的指定存在任何错误（如值无效、数量过多或过少），则该文档片段会出错。

  如果简单持续时间是无限期的，任何 **keyTimes** 的指定都会被忽略。

.. tab:: 英文

  keyTimes = `<list>`

  A semicolon-separated list of time values used to control the pacing of the
  animation. Each time in the list corresponds to a value in the **values**
  attribute list, and defines when the value is used in the animation function.
  Each time value in the **keyTimes** list is specified as a floating point
  value between 0 and 1 (inclusive), representing a proportional offset into
  the simple duration of the animation element.

  If a list of **keyTimes** is specified, there must be exactly as many values
  in the **keyTimes** list as in the **values** list.

  Each successive time value must be greater than or equal to the preceding
  time value.

  The **keyTimes** list semantics depends upon the interpolation mode:

  * For linear and spline animation, the first time value in the list must be
    0, and the last time value in the list must be 1. The key time associated
    with each value defines when the value is set; values are interpolated
    between the key times.
  * For discrete animation, the first time value in the list must be 0. The
    time associated with each value defines when the value is set; the
    animation function uses that value until the next time defined in **keyTimes**.

  If the interpolation mode is ``'paced'``, the **keyTimes** attribute is ignored.

  If there are any errors in the **keyTimes** specification (bad values, too
  many or too few values), the document fragment is in error.

  If the simple duration is indefinite, any **keyTimes** specification will be
  ignored.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#KeyTimesAttribute

.. _keySplines:

keySplines
----------

.. tab:: 中文

  **keySplines** = `<list>`

  这是与 **keyTimes** 列表相关联的一组Bézier控制点，定义了一个控制区间节奏的三次Bézier函数。该属性的值是一个以分号分隔的控制点描述列表。每个控制点描述包含四个值：x1 y1 x2 y2，表示一个时间段的Bézier控制点。

  - 请注意，SMIL允许这些值通过逗号（可选空格）或仅通过空格分隔。
  - **keyTimes** 中定义的时间值充当Bézier的“锚点”，而 **keySplines** 中的值则为控制点。因此，控制点的组数比 **keyTimes** 少一个。

  所有的值都必须在0到1的范围内。

  该属性只有在 **calcMode** 设置为 ``'spline'`` 时才会生效。

  如果 **keySplines** 的指定存在任何错误（如值无效、数量过多或过少），则该文档片段会出错。

.. tab:: 英文

  keySplines = `<list>`

  A set of Bézier control points associated with the **keyTimes** list,
  defining a cubic Bézier function that controls interval pacing. The attribute
  value is a semicolon-separated list of control point descriptions. Each
  control point description is a set of four values: x1 y1 x2 y2, describing
  the Bézier control points for one time segment. Note: SMIL allows these
  values to be separated either by commas with optional whitespace, or by
  whitespace alone. The ‘keyTimes’ values that define the associated segment
  are the Bézier "anchor points", and the ‘keySplines’ values are the control
  points. Thus, there must be one fewer sets of control points than there are
  **keyTimes**.

  The values must all be in the range 0 to 1.

  This attribute is ignored unless the **calcMode** is set to ``'spline'``.

  If there are any errors in the **keySplines** specification (bad values, too
  many or too few values), the document fragment is in error.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#KeySplinesAttribute

.. _from:

from
----

.. tab:: 中文

  from = `<value>`

  指定动画的起始值。

.. tab:: 英文

  from = `<value>`

  Specifies the starting value of the animation.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#FromAttribute

.. _to:

to
----

.. tab:: 中文

  to = `<value>`

  指定动画的结束值。

.. tab:: 英文

  to = `<value>`

  Specifies the ending value of the animation.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#ToAttribute

.. _by:

by
----

.. tab:: 中文

  by = `<value>`

  指定动画的相对偏移值。

.. tab:: 英文

  by = `<value>`

  Specifies a relative offset value for the animation.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#ByAttribute