# PolygenOverlay图层

### 概述

多边形的图层。

[实践案例](https://smartdata.b0.upaiyun.com/inmap/examples/PolygonOverlay2.html ':include :type=iframe width=100% height=600px')


### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| PolygenOverlay(opts: PolygenOverlay)     | 创建一个多边形图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |



### styleOption

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| normal    | Object |   默认状态的样式配置    |
| mouseOver    | Object |   鼠标悬浮状态的样式配置    |
| selected    | Object |   鼠标选中状态的样式配置    |

### 样式描述

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| borderStyle  | String,Array |   支持字符串类型'dotted'，'dashed',支持数组类型比如：[1,4],第一个参数用于规定第一个虚线的长度。第二个参数用于规定第一个虚线与第二个虚线之间的间隔。    |


### eventOption

| 状态        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| onMouseOver(item, event)    | 多边形鼠标悬浮事件。 item:当前悬浮的数据对象。event: 事件对象 |   Function    |
| onMouseMove(item, event)    | 多边形鼠标移动事件。 item:当前悬浮的数据对象。event: 事件对象 |   Function    |