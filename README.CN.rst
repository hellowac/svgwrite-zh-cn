svgwrite
========

此软件包处于非活动状态！不会添加任何新功能，也不会改变行为，只会合并错误修复。

摘要
--------

用于创建 SVG 绘图的 Python 库。

一个简单的例子::

    import svgwrite

    dwg = svgwrite.Drawing('test.svg', profile='tiny')
    dwg.add(dwg.line((0, 0), (10, 0), stroke=svgwrite.rgb(10, 10, 16, '%')))
    dwg.add(dwg.text('Test', insert=(0, 0.2), fill='red'))
    dwg.save()

更多例子见: examples.py

正如 `svgwrite` 这个名字所暗示的， `svgwrite` 创建新的 SVG 绘图，它不读取现有绘图，也不导入现有绘图，但您始终可以通过 <image> 实体包含其他 SVG 绘图。

`svgwrite` 是一个纯 Python 包，没有外部依赖项。

安装
------------

使用 pip::

    pip install svgwrite

或从源::

    python setup.py install


文档
-------------

http://readthedocs.org/docs/svgwrite/

svgwrite 可在 GitHub.com 上找到：

http://github.com/mozman/svgwrite.git

联系方式
-------

svgwrite@mozman.at
