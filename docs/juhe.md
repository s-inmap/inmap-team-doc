# 聚合能力

### 概述

百度的聚合能力+inmap的canvas渲染，在文档中引入markerClusterer.js

``` bash
<script src="https://smartdata.b0.upaiyun.com/thinkmark/markerClusterer.js"></script>

<script>
//生成聚合实例
let markerClusterer = new BMapLib.MarkerClusterer(map, {
    markers: markers,
    gridSize: 50
});

//返回聚合数据
let result = markerClusterer.getClusters();

//渲染
overlay.setData(result);
</script>
```
[实践案例](https://smartdata.b0.upaiyun.com/inmap/examples/pieOverlay.html ':include :type=iframe width=100% height=600px')

