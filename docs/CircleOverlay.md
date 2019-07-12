# CircleOverlay图层

### 概述


[实践案例](https://competent-morse-8518a5.netlify.com/examples/CircleOverlay.html ':include :type=iframe width=100% height=600px')


### 构造函数

| 类名        | 描述   |
| --------   | -----:  |
| CircleOverlay(opts:CircleOverlay)     | 创建一个圆形图层对象。注意：图层对象实例被remove后，不可重复使用，需要重新new创建方可使用。 |


### CircleOverlay 方法

| 方法	        | 返回值	   |  描述  |
| --------   | -----:  | :----:  |
| setRange(Object)    | none |   设置辐射范围大小    |
| setRangeIsShow(Boolean)    | none |   是否显示辐射范围    |


### styleOption

| 状态        | 类型   |  说明  |
| --------   | -----:  | :----:  |
| normal    | 样式描述 |   默认状态的样式配置    |
| mouseOver    | 样式描述 |   鼠标悬浮状态的样式配置    |


### 样式描述

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| rangeShow    | 初始化显示还是隐藏辐射范围 |   Boolean    |
| icon    | 图片绝对路径地址后者图片对象	 |   path/Image    |
| width    | 图标宽度	 |   Number    |
| height    | 图标的高度	 |   Number    |
| backgroundColor    | 背景颜色 |   RGB/HSL/HEX    |
| borderColor    | 边框颜色	 |   RGB/HSL/HEX    |
| unit    | 格子大小单位，目前仅支持两个值，分别是px、m。 px表示像素单位，m表示地理的米单位。 |   String    |
| size    | 圆点大小 |   Number    |


### eventOption

| 参数        | 说明   |  类型  |  默认值  |
| --------   | -----:  | :----:  | :----:  |
| onMouseOver(item, event,this)   | 鼠标悬浮事件。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |
| onMouseEnter(item, event,this)   | 鼠标进入被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |
| onMouseLeave(item, event,this)    | 鼠标离开被选元素时。 <br> item:当前鼠标数据对象。 <br>event: 事件对象<br> this: 当前对象 |   Function    |     -     |


```js
var inmap = new inMap.Map({
    id: 'allmap',
    skin: "Blueness",
    center: [116.407395, 39.904211],
    zoom: {
        value: 12,
        show: true,
        max: 18,
        min: 5
    },
})
var map = inmap.getMap();
let s = 'http://www.wulihub.com.cn/go/JPVkkW/';

function createCircleOverlay() {
    let img = new Image();
    img.src = s + 'dot_mine.png';

    let hoverImg = new Image();
    hoverImg.src = s + 'dot_hover.png';

    let overlay = new inMap.CircleOverlay({
        name: '蓝色圈图',
        tooltip: {
            show: true,
            customClass: "img",
            offsets: {
                top: -50,
                left: 12,
                bottom: 30
            },
            async formatter(params, dom) {
                let arrowBottom = ''
                setTimeout(() => {
                    let b = dom.getAttribute('data-bottom');
                    // console.log(dom, b)
                    if (b !== null) {
                        arrowBottom = 'margin-top:' + (b - 20) + 'px';
                    } else {
                        arrowBottom = 'margin-top:18px';
                    }
                }, 200)

                let message;
                if (params.incomeMonthly == '0') {
                    message = '月流水未上传';
                } else {
                    message = '月流水<em>' + params.incomeMonthly + '</em>元';
                }

                return (`
                        <div class="mapLabel">
                            <div class="arraw" style="${arrowBottom}"></div>
                            <div class="edit"></div>
                            <div class="header">
                                <div class="name">${params.name}</div>
                                <div class="type">我的门店</div>
                            </div>
                            <div class="content">
                                <div class="box addr">
                                    <span>地址</span>
                                    <span>${params.address}</span>
                                </div>
                                <div class="box">
                                    <span>月营业额</span>
                                    <span>${message}</span>
                                </div>
                                <div class="box">
                                    <span>面积</span>
                                    <span>${params.area}</span>
                                </div>
                                <div class="box">
                                    <span>租金</span>
                                    <span>${params.rent}</span>
                                </div>
                                <div class="box">
                                    <span>经营状况</span>
                                    <span>${params.situation}</span>
                                </div>
                            </div>
                        </div>`);

            },
        },
        style: {
            normal: {
                rangeShow: true,
                icon: img,
                width: 24,
                height: 24,
                offsets: {
                    top: "-90%",
                    left: "-40%",
                },
                backgroundColor: 'rgba(129, 186, 246, 0.10)',
                borderColor: "rgba(45, 140, 240, 0.60)",
                borderWidth: 1,
                unit: 'm',
                size: 500
            },
            mouseOver: {
                icon: hoverImg,
                width: 24,
                height: 24,
                offsets: {
                    top: "-90%",
                    left: "-40%",
                },
                backgroundColor: 'rgba(56,72,195,0)'
            },
        },
        event: {
            onState: (state) => {}
        }
    });
    //去掉点击事件
    overlay.type = 'CIRCLEOVERLAY';
    inmap.add(overlay);
    // overlay.hide()
    // overlay.setTooltipIsShow(false);
    return overlay;
}


function show() {
    // console.log('show')
    let list = map.getOverlays();
    let arr = [];
    list.map((overlay, index) => {
        if (overlay.type === 'CIRCLEOVERLAY') {
            overlay.show();
            overlay.setTooltipIsShow(true);
        }
    })
}

function hide() {
    // console.log('hide')
    let list = map.getOverlays();
    let arr = [];
    list.map((overlay, index) => {
        if (overlay.type === 'CIRCLEOVERLAY') {
            overlay.hide();
            overlay.setTooltipIsShow(false);
        }
    })
}

function showTip() {
    let list = map.getOverlays();
    let arr = [];
    list.map((overlay, index) => {
        if (overlay.type === 'CIRCLEOVERLAY') {
            overlay.setTooltipIsShow(true)
        }
    })
}

function hideTip() {
    let list = map.getOverlays();
    let arr = [];
    list.map((overlay, index) => {
        if (overlay.type === 'CIRCLEOVERLAY') {
            overlay.setTooltipIsShow(false)
        }
    })
}

function showRange() {
    overlay1.setRangeIsShow(true);
}

function hideRange() {
    overlay1.setRangeIsShow(false);
}

function changeRange() {
    overlay1.setRange({
        unit: 'm',
        size: 1000
    });
}
let points1 = data.data.storeList;
points1.map(item => {
    item.count = 6;
    item.geometry = {
        "type": "Point",
        "coordinates": [String(item.lng), String(item.lat)]
    }
})
let overlay1 = createCircleOverlay();
overlay1.setData(points1);
overlay1.setZIndex(600);
```