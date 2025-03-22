Path
====

.. autoclass:: svgwrite.path.Path

.. seealso:: http://www.w3.org/TR/SVG11/paths.html#PathElement

.. automethod:: svgwrite.path.Path.__init__

属性
----------

Attributes

.. attribute:: commands

   `list` -- the command and coordinate stack

方法
-------

Methods

.. automethod:: svgwrite.path.Path.push

.. automethod:: svgwrite.path.Path.push_arc

父类
--------------

Parent Classes

* :class:`svgwrite.base.BaseElement`
* :class:`svgwrite.mixins.Transform`
* :class:`svgwrite.mixins.Presentation`
* :class:`svgwrite.mixins.Markers`

.. _pathCommands:

路径命令
-------------

Path Commands

.. tab:: 中文

  .. seealso:: http://www.w3.org/TR/SVG11/paths.html#PathData

  大写命令表示绝对坐标，小写命令表示相对坐标。

  * **horizontal-line 'h', 'H' x+**

    从当前点 (cpx, cpy) 绘制一条水平线到 (x, cpy)。

  * **vertical-line 'v', 'V' y+**

    从当前点 (cpx, cpy) 绘制一条垂直线到 (cpx, y)。

  * **line 'l', 'L' (x y)+**

    从当前点绘制一条线到给定的 (x,y) 坐标。

  * **moveto 'm', 'M' (x y)+**

    在给定的 (x,y) 坐标处开始一个新的子路径。
    如果 moveto 后跟随多个坐标对，则后续坐标对被视为隐式的线段命令。因此，如果 moveto 是相对的，隐式的线段命令也将是相对的；如果 moveto 是绝对的，则隐式的线段命令也是绝对的。如果相对的 moveto (m) 出现在路径的第一个元素中，则它被视为一对绝对坐标。
    在这种情况下，后续的坐标对即使初始 moveto 被解释为绝对 moveto，也会被视为相对坐标。

  * **cubic-bezier-curve 'c', 'C' (x1 y1 x2 y2 x y)+**

    从当前点绘制一条三次贝塞尔曲线到 (x, y)，使用 (x1, y1) 作为曲线起始处的控制点，使用 (x2, y2) 作为曲线结束处的控制点。

  * **smooth-cubic-bezier-curve 's', 'S' (x2 y2 x y)+**

    从当前点绘制一条三次贝塞尔曲线到 (x, y)。第一个控制点假定为前一个命令中第二个控制点相对于当前点的镜像。（如果没有前一个命令，或者前一个命令不是 C、c、S 或 s，则假定第一个控制点与当前点重合。）(x2, y2) 是第二个控制点（即曲线结束处的控制点）。

  * **quadratic-bezier-curve 'q', 'Q' (x1 y1 x y)+**

    从当前点绘制一条二次贝塞尔曲线到 (x, y)，使用 (x1, y1) 作为控制点。

  * **smooth-quadratic-bezier-curve 't', 'T' (x y)+**

    从当前点绘制一条二次贝塞尔曲线到 (x, y)。控制点假定为前一个命令中控制点相对于当前点的镜像。（如果没有前一个命令，或者前一个命令不是 Q、q、T 或 t，则假定控制点与当前点重合。）

  * **elliptical-arc 'a', 'A' (rx ry x-axis-rotation large-arc-flag sweep-flag x y)+**

    从当前点绘制一条椭圆弧到 (x, y)。椭圆的大小和方向由两个半径 (rx, ry) 和 x 轴旋转角度定义，x 轴旋转角度表示椭圆相对于当前坐标系的旋转方式。椭圆的中心 (cx, cy) 会根据其他参数自动计算，以满足约束条件。large-arc-flag 和 sweep-flag 有助于自动计算，并帮助确定弧线的绘制方式。

  * **'z', 'Z'**

    关闭当前子路径。


