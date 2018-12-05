# PieOverlay图层

### 概述

环形的图层，表示数据百分比。

[实践案例](https://smartdata.b0.upaiyun.com/inmap/examples/pieOverlay01.html ':include :type=iframe width=100% height=600px')

### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| PieOverlay(opts: PieOverlayOption)     | 创建一个环形图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |


### PieOverlay 方法

| 方法        | 返回值   |  描述  |
| --------   | -----:  | :----:  |
| setZIndex(index:Number)     | none |   设置当前的图层的z-index值。注意：被and添加之后才能调用生效,inmap默认是按照添加图层的顺序设置层级的     |
| setData(data:Array)        |   none   |   设置当前图层的数据，环形数据必须提供属性['value'],类似obj.value = [302, 500, 608];  |

### styleOption

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| backgroundStyle    | Object |   设置背景    |
| pieStyle        |   Object   |   设置环形   |
| textStyle        |    Object    |  设置文字  |


### backgroundStyle

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| show    | 是否显示环形背景 |   Boolean     |
| radius        |   背景圆形半径像素值   |   Number   |
| bgColor        |    环形背景色    |  RGB/HSL/HEX  |

### pieStyle

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| show    | 是否显示环形 |   Boolean     |
| radius        |   环形半径像素值   |   Number   |
| strokeWidth        |    环形宽度    |  Number  |
| colorList        |    环形颜色列表    |  Array  |

### textStyle

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| show    | 是否显示任何文字 |   Boolean     |
| fontSize        |   文字大小像素值   |   Number   |
| fontColor        |    文字颜色    |  RGB/HSL/HEX  |
| fontWeight        |    文字粗细    |  String  |