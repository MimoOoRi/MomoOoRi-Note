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
- Annotation -
	- ![image.png](../assets/image_1661780809204_0.png)
	- ![image.png](../assets/image_1661780952247_0.png)