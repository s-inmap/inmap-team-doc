# 增强配置


### 支持命名

| 参数        | 说明   |  类型  |
| --------   | -----:  | :----:  |
| name    | 为canvas命名 |   String     |

``` bash
var styles = {
    name: '云选',
    style: {
        normal: {
            size: 20.6,
            padding: 1,
        },
        colors: [
            "rgba(45,226,142,0.50)"
        ],
        mouseOver: {
            backgroundColor: 'rgba(56,72,195,0.60)'
        },
        selected: {
            backgroundColor: 'rgba(56,72,195,0.60)'
        }
    },
    tooltip: {
        show: true,
        formatter: (params) => {
            let r = params.data.r,
                index = params.data.index,
                str = '',
                bar = 'width:' + Math.floor(r * 100) + '%';

            if (r <= 1.0 && r >= 0.91) {
                str = '非常好'
            }
            if (r <= 0.9 && r >= 0.81) {
                str = '较好';
            }
            if (r <= 0.8 && r >= 0.71) {
                str = '一般';
            }
            if (r <= 0.7 && r >= 0.6) {
                str = '较差';
            }
            return `
            <div class="ml_tooltip">
                <div class="top">
                    <div class="level">
                        <div class="">${str}</div>
                        <div>推荐级别</div>
                    </div>
                    <div class="rank">
                        <div>No.${index}</div>
                        <div>推荐排行</div>
                    </div>
                </div>
                <div class="bar-wrap">
                    <div class="bar" style="${bar}">
                </div>
            </div>
            `;
        },
    },
    legend: {
        show: false
    },
    event: {
        onMouseOver(item, e) {},
        onState(state) {}
    }
}
	
```

### Tooltip对象

1.增加Tooltip弹出框边缘智能控制，通过class名称控制箭头arrow-left、arrow-right

2.增加Tooltip元素绑定事件

3.增加支持异步函数声明,前提是babel没有转义

4.增加pormise支持

``` bash
<!-- 支持异步函数声明 -->
var styles = {
    name: '云选',
    style: {
        normal: {
            size: 20.6,
            padding: 1,
        }
    },
    tooltip: {
        show: true,
        async formatter: (params) => {
            return `
            <div class="ml_tooltip">
            </div>
            `;
        },
    },
    legend: {
        show: false
    },
    event: {
        onMouseOver(item, e) {},
        onState(state) {}
    }
}
    
```

``` bash
<!-- 支持pormise -->
var styles = {
    name: '云选',
    style: {
        normal: {
            size: 20.6,
            padding: 1,
        }
    },
    tooltip: {
        show: true,
        formatter: (params) => {
            return new Promise((resolve, reject) => {
                let str = '<div>22</div>'

                resolve(str);
            });
        },
    },
    legend: {
        show: false
    },
    event: {
        onMouseOver(item, e) {},
        onState(state) {}
    }
}
    
```
[实践案例](https://competent-morse-8518a5.netlify.com/examples/PointOverlay01.html ':include :type=iframe width=100% height=600px')