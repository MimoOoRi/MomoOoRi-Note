- ## slider 滑块
  collapsed:: true
	- 需要单独引入
	  collapsed:: true
		- ```jsx
		  import { Chart Slider Line } from 'bizcharts';
		  
		  <Chart padding="auto" autoFit height={500} data={data} >
		      <Line shape="hv" position="month*value" />
		      <Slider end={0.8} />
		    </Chart>
		  ```
	- ![image.png](../assets/image_1661780299302_0.png)
- ## interaction  交互
  collapsed:: true
	- active-region  鼠标在画布上移动时对应位置的分类出现背景框
	- view-zoom  鼠标==滚动==时，图表内部缩放
	- element-highlight 高亮
	- brush  框选过滤图形
		- brush-x
		- brush-y  把上面 brush Action 换成 brush-y 即成为新的交互，仅框选 y 轴相关的数据
	- ```jsx
	  <Interaction
	      type="tooltip"
	      config={{ // 修改了原有的tooltip交互，改为点击时展示。
	        start: [{ trigger: 'plot:click', action: 'tooltip:show' }],
	      }}
	    />
	  ```
- ## Annotation - 图形标注
  collapsed:: true
	- 支持html、文本、图片、数据点标注(marker，支持'min', 'median', 'max' 关键字)、
	- ![image.png](../assets/image_1661780809204_0.png)
	- ![image.png](../assets/image_1661780952247_0.png)
- ## Facet 分面
	- ![image.png](../assets/image_1661781227335_0.png)
- ## DataSet
	- dataset 数据集
	- transform  数据转换
		- filter、sort、rename(字段重命名)、partition(数据分组：grouoBy、orderBy)、
		- aggregate 聚合统计
		  collapsed:: true
			- ![image.png](../assets/image_1661782067121_0.png)
	- connector
		- CSV 文件 ->  图表
			- ```jsx
			  ds.source(data, {
			        type: 'csv', // 使用 CSV 类型的 Connector 装载 data
			      });
			  ```
			- ![image.png](../assets/image_1661782654135_0.png)
			- ![image.png](../assets/image_1661782639800_0.png)
			-
- ## Hooks
  collapsed:: true
	- Effects
		- ![image.png](../assets/image_1661782339945_0.png)
	- 可以直接使用[G2的语法](https://g2.antv.vision/zh/docs/manual/about-g2)对chart对象进行配置
	- useView  获取view对象
	- useChartInstance 用于获得G2的chart实例的hooks
- watchingStates