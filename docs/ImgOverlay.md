# ImgOverlay图层

### 概述

增加mouseover更换图标

[实践案例](https://competent-morse-8518a5.netlify.com/examples/ImgOverlay-formatter.html ':include :type=iframe width=100% height=600px')


### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| SSImgOverlay(opts: ImgOverlay)     | 创建一个图片图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |


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
| onMouseOver(item, event,this)   | 鼠标悬浮事件。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |
| onMouseEnter(item, event,this)   | 鼠标进入被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |
| onMouseLeave(item, event,this)    | 鼠标离开被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |