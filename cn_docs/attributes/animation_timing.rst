Animation Timing Attributes
===========================

.. _begin:

begin
-----

.. tab:: 中文

    begin = `<begin-value-list>`

    定义元素何时开始（即变为活动状态）。

    属性值是一个以分号分隔的值列表。

.. tab:: 英文

    begin = `<begin-value-list>`

    Defines when the element should begin (i.e. become active).

    The attribute value is a semicolon separated list of values.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#BeginAttribute

.. _dur:

dur
---

.. tab:: 中文

    **dur** = `<Clock-value>` | ``'media | indefinite'``

    指定简单持续时间。

    该属性值可以是以下之一：

    =============== ==============================================================
    值               描述
    =============== ==============================================================
    `<Clock-value>`  指定呈现时间中的简单持续时间长度。值必须大于 0。
    ``media``        指定简单持续时间为固有的媒体持续时间。 
                    仅对定义了媒体的元素有效。（对于 SVG 的动画元素，如果指定了 ``'media'``，该属性将被忽略。）
    ``indefinite``   指定简单持续时间为无限期。
    =============== ==============================================================

    如果动画没有 **dur** 属性，则简单持续时间为无限期。请注意，如果简单持续时间为无限期，则插值将无法工作（尽管对于 **set** 元素仍然可能有用）。

.. tab:: 英文

    dur = `<Clock-value>` | ``'media | indefinite'``

    Specifies the simple duration.

    The attribute value can be one of the following:

    =============== ==============================================================
    value           description
    =============== ==============================================================
    `<Clock-value>` Specifies the length of the simple duration in presentation
                    time. Value must be greater than 0.
    ``media``       Specifies the simple duration as the intrinsic media duration.
                    This is only valid for elements that define media.(For SVG's
                    animation elements, if ``'media'`` is specified, the attribute
                    will be ignored.)
    ``indefinite``  Specifies the simple duration as indefinite.
    =============== ==============================================================

    If the animation does not have a **dur** attribute, the simple duration is
    indefinite. Note that interpolation will not work if the simple duration is
    indefinite (although this may still be useful for **set** elements).

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#DurAttribute

.. _end:

end
---

.. tab:: 中文

    **end** = `<end-value-list>`

    定义动画的结束值，可以限制活动持续时间。

    该属性值是一个以分号分隔的值列表。

    ``'indefinite'`` 的值指定动画的结束将通过调用 `endElement` 方法来决定（动画的 DOM 方法在 DOM 接口中描述）。

.. tab:: 英文


    end = `<end-value-list>`

    Defines an end value for the animation that can constrain the active duration.

    The attribute value is a semicolon separated list of values.

    A value of ``'indefinite'`` specifies that the end of the animation will be
    determined by an endElement method call (the animation DOM methods are
    described in DOM interfaces).

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#EndAttribute

.. _min:

min
---

.. tab:: 中文

    **min** = `<Clock-value>` | ``'media'``

    指定活动持续时间的最小值。

    =============== =============================================================  
    值               描述  
    =============== =============================================================  
    `<Clock-value>`    指定活动持续时间的最小值，单位为本地时间。  
                        值必须大于 0。  
    ``'media'``        指定活动持续时间的最小值为固有的媒体持续时间。  
                        这仅对定义媒体的元素有效。（对于 SVG 动画元素，  
                        如果指定了 ``'media'``，该属性将被忽略。）  
    =============== =============================================================  

    **min** 的默认值为 ``'0'``。这不会限制活动持续时间。

.. tab:: 英文

    min = `<Clock-value>` | ``'media'``

    Specifies the minimum value of the active duration.

    =============== =============================================================
    value           description
    =============== =============================================================
    `<Clock-value>` Specifies the length of the minimum value of the active
                    duration, measured in local time.
                    Value must be greater than 0.
    ``'media'``     Specifies the minimum value of the active duration as the
                    intrinsic media duration. This is only valid for elements
                    that define media. (For SVG's animation elements, if
                    ``'media'`` is specified, the attribute will be ignored.)
    =============== =============================================================

    The default value for **min** is ``'0'``. This does not constrain the active
    duration at all.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#MinAttribute

.. _max:

max
---

.. tab:: 中文

    **max** = `<Clock-value>` | ``'media'``

    指定活动持续时间的最大值。

    =============== =============================================================  
    值               描述  
    =============== =============================================================  
    `<Clock-value>`    指定活动持续时间的最大值，单位为本地时间。  
                        值必须大于 0。  
    ``'media'``        指定活动持续时间的最大值为固有的媒体持续时间。  
                        这仅对定义媒体的元素有效。（对于 SVG 动画元素，  
                        如果指定了 ``'media'``，该属性将被忽略。）  
    =============== =============================================================  

    **max** 没有默认值。它不会限制活动持续时间。

.. tab:: 英文

    max = `<Clock-value>` | ``'media'``

    Specifies the maximum value of the active duration.

    =============== =============================================================
    value           description
    =============== =============================================================
    `<Clock-value>` Specifies the length of the maximum value of the active
                    duration, measured in local time.
                    Value must be greater than 0.
    ``'media'``     Specifies the maximum value of the active duration as the
                    intrinsic media duration. This is only valid for elements
                    that define media. (For SVG's animation elements, if
                    ``'media'`` is specified, the attribute will be ignored.)
    =============== =============================================================

    There is no default value for **max**. This does not constrain the active
    duration at all.

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#MaxAttribute

