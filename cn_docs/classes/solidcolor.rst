SolidColor
==========

.. tab:: 中文

    `solidColor` 元素是提供具有不透明度的单一颜色的绘画服务器。它可以像其他绘画服务器（即渐变）一样被引用。

.. tab:: 英文

    The `solidColor` element is a paint server that provides a single color with opacity. It can be referenced like the
    other paint servers (i.e. gradients).

.. autoclass:: svgwrite.solidcolor.SolidColor

.. seealso:: https://www.w3.org/TR/SVGTiny12/painting.html#SolidColorElement


方法
-------

Methods

.. automethod:: svgwrite.solidcolor.SolidColor.__init__

SVG 属性
--------------

SVG Attributes

.. tab:: 中文

    * **solid-color** -- ``'currentColor | <color> | inherit'`` (__init__() 参数 `color`)

    `solid-color` 属性指定应为此 `solidColor` 元素使用的颜色。关键字 ``"currentColor"`` 可以像在 `<paint>` 规格中的 `fill` 和 `stroke` 属性中一样指定。

    * **solid-opacity** -- ``'<opacity-value> | inherit'`` (__init__() 参数 `opacity`)

    `solid-opacity` 参数定义了 `solidColor` 的不透明度。任何超出 `0.0` （完全透明）到 `1.0` （完全不透明）范围的值必须被限制在此范围内。

.. tab:: 英文

    * **solid-color** -- ``'currentColor | <color> | inherit'`` (__init__() parameter `color`)

        The `solid-color` attribute specifies the color that shall be used for this `solidColor` element. The keyword
        ``"currentColor"`` can be specified in the same manner as within a `<paint>` specification for the `fill` and
        `stroke` properties.

    * **solid-opacity** -- ``'<opacity-value> | inherit'`` (__init__() parameter `opacity`)

        The `solid-opacity` parameter defines the opacity of the `solidColor`. Any values outside the range `0.0`
        (fully transparent) to `1.0` (fully opaque) must be clamped to this range.