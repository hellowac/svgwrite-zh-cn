.. _feDistantLight:

feDistantLight 滤镜元素
=============================

feDistantLight Filter Element

.. tab:: 中文

    光源 **feDistantLight** 是滤镜原语 :ref:`feDiffuseLighting <feDiffuseLighting>` 或 :ref:`feSpecularLighting <feDiffuseLighting>` 的子元素，可以通过滤镜原语 **feDiffuseLighting** 或 **feSpecularLighting** 的方法 :meth:`feDistantLight` 来创建并添加该对象。

.. tab:: 英文

    The light source **feDistantLight** is a child element of the filter primitives
    :ref:`feDiffuseLighting <feDiffuseLighting>` or :ref:`feSpecularLighting <feDiffuseLighting>`,
    create and add this object with the method :meth:`feDistantLight`
    of the filter primitives **feDiffuseLighting** or **feSpecularLighting**.

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feDistantLightElement

SVG Attributes
--------------

.. tab:: 中文

    * **azimuth** -- `<number>`

    光源在 XY 平面上的方向角（顺时针方向），单位为度。

    默认值为 ``'0'``

    * **elevation** -- `<number>`

    光源在 YZ 平面上的方向角，单位为度。

    默认值为 ``'0'``

.. tab:: 英文

    * **azimuth** -- `<number>`

        Direction angle for the light source on the XY plane (clockwise), in degrees.

        Default is ``'0'``

    * **elevation** -- `<number>`

        Direction angle for the light source on the YZ plane, in degrees.

        Default is ``'0'``

.. _fePointLight:

fePointLight 滤镜元素
===========================

fePointLight Filter Element

.. tab:: 中文

    光源 **fePointLight** 是 **feDiffuseLighting** 或 **feSpecularLighting** 过滤原语的子元素，可以通过过滤原语 **feDiffuseLighting** 或 **feSpecularLighting** 的方法 :meth:`fePointLight` 创建并添加此对象。

    光源 **feDistantLight** 是 **feDiffuseLighting** 或 **feSpecularLighting** 过滤原语的子元素。

.. tab:: 英文

    The light source **fePointLight** is a child element of the filter primitives
    :ref:`feDiffuseLighting <feDiffuseLighting>` or :ref:`feSpecularLighting <feDiffuseLighting>`,
    create and add this object with the method :meth:`fePointLight`
    of the filter primitives **feDiffuseLighting** or **feSpecularLighting**.

    The light source **feDistantLight** is a child element of the filter primitives
    **feDiffuseLighting** or **feSpecularLighting**.

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#fePointLightElement

SVG Attributes
--------------

.. tab:: 中文

    * **x** -- `<number>` -- **source** 参数

    光源在由 **filter** 元素上的 **primitiveUnits** 属性建立的坐标系统中的 X 坐标位置。

    默认值为 ``'0'``

    * **y** -- `<number>` -- **source** 参数

    光源在由 **filter** 元素上的 **primitiveUnits** 属性建立的坐标系统中的 Y 坐标位置。

    默认值为 ``'0'``

    * **z** -- `<number>` -- **source** 参数

    光源在由 **filter** 元素上的 **primitiveUnits** 属性建立的坐标系统中的 Z 坐标位置，假设在初始坐标系统中，正 Z 轴朝向观看内容的观众，并假设 Z 轴上的单位等于 X 和 Y 轴上的单位。

    默认值为 ``'0'``

.. tab:: 英文

    * **x** -- `<number>` -- **source** parameter

        X location for the light source in the coordinate system established by
        attribute **primitiveUnits** on the **filter** element.

        Default is ``'0'``

    * **y** -- `<number>` -- **source** parameter
        Y location for the light source in the coordinate system established by
        attribute **primitiveUnits** on the **filter** element.

        Default is ``'0'``

    * **z** -- `<number>`-- **source** parameter

        Z location for the light source in the coordinate system established by
        attribute **primitiveUnits** on the ‘filter’ element, assuming that, in the
        initial coordinate system, the positive Z-axis comes out towards the person
        viewing the content and assuming that one unit along the Z-axis equals one
        unit in X and Y.

        Default is ``'0'``


