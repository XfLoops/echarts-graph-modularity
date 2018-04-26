# [ECharts](https://github.com/ecomfe/echarts) graph modularity extension

<a href="http://echarts.baidu.com">
    <img style="vertical-align: top;" src="https://github.com/ecomfe/echarts/raw/master/asset/logo.png?raw=true" alt="logo" height="50px">
</a>

Graph modularity extension will do community detection and partian a graph's vertices in several subsets. Each subset will be assigned a different color.

![](./example/modularity.png)

[**New Feature**] Add a method to access graph community detection result.

```javascript
var communities = chart._api.getCommunities()

console.log(communities)
```
输出如下结果：

```javascript
[
  {
    nodes: ["1"],       // 社群组成节点
    color: "#c23531"    // 节点颜色
  },
  {
    nodes: ["21", "41", "52"],
    color: "#d48265"
  },
  ...
]

```


## Install

```html
<script src="echarts.min.js"></script>
<script src="echarts-graph-modularity.min.js"></script>
```

Or

```shell
npm install echarts-graph-modularity
```

```js
var echarts = require('echarts');
require('echarts-graph-modularity');
```

## Usage

```js
setOption({

    ...

    series: [{
        type: 'graph',
        layout: 'force',
        // Set modularity property true and extension will automatically detect different communities
        // and assign each different color.
        modularity: true

        // Specify resolution. Higher resolution will produce less communities
        modularity: {
            resolution: 5,
            // If sort the communities
            sort: false
        }

        ...
    }]
})
```
