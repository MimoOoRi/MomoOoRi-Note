> [动态组件 & 异步组件 — Vue.js](https://cn.vuejs.org/v2/guide/components-dynamic-async.html)
    Tags:
    Date:  [[2022_05_11  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >在一个多标签的界面中使用 `is` attribute 来切换不同的组件：
	-
	-
- >我们更希望那些标签的组件实例能够被在它们第一次被创建的时候缓存下来。为了解决这个问题，我们可以用一个 `<keep-alive>` 元素将其动态组件包裹起来。
	-
	-
- >注意这个 `<keep-alive>` 要求被切换到的组件都有自己的名字，不论是通过组件的 `name` 选项还是局部 / 全局注册。
	-
	-