Animation Target Attributes
===========================

.. _attributeType:

attributeType
-------------

.. tab:: 中文

    指定目标属性及其相关值定义的命名空间。属性值是以下之一（值区分大小写）：

    =========== =================================================================
    值          描述
    =========== =================================================================
    ``CSS``     这指定 **attributeName** 的值是本规范中定义为可动画的 CSS 属性名称。
    ``XML``     这指定 **attributeName** 的值是目标元素默认 XML 命名空间中定义的 XML 属性名称。如果 **attributeName** 的值具有 XMLNS 前缀，则实现必须使用在目标元素作用域中定义的相关命名空间。该属性必须在本规范中定义为可动画的。
    ``auto``    实现应将 **attributeName** 匹配到目标元素的属性。实现必须首先在 CSS 属性列表中搜索匹配的属性名称，如果未找到，则搜索该元素的默认 XML 命名空间。
    =========== =================================================================

    默认值是 ``'auto'``。

.. tab:: 英文

    Specifies the namespace in which the target attribute and its associated
    values are defined. The attribute value is one of the following (values are
    case-sensitive):

    =========== =================================================================
    value       description
    =========== =================================================================
    ``CSS``     This specifies that the value of **attributeName** is the name
                of a CSS property defined as animatable in this specification.
    ``XML``     This specifies that the value of **attributeName** is the name
                of an XML attribute defined in the default XML namespace for the
                target element. If the value for **attributeName** has an XMLNS
                prefix, the implementation must use the associated namespace as
                defined in the scope of the target element. The attribute must
                be defined as animatable in this specification.
    ``auto``    The implementation should match the **attributeName** to an
                attribute for the target element. The implementation must first
                search through the list of CSS properties for a matching property
                name, and if none is found, search the default XML namespace for
                the element.
    =========== =================================================================

    The default value is ``'auto'``.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AttributeTypeAttribute

.. _attributeName:

attributeName
-------------

.. tab:: 中文

    **attributeName** = `<attributeName>`

    指定目标属性的名称。可以使用 XMLNS 前缀来指示该属性的 XML 命名空间。该前缀将在当前（即引用的）动画元素的作用域中进行解释。

.. tab:: 英文


    attributeName = `<attributeName>`

    Specifies the name of the target attribute. An XMLNS prefix may be used to
    indicate the XML namespace for the attribute. The prefix will be interpreted
    in the scope of the current (i.e., the referencing) animation element.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#AttributeNameAttribute
