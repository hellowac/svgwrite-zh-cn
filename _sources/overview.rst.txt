概述
========

Overview

.. tab:: 中文

   如名称 `svgwrite` 所示， `svgwrite` 创建新的 SVG 图形，它不会读取/导入现有的图形，但你可以通过 `<image>` 实体始终包含其他 SVG 图形。

   `svgwrite` 具有一个调试功能，可以通过 :code:`svgwrite.Drawing(debug=True)` 激活。此功能用于在开发过程中查找代码生成的 SVG 错误。该验证算法未经过优化，因此对于大的 SVG 文件来说非常慢。未来也不会进行改进。因为它很慢，所以不要在生产代码中使用它！

   如果没有调试功能的 `svgwrite` 仍然太慢，你必须使用 `lxml` 包而不通过 `svgwrite` 作为包装器。这是一个残酷的事实，因为 `svgwrite` 只是 `xml.etree.ElementTree` 的一个包装器。如果你学习了 ElementTree API 和 SVG 元素及属性，你就不再需要 `svgwrite`。

.. tab:: 英文

   As the name `svgwrite` implies, `svgwrite` creates new SVG drawings, it does not read/import existing drawings, but you can always include other SVG drawings by the `<image>` entity.

   `svgwrite` has a debugging feature, activated by :code:`svgwrite.Drawing(debug=True)`. This feature is meant to find
   SVG errors produced by your code while developing. This validation algorithm is not optimized and therefore very slow for
   big SVG files. That will not change in the future. And because it is slow DON'T use it in production code!

   If `svgwrite` without debugging is still too slow, you have to use the `lxml` package without `svgwrite` as wrapper. That
   is the ugly truth since `svgwrite` is just a wrapper around `xml.etree.ElementTree`. If you learn the ElementTree API and the
   SVG elements and attributes, you do not need `svgwrite`.


SVG 元素
------------

SVG Elements

.. tab:: 中文

   .. IMPORTANT::

      使用 **Drawing** 类的 **工厂方法** 来创建新的对象。
      （这是为了支持不同 SVG 版本的验证。）
      所有 **工厂方法** 都具有原始的 SVG 元素名称（例如 Drawing.a(...)，
      Drawing.g(...)，Drawing.symbol(...)，Drawing.line(...)）

   一个简短的示例::

      dwg = svgwrite.Drawing()
      link = dwg.add(dwg.a("http://link.to/internet"))
      square = link.add(dwg.rect((0, 0), (1, 1), fill='blue'))

.. tab:: 英文

   .. IMPORTANT::

      Use the **factory-methods** of the class **Drawing** to create new objects.
      (This is necessary to support validation for different SVG versions.)
      All **factory-methods** have the original SVG Elementname (e.g. Drawing.a(...),
      Drawing.g(...), Drawing.symbol(...), Drawing.line(...))

   a short example::

      dwg = svgwrite.Drawing()
      link = dwg.add(dwg.a("http://link.to/internet"))
      square = link.add(dwg.rect((0, 0), (1, 1), fill='blue'))


结构元素
~~~~~~~~~~~~~~~~~~~

Structural Elements

:class:`~svgwrite.drawing.Drawing`, :class:`~svgwrite.container.SVG`,
:class:`~svgwrite.container.Group`, :class:`~svgwrite.container.Defs`,
:class:`~svgwrite.container.Symbol`, :class:`~svgwrite.container.Marker`,
:class:`~svgwrite.container.Use`, :class:`~svgwrite.container.Hyperlink`

图形元素
~~~~~~~~~~~~~~~~~~

Graphical Elements

:class:`~svgwrite.shapes.Line`, :class:`~svgwrite.shapes.Rect`,
:class:`~svgwrite.shapes.Circle`, :class:`~svgwrite.shapes.Ellipse`,
:class:`~svgwrite.shapes.Polyline`, :class:`~svgwrite.shapes.Polygon`,
:class:`~svgwrite.path.Path`

文本对象
~~~~~~~~~~~~

Text Objects

:class:`~svgwrite.text.Text`, :class:`~svgwrite.text.TSpan`,
:class:`~svgwrite.text.TRef`, :class:`~svgwrite.text.TextPath`,
:class:`~svgwrite.text.TextArea`,

