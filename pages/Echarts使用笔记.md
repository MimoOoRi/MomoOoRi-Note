- ```js
  import ReactEcharts from 'echarts-for-react'
  ```
- ECharts遇到的问题
- loading：showLoading    hideLoading
	- ```js
	  myChart.showLoading();
	  $.get('data.json').done(function (data) {
	      myChart.hideLoading();
	      myChart.setOption(...);
	  });
	  ```
- 遇到的问题：
	- 后台项目数据可视化，获取数据，单独把圆环图摘出来了，但是需要等待请求，做的是异步请求。此时页面已经渲染了，数据还没拿到。
	- 解决方法：watch监听数据长度
- 过渡动画
	- 如果开启[动画](https://echarts.apache.org/zh/option.html#option.animation)的话，ECharts 找到两组数据之间的差异然后通过合适的动画去表现数据的变化。
	- ucharts：animation配置为true
	- echarts：
- ### 为什么用ucharts？
	- 适合多端开发
	- 在线调试，复制代码
- ### 使用uCharts遇到的问题？
	- 开启动画：animation：true
	- 进度条：
		- uCharts
			- `arcbar`展示考勤率，考勤人数
			- 圆环 ：`ring`展示男女比例
		-
- 小程序和vue的区别(双向绑定上)
	- 在小程序中设置data中的数据，需要调用 this.setData方法进行设置
	- 小程序：bindinput绑定事件
		- ```js
		  <button id="btn" data-hi="WeChat" bindtap="testFun"> Click me! </button>
		  ```
	- ucharts打包后体积小  100+kb
	-
- 缓存失效  keep-alive
- vuex 什么时候用哪种方式，分析业务场景
- 数据劫持、发布-订阅模式，实现响应式原理
- 数据劫持：definedProperty，底层是遍历递归，只能监听属性，不能是对象。
- [Dep.target](https://coding.imooc.com/learn/questiondetail/169918.html)
- keep-alive
	- 获取第一个子节点，判断子阶段是不是组件类型，不是不缓存
- 任务循环
	- 一开始整个脚本（script）作为一个宏任务执行
	- 执行过程中同步任务直接执行，异步任务中宏任务进入宏任务队列，微任务进入微任务队列
	- 当前宏任务执行完出栈(stack)，检查微任务队列，有则依次执行，直到全部执行完
	- 执行浏览器UI线程的渲染工作
	- 检查是否有 `Web Worker` 任务，有则执行
	- 执行完本轮的宏任务，回到2，依此循环，直到宏任务和微任务队列都为空
	-
	- 单线程，同步任务在主线程执行，将异步队列放入异步队列。
	- 同步执行完，将异步队列中的一个异步任务放入执行栈执行，
	- 这个不断==循环往复==的过程，就称为事件循环，也就是Event Loop
	- 同步执行完了，循环判断是否有异步要执行。
- async promise
	- 语法简洁，await ES7，语法糖
- 小程序分包
	- pages.json
		- 配置分包规则  subpackage，对象数组，root、pages[path]
- react 中key的作用
	- react采用的是自顶而下的更新策略，每次小的改动都会生成一个全新的的vdom，从而进行diff，如果不写key，就会发生本来应该更新却没有更新
- 2、react中setState什么时候同步什么时候异步
	- 这里所说的同步异步并不是真正的同步异步，
	- setstate本身执行过程是同步的，只是因为在react的合成事件中与钩子函数中执行的顺序在更新之前，所以拿不到更新后的值形成的所谓的异步
- 每天投递量，系统判断活跃度
	- 太低，判定为不着急的
	- 薪资、年限