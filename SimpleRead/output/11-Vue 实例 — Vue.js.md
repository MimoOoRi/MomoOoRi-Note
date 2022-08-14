> [Vue 实例 — Vue.js](https://cn.vuejs.org/v2/guide/instance.html)
    Tags:
    Date:  [[2022_04_29  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >只有当实例被创建时就已经存在于 `data` 中的 property 才是**响应式**的。
	-
	-
- >使用 `Object.freeze()`，这会阻止修改现有的 property，也意味着响应系统无法再_追踪_变化
	-
	-
- >Vue 实例还暴露了一些有用的实例 property 与方法。它们都有前缀 `- >，以便与用户定义的 property 区分开来。
	- 比如$ data、$ el
	-
- >每个 Vue 实例在被创建时都要经过一系列的初始化过程——例如，需要设置数据监听、编译模板、将实例挂载到 DOM 并在数据变化时更新 DOM 等。同时在这个过程中也会运行一些叫做**生命周期钩子**的函数，这给了用户在不同阶段添加自己的代码的机会
	- 生命周期的意义：用户在不同阶段添加自己代码的机会
	-
- >因为箭头函数并没有 `this`，`this` 会作为变量一直向上级词法作用域查找，直至找到为止
	-
	-
-
-
-
-
-