绘图服务器
~~~~~~~~~~~~

Paint Server

:class:`~svgwrite.gradients.LinearGradient`, :class:`~svgwrite.gradients.RadialGradient`,
:class:`~svgwrite.pattern.Pattern`,

蒙版
~~~~~~~

Masking

:class:`~svgwrite.masking.Mask`, :class:`~svgwrite.masking.ClipPath`

动画
~~~~~~~~~

Animation

:class:`~svgwrite.animate.Set`, :class:`~svgwrite.animate.Animate`,
:class:`~svgwrite.animate.AnimateColor`, :class:`~svgwrite.animate.AnimateMotion`,
:class:`~svgwrite.animate.AnimateTransform`

滤镜效果
~~~~~~~~~~~~~~

Filter Effects

:class:`~svgwrite.filters.Filter`


混合
------

Mixins

:class:`~svgwrite.mixins.ViewBox`,
:class:`~svgwrite.mixins.Transform`,
:class:`~svgwrite.mixins.XLink`,
:class:`~svgwrite.mixins.Presentation`,
:class:`~svgwrite.mixins.MediaGroup`,
:class:`~svgwrite.mixins.Markers`,
:class:`~svgwrite.mixins.Clipping`,

常用属性
-----------------

Common Attributes

.. toctree::
   :maxdepth: 1

   attributes/core
   attributes/conditional_processing
   attributes/document_event
   attributes/graphical_event
   attributes/presentation
   attributes/xlink

基本数据类型
----------------

Basic Data Types

.. tab:: 中文

   W3C: http://www.w3.org/TR/SVG11/types.html

   你可以始终使用 Python 类型（ `int`， `float`）来表示长度、坐标或角度值，对于长度和坐标，默认单位是 ``px``，对于角度，默认单位是 ``deg``，或者你可以使用包含单位的字符串（例如 ``100in``， ``1.5cm``， ``3.141529rad``）。

   示例::

      Drawing(height=100, width=100)  # 画布区域为 100px x 100px
      Drawing(height='10cm', width='20cm')  # 画布区域为 10cm x 20cm

.. tab:: 英文

   W3C: http://www.w3.org/TR/SVG11/types.html

   You can always use python-types (`int`, `float`) for length, coordinate or angle
   values, for length and coordinates the default unit is ``px``, for angles the
   default unit is ``deg``, or you can use a string including a unit (e.g. ``100in``,
   ``1.5cm``, ``3.141529rad``).

   Examples::

      Drawing(height=100, width=100) # drawing area of 100px x 100px
      Drawing(height='10cm', width='20cm') # drawing area of 10cm x 20cm


数字
-------

Numbers

.. tab:: 中文

   数字可以是整数或浮动数字，也可以使用科学计数法：

   .. note::
      *tiny profile*: 数字的 **小数部分** 不能超过 4 位小数，且必须在范围 -32,767.9999 到 +32,767.9999 之间（包括该范围）。

   示例：

   * 10, -23, 0
   * 73.1234, -0.002, .154, -.897, +13.2, 0000.123
   * 1.24E+2, 1.24e+2, 1E0, -.0E-1

.. tab:: 英文

   Numbers can be intergers or floats, also in scientific notation:

   .. note::
      *tiny profile*: numbers must **not** have more than 4 decimal digits in the
      fractional part of their decimal expansion and must be in the range -32,767.9999
      to +32,767.9999, inclusive

   Examples:

   * 10, -23, 0
   * 73.1234, -0.002, .154, -.897, +13.2, 0000.123
   * 1.24E+2, 1.24e+2,1E0, -.0E-1

角度
------

Angles

.. tab:: 中文

   <angle> 单位标识符是可选的。如果未提供，角度值默认以度为单位。

   ==== =================== ========================
   单位 标识符              描述
   ==== =================== ========================
   deg  角度，以度为单位    (完整圆为 360deg)
   grad 角度，以梯度为单位  (完整圆为 400grad)
   rad  角度，以弧度为单位  (完整圆为 2*PI)
   ==== =================== ========================