.. _restart:

restart
-------

.. tab:: 中文

    **restart** = ``'always | whenNotActive | never'``

    =================== ==========================================================  
    值                描述  
    =================== ==========================================================  
    ``'always'``       动画可以随时重新启动。这是默认值。  
    ``'whenNotActive'`` 动画只能在不活动时重新启动（即在活动结束后）。  
                        在活动持续时间内尝试重新启动动画会被忽略。  
    ``'never'``        元素在父时间容器的当前简单持续时间剩余时间内无法重新启动。  
                        （对于 SVG 来说，由于父时间容器是 SVG 文档片段，  
                        所以动画不能在文档持续时间剩余时间内重新启动。）  
    =================== ==========================================================  

.. tab:: 英文


    restart = ``'always | whenNotActive | never'``

    =================== ==========================================================
    value               description
    =================== ==========================================================
    ``'always'``        The animation can be restarted at any time. This is the
                        default value.
    ``'whenNotActive'`` The animation can only be restarted when it is not active
                        (i.e. after the active end). Attempts to restart the
                        animation during its active duration are ignored.
    ``'never'``         The element cannot be restarted for the remainder of the
                        current simple duration of the parent time container.
                        (In the case of SVG, since the parent time container is
                        the SVG document fragment, then the animation cannot be
                        restarted for the remainder of the document duration.)
    =================== ==========================================================

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#RestartAttribute

.. _repeatCount:

repeatCount
-----------

.. tab:: 中文

    **repeatCount** = `<number>` | ``'indefinite'``

    指定动画函数的迭代次数。它可以具有以下属性值：

    ================ ============================================================  
    值               描述  
    ================ ============================================================  
    `<number>`       这是一个（十进制）"浮动点"数值，指定迭代次数。  
                    它可以包括以分数形式表示的部分迭代。一个分数值描述了  
                    简单持续时间的一部分。值必须大于 0。  
    ``'indefinite'`` 动画被定义为无限重复（即直到文档结束）。  
    ================ ============================================================  

.. tab:: 英文

    repeatCount = `<number>` | ``'indefinite'``

    Specifies the number of iterations of the animation function. It can have the
    following attribute values:

    ================ ============================================================
    value            description
    ================ ============================================================
    `<number>`       This is a (base 10) "floating point" numeric value that
                    specifies the number of iterations. It can include partial
                    iterations expressed as fraction values. A fractional value
                    describes a portion of the simple duration. Values must be
                    greater than 0.
    ``'indefinite'`` The animation is defined to repeat indefinitely (i.e. until
                    the document ends).
    ================ ============================================================

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#RepeatCountAttribute

.. _repeatDur:

repeatDur
---------

.. tab:: 中文

    **repeatDur** = `<Clock-value>` | ``'indefinite'``

    指定重复的总持续时间。它可以具有以下属性值：

    ================ ============================================================  
    值               描述  
    ================ ============================================================  
    `<Clock-value>`  指定在演示时间内重复动画函数 f(t) 的持续时间。  
    ``'indefinite'`` 动画被定义为无限重复（即直到文档结束）。  
    ================ ============================================================  

.. tab:: 英文

    repeatDur = `<Clock-value>` | ``'indefinite'``

    Specifies the total duration for repeat. It can have the following attribute
    values:

    ================ ============================================================
    value            description
    ================ ============================================================
    `<Clock-value>`  Specifies the duration in presentation time to repeat the
                    animation function f(t).
    ``'indefinite'`` The animation is defined to repeat indefinitely (i.e. until
                    the document ends).
    ================ ============================================================

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#RepeatDurAttribute

.. _animateFill:

fill
----

.. tab:: 中文

    **fill** = ``'freeze | remove'``

    此属性可以具有以下值：

    ============ ================================================================  
    值            描述  
    ============ ================================================================  
    ``'freeze'`` 动画效果 F(t) 被定义为在活动持续时间的最后一个值处冻结效果值。动画效果将在文档的剩余时间内保持“冻结”（或直到动画重新启动 - 见 SMIL 动画：重新启动动画）。  
    ``'remove'`` 动画效果在动画的活动持续时间结束时被移除（不再应用）。在动画的活动结束后，动画不再影响目标（除非动画被重新启动 - 见 SMIL 动画：重新启动动画）。  

    这是默认值。  
    ============ ================================================================  

.. tab:: 英文


    fill = ``'freeze | remove'``

    This attribute can have the following values:

    ============ ================================================================
    value        description
    ============ ================================================================
    ``'freeze'`` The animation effect F(t) is defined to freeze the effect value
                at the last value of the active duration. The animation effect
                is "frozen" for the remainder of the document duration (or until
                the animation is restarted - see SMIL Animation: Restarting
                animation).
    ``'remove'`` The animation effect is removed (no longer applied) when the
                active duration of the animation is over. After the active end
                of the animation, the animation no longer affects the target
                (unless the animation is restarted - see SMIL Animation:
                Restarting animation).

                This is the default value.
    ============ ================================================================

.. seealso:: http://www.w3.org/TR/SVG11/animate.html#FillAttribute