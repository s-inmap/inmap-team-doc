# ImgOverlay图层

### 概述

增加mouseover更换图标

[实践案例](https://smartdata.b0.upaiyun.com/inmap/examples/ImgOverlay-formatter.html ':include :type=iframe width=100% height=600px')


### styleOption

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| mouseOver    | Object |   鼠标悬浮状态的样式配置    |


### 样式描述

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| icon    | 图片绝对路径地址后者图片对象 |   path/Image    |

### eventOption

| 参数        | 说明   |  类型  |  默认值  |
| --------   | -----:  | :----:  | :----:  |
| onMouseEnter    | 鼠标进入被选元素时。 
item:当前鼠标悬浮选中的数据对象。 
event: 事件对象 
this: 当前对象 |   Function    |     -     |
| onMouseLeave    | 鼠标离开被选元素时。 
item:当前鼠标悬浮选中的数据对象。 
event: 事件对象 
this: 当前对象 |   Function    |     -     |