.. tab:: 英文

   The <angle> unit identifier is optional. If not provided, the angle value is assumed to be in degrees.

   ==== ================ ========================
   unit identifier       description
   ==== ================ ========================
   deg  angle in degrees (full circle is 360deg)
   grad angle in grads   (full circle is 400grad)
   rad  angle in radians (full circle is 2*PI)
   ==== ================ ========================

长度
------

Length

.. tab:: 中文

   一个 *<length>* 是一个距离度量，表示为一个数字和单位，单位标识符必须使用小写字母。百分比长度值的含义取决于指定该百分比长度值的属性。

   两种常见情况是：

   1. 当百分比长度值表示视口的 *宽度* 或 *高度* 的百分比时，
   2. 当百分比长度值表示给定对象的边界框 *宽度* 或 *高度* 的百分比时。

.. tab:: 英文

   A *<length>* is a distance measurement, given as a number along with a unit, the
   unit identifiers must be in lower case. The meaning of a percentage length value
   depends on the attribute for which the percentage length value has been specified.

   Two common cases are:

   1. when a percentage length value represents a percentage of the viewport *width* or *height*, and
   2. when a percentage length value represents a percentage of the bounding box *width* or *height* on a given object.

坐标
-----------

Coordinates

.. tab:: 中文

   一个 *<coordinate>* 是用户坐标系统中的一个长度，它是从用户坐标系统的原点沿相关轴（X 坐标为 x 轴，Y 坐标为 y 轴）测量的给定距离。它的语法与 *<length>* 相同。

.. tab:: 英文

   A *<coordinate>* is a length in the user coordinate system that is the given distance
   from the origin of the user coordinate system along the relevant axis (the x-axis
   for X coordinates, the y-axis for Y coordinates). Its syntax is the same as that
   for *<length>*.

单位
-----

Units

.. tab:: 中文

   W3C: http://www.w3.org/TR/SVG11/coords.html#Units

   当坐标或长度值是没有单位标识符的数字（例如，“25”）时，给定的坐标或长度默认以用户单位表示（即当前用户坐标系统中的一个值）。

   绝对单位标识符仅建议用于 `width` 和 `height` 属性，或在内容不包含任何变换且希望相对于设备像素网格或特定实际单位大小指定值的情况。

   .. note::

      *tiny profile*: 除了 **Drawing** 对象的 *width* 和 *height* 属性外，不使用任何单位。

   ==== ======================
   单位 标识符 描述
   ==== ======================
   px   一个 px 单位等于一个用户单位(user unit)
   em   字体大小 (实际字体高度)
   ex   x 高度（实际字体中字母 'x' 的高度）
   pt   点（point）"1pt" 等于 "1.25px"（因此等于 1.25 用户单位）
   pc   派卡（pica）"1pc" 等于 "15px"（因此等于 15 用户单位）
   mm   毫米（millimeter）"1mm" 等于 "3.543307px"（即 3.543307 用户单位）
   cm   厘米（centimeter）"1cm" 等于 "35.43307px"（即 35.43307 用户单位）
   in   英寸（inch）"1in" 等于 "90px"（即 90 用户单位）
   ==== ======================

.. tab:: 英文

   W3C: http://www.w3.org/TR/SVG11/coords.html#Units

   When a coordinate or length value is a number without a unit identifier (e.g., "25"),
   then the given coordinate or length is assumed to be in user units (i.e., a value
   in the current user coordinate system).

   Absolute units identifiers are only recommended for the `width` and the `height`
   on and situations where the content contains no transformations and it is desirable
   to specify values relative to the device pixel grid or to a particular real world
   unit size.

   .. note::
      *tiny profile*: no usage of units except for the *width* and *height* attributes
      of the Drawing object.

   ==== ======================
   unit identifier description
   ==== ======================
   px   one px unit is defined to be equal to one user unit
   em   font-size (actual font height)
   ex   x-height (height of letter 'x' of actual font)
   pt   point   "1pt" equals "1.25px" (and therefore 1.25 user units)
   pc   pica "1pc" equals "15px" (and therefore 15 user units)
   mm   millimeter "1mm" would be "3.543307px" (3.543307 user units)
   cm   centimeter "1cm" equals "35.43307px" (and therefore 35.43307 user units)
   in   inch "1in" equals "90px" (and therefore 90 user units)
   ==== ======================