.. _feSpotLight:

feSpotLight 滤镜元素
==========================

feSpotLight Filter Element

.. tab:: 中文

    光源 **feSpotLight** 是 **feDiffuseLighting** 或 **feSpecularLighting** 滤镜原语的子元素，可以通过 **feDiffuseLighting** 或 **feSpecularLighting** 滤镜原语的 :meth:`feSpotLight` 方法创建并添加此对象。

.. tab:: 英文

    The light source **feSpotLight** is a child element of the filter primitives
    :ref:`feDiffuseLighting <feDiffuseLighting>` or :ref:`feSpecularLighting <feDiffuseLighting>`,
    create and add this object with the method :meth:`feSpotLight`
    of the filter primitives **feDiffuseLighting** or **feSpecularLighting**.

.. seealso:: http://www.w3.org/TR/SVG11/filters.html#feSpotLightElement

SVG Attributes
--------------

.. tab:: 中文

    * **x**, **y**, **z** -- 参见 :ref:`fePointLight`

    * **pointsAtX** -- `<number>` -- **target** 参数

        光源指向的点在由 **filter** 元素的 **primitiveUnits** 属性确定的坐标系统中的 X 坐标。

        默认值为 ``'0'``

    * **pointsAtY** -- `<number>` -- **target** 参数

        光源指向的点在由 **filter** 元素的 **primitiveUnits** 属性确定的坐标系统中的 Y 坐标。

        默认值为 ``'0'``

    * **pointsAtZ** -- `<number>` -- **target** 参数

        光源指向的点在由 **filter** 元素的 **primitiveUnits** 属性确定的坐标系统中的 Z 坐标。假设在初始坐标系统中，正 Z 轴指向观看内容的人，并假设 Z 轴上的一个单位等于 X 和 Y 上的一个单位。

        默认值为 ``'0'``

    * **specularExponent** -- `<number>`

        控制光源聚焦的指数值。

        默认值为 ``'1'``

    * **limitingConeAngle** -- `<number>`

        限制光源投射区域的锥形角度。光源在锥形外部不会投射光线。**limitingConeAngle** 表示光源轴（即光源与其指向的点之间的轴）与光源锥体之间的角度（单位为度）。用户代理应在锥形的边界应用平滑技术，例如抗锯齿。

        如果未指定值，则不应用限制锥体。

.. tab:: 英文

    * **x**, **y**, **z** -- see :ref:`fePointLight`

    * **pointsAtX** -- `<number>` -- **target** parameter

        X location in the coordinate system established by attribute
        **primitiveUnits** on the **filter** element of the point at which the
        light source is pointing.

        Default is ``'0'``

    * **pointsAtY** -- `<number>` -- **target** parameter

        Y location in the coordinate system established by attribute
        **primitiveUnits** on the **filter** element of the point at which the
        light source is pointing.

        Default is ``'0'``

    * **pointsAtZ** -- `<number>` -- **target** parameter

        Z location in the coordinate system established by attribute
        **primitiveUnits** on the **filter** element of the point at which the light
        source is pointing, assuming that, in the initial coordinate system, the
        positive Z-axis comes out towards the person viewing the content and
        assuming that one unit along the Z-axis equals one unit in X and Y.

        Default is ``'0'``

    * **specularExponent** -- `<number>`

        Exponent value controlling the focus for the light source.

        Default is ``'1'``

    * **limitingConeAngle** -- `<number>`

        A limiting cone which restricts the region where the light is projected. No
        light is projected outside the cone. **limitingConeAngle** represents the
        angle in degrees between the spot light axis (i.e. the axis between the
        light source and the point to which it is pointing at) and the spot light
        cone. User agents should apply a smoothing technique such as anti-aliasing
        at the boundary of the cone.

        If no value is specified, then no limiting cone will be applied.