.. tab:: 英文


  .. seealso:: http://www.w3.org/TR/SVG11/paths.html#PathData

  Uppercase commands indicates absolute coordinates, lowercase commands
  indicates relative coordinates

  * **horizontal-line 'h', 'H' x+**

    Draws a horizontal line from the current point (cpx, cpy) to (x, cpy).

  * **vertical-line 'v', 'V' y+**

    Draws a vertical line from the current point (cpx, cpy) to (cpx, y).

  * **line 'l', 'L' (x y)+**

    Draw a line from the current point to the given (x,y) coordinate.

  * **moveto 'm', 'M' (x y)+**

    Start a new sub-path at the given (x,y) coordinate.
    If a moveto is followed by multiple pairs of coordinates, the subsequent
    pairs are treated as implicit lineto commands. Hence, implicit lineto
    commands will be relative if the moveto is relative, and absolute if the
    moveto is absolute. If a relative moveto (m) appears as the first element
    of the path, then it is treated as a pair of absolute coordinates.
    In this case, subsequent pairs of coordinates are treated as relative even
    though the initial moveto is interpreted as an absolute moveto.

  * **cubic-bezier-curve 'c', 'C' (x1 y1 x2 y2 x y)+**

    Draws a cubic Bézier curve from the current point
    to (x,y) using (x1,y1) as the control point at the beginning of the curve
    and (x2,y2) as the control point at the end of the curve.

  * **smooth-cubic-bezier-curve 's', 'S' (x2 y2 x y)+**

    Draws a cubic Bézier curve from the current point to
    (x,y). The first control point is assumed to be the reflection of the second
    control point on the previous command relative to the current point. (If
    there is no previous command or if the previous command was not an C, c,
    S or s, assume the first control point is coincident with the current point.)
    (x2,y2) is the second control point (i.e., the control point at the end of
    the curve).

  * **quadratic-bezier-curve 'q', 'Q' (x1 y1 x y)+**

    Draws a quadratic Bézier curve from the current point
    to (x,y) using (x1,y1) as the control point.

  * **smooth-quadratic-bezier-curve 't', 'T' (x y)+**

    Draws a quadratic Bézier curve from the current point to (x,y).
    The control point is assumed to be the reflection of the control point on
    the previous command relative to the current point. (If there is no previous
    command or if the previous command was not a Q, q, T or t, assume the control
    point is coincident with the current point.)

  * **elliptical-arc 'a', 'A' (rx ry x-axis-rotation large-arc-flag sweep-flag x y)+**

    Draws an elliptical arc from the current point to (x, y). The size and orientation
    of the ellipse are defined by two radii (rx, ry) and an x-axis-rotation,
    which indicates how the ellipse as a whole is rotated relative to the
    current coordinate system. The center (cx, cy) of the ellipse is
    calculated automatically to satisfy the constraints imposed by the other
    parameters. large-arc-flag and sweep-flag contribute to the automatic
    calculations and help determine how the arc is drawn.

  * **'z', 'Z'**

    close current subpath

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

  * **class** -- `string`

    将一个或多个 CSS 类名分配给一个元素。

  * **style** -- `string`

    允许在给定元素上直接指定每个元素的 CSS 样式规则。

  * **externalResourcesRequired** -- `bool`

    *False*：如果即使外部资源不可用，文档渲染也能继续进行；否则为 *True*。

  * **transform** -- 使用 :class:`svgwrite.mixins.Transform` 方法。

  * **pathLength** -- `<number>`

    *pathLength* 属性可以用来提供作者计算的路径总长度，以便用户代理可以根据“pathLength”与用户代理计算的路径总长度的比率，缩放路径上的距离计算。
    在 'path' 元素中的 "moveto" 操作被定义为零长度。

  * **d** -- `string`

    形状轮廓的定义，使用推送方法添加命令和坐标。


.. tab:: 英文

  * **class** -- `string`

    assigns one or more css-class-names to an element

  * **style** -- `string`

    allows per-element css-style rules to be specified directly on a given element

  * **externalResourcesRequired** -- `bool`

    *False*: if document rendering can proceed
    even if external resources are unavailable else: *True*

  * **transform** -- use :class:`svgwrite.mixins.Transform` methods

  * **pathLength** -- `<number>`

    the *pathLength* attribute can be used to provide the author's
    computation of the total length of the path so that the user agent can
    scale distance-along-a-path computations by the ratio of 'pathLength' to
    the user agent's own computed value for total path length.
    A "moveto" operation within a 'path' element is defined to have zero length.

  * **d** -- `string`

    The definition of the outline of a shape, use push-method to add commands
    and coordinates

标准 SVG 属性
-----------------------

Standard SVG Attributes

* :doc:`Core Attributes </attributes/core>`
* :doc:`Conditional Processing Attributes </attributes/conditional_processing>`
* :doc:`Graphical Event Attributes </attributes/graphical_event>`
* :doc:`Presentation Attributes </attributes/presentation>`
