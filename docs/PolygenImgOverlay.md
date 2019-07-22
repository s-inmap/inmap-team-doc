# PolygenImgOverlay图层

### 概述

多边形POI的图层。

[实践案例](https://competent-morse-8518a5.netlify.com/examples/PolygonImgOverlay.html ':include :type=iframe width=100% height=600px')


### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| PolygenImgOverlay(opts:PolygenImgOverlay)     | 创建一个多边形POI图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |


### styleOption

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| normal    | 样式描述 |   默认状态的样式配置    |
| mouseOver    | 样式描述 |   鼠标悬浮状态的样式配置    |


### 样式描述

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| icon    | 图片绝对路径地址后者图片对象	 |   path/Image    |
| width    | 图标宽度	 |   Number    |
| height    | 图标的高度	 |   Number    |
| offsets    | 图标的偏移量	 |   Object    |
| backgroundColor    | 背景颜色 |   RGB/HSL/HEX    |
| borderColor    | 边框颜色	 |   RGB/HSL/HEX    |


### eventOption

| 参数        | 说明   |  类型  |  默认值  |
| --------   | -----:  | :----:  | :----:  |
| onMouseOver(item, event,this)    | 多边形鼠标悬浮事件。<br> item:当前悬浮的数据对象。<br>event: 事件对象 |    Function   |     -     |
| onMouseEnter(item, event,this)   | 鼠标进入被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |
| onMouseLeave(item, event,this)    | 鼠标离开被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |

### PolygonImgOverlay 方法

| 方法        | 返回值   |  描述  |
| --------   | -----:  | :----:  |
| setSelectd(point: Array,zoom: Number)       |    none    |  设置选中,point:表示经纬度数组，例如：[116.33241452690892, 39.97210699633034]，zoom表示地图缩放的级别，比如16 |