> [混入 — Vue.js](https://cn.vuejs.org/v2/guide/mixins.html)
    Tags:
    Date:  [[2022_05_11  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >数据对象在内部会进行递归合并，并在发生冲突时以组件数据优先
	-
	-
- >同名钩子函数将合并为一个数组，因此都将被调用。另外，混入对象的钩子将在组件自身钩子**之前**调用。
	-
	-
- >值为对象的选项，例如 `methods`、`components` 和 `directives`，将被合并为同一个对象。两个对象键名冲突时，取组件对象的键值对。
	-
	-
- >混入也可以进行全局注册。使用时格外小心！一旦使用全局混入，它将影响**每一个**之后创建的 Vue 实例
	-
	-