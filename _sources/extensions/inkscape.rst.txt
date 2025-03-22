Inkscape 扩展
==================

Inkscape Extension

.. tab:: 中文

    此扩展为 `inkscape`_ 添加了对图层的支持。在 inkscape 中，图层是一个扩展的 *group* 容器，具有额外的 *label* 和 *locked* 属性。Inkscape 支持嵌套图层。

    首先导入 inkscape 扩展模块::

        import svgwrite
        from svgwrite.extensions import Inkscape


        dwg = svgwrite.Drawing('test-inkscape-extension.svg', profile='full', size=(640, 480))

    您需要为每个图形激活扩展，因为需要额外的 XML 名称空间::

        inkscape = Inkscape(dwg)

    创建一个新的图层，所有支持 *group* 容器的属性也都适用::

        top_layer = inkscape.layer(label="Top LAYER 1", locked=True)

    将新图层添加为 SVG 图形的顶层图层::

        dwg.add(top_layer)

    创建新元素并将它们添加到图层中::

        line = dwg.line((100, 100), (300, 100), stroke=svgwrite.rgb(10, 10, 16, '%'), stroke_width=10)
        top_layer.add(line)

        text = dwg.text('Test', insert=(100, 100), font_size=100, fill='red')
        top_layer.add(text)

    创建另一个图层，并将其作为嵌套图层添加到“Top LAYER 1”中::

        nested_layer = inkscape.layer(label="Nested LAYER 2", locked=False)
        top_layer.add(nested_layer)

        text = dwg.text('Test2', insert=(100, 200), font_size=100, fill='blue')
        nested_layer.add(text)

        dwg.save()


.. tab:: 英文

    This extension adds support for layers in `inkscape`_. A layer in inkscape is an extended *group* container with
    additional *label* and *locked* attributes. Inkscape supports nested layers.

    First import the inkscape extension::

        import svgwrite
        from svgwrite.extensions import Inkscape


        dwg = svgwrite.Drawing('test-inkscape-extension.svg', profile='full', size=(640, 480))

    You have to activate the extension for each drawing, because additional XML name spaces are required::

        inkscape = Inkscape(dwg)

    Create a new layer, all attributes that are supported by the *group* container are also allowed::

        top_layer = inkscape.layer(label="Top LAYER 1", locked=True)

    Add new layer as top level layer to the SVG drawing::

        dwg.add(top_layer)

    Create new elements and add them to a layer::

        line = dwg.line((100, 100), (300, 100), stroke=svgwrite.rgb(10, 10, 16, '%'), stroke_width=10)
        top_layer.add(line)

        text = dwg.text('Test', insert=(100, 100), font_size=100, fill='red')
        top_layer.add(text)

    Create another layer and add them as nested layer to "Top LAYER 1"::

        nested_layer = inkscape.layer(label="Nested LAYER 2", locked=False)
        top_layer.add(nested_layer)

        text = dwg.text('Test2', insert=(100, 200), font_size=100, fill='blue')
        nested_layer.add(text)

        dwg.save()



.. _inkscape: https://inkscape.org