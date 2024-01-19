# element+echarts

## 参考

<https://element.eleme.io/#/zh-CN>

<https://echarts.apache.org/zh/index.html>

## 【Echarts】快速上手指南

- 新建一个有长宽、id的DIV：`<div id="main1" style="width: 600px;height:400px;"></div>`
- 导包：`import * as echarts from 'echarts';`
- 定义option：`var option = {title:{},series:[{}]}`
- 初始化dom：`var myChart = echarts.init(document.getElementById('main1'),'dark');`
- 配置数据：`myChart.setOption(option);`
- 设置监听器监听 

> **echarts不会自动帮你渲染数据的，需要手动再次调用setOption函数。**

资料：查vue中echarts动态更改数据的办法（用watched）

```vue
<template>
	<div>
		<div id="main1" style="width: 600px;height:400px;"></div>
	</div>
</template>
<script>
import * as echarts from 'echarts';
import charts from './components/charts.vue'
  // 指定图表的配置项和数据
  var option = {
	title: {
	  text: 'ECharts 入门示例'
	},
	tooltip: {},
	legend: {
	  data: ['销量']
	},
	xAxis: {
	  data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
	},
	yAxis: {},
	series: [
	  {
		name: '销量',
		type: 'bar',
		data: [5, 20, 36, 10, 10, 20]
	  }
	]
  };
export default {
  name: 'app',
    data() {
    return {
		chart: null,
		option: option
    };

  },
  mounted() {
  	// 基于准备好的dom，初始化echarts实例
  	this.chart = echarts.init(document.getElementById('main'));
  	// 使用刚指定的配置项和数据显示图表。
  	this.chart.setOption(option);
  },  
  watch: {
	option: function (val) {
		this.chart.setOption(val)
	},
  }
}
</script>
```
