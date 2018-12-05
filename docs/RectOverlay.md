# RectOverlay图层

### 概述

正方形的图层，用来表示热力。

[实践案例](https://smartdata.b0.upaiyun.com/inmap/examples/RectOverlay.html ':include :type=iframe width=100% height=600px')


### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| RectOverlay(opts: RectOverlayOption)     | 创建一个正方形图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |


### RectOverlay 方法

| 方法        | 返回值   |  描述  |
| --------   | -----:  | :----:  |
| setZIndex(index:Number)     | none |   设置当前的图层的z-index值。注意：被and添加之后才能调用生效,inmap默认是按照添加图层的顺序设置层级的     |
| setData(data:Array<Point>)        |   none   |   设置当前图层的数据   |
| setOptionStyle(opts: ImgOverlayOption)        |    none    |  设置当前样式，会造成画布重绘.  |
| setSelectd(exp: String)       |    none    |  设置选中  |