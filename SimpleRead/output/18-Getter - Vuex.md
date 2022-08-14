> [Getter | Vuex](https://v3.vuex.vuejs.org/zh/guide/getters.html#%E9%80%9A%E8%BF%87%E5%B1%9E%E6%80%A7%E8%AE%BF%E9%97%AE)
    Tags:
    Date:  [[2022_05_06  ]]
    Describe:Vue.js 的中心化状态管理方案

- >Vuex 允许我们在 store 中定义 “getter”（可以认为是 store 的计算属性）。就像计算属性一样，getter 的返回值会根据它的依赖被缓存起来，且只有当它的依赖值发生了改变才会被重新计算。
	- Getter 接受 state 作为其第一个参数：
	  Getter 也可以接受其他 getter 作为第二个参数：
	-
- >Getter 会暴露为 `store.getters` 对象，你可以以属性的形式访问这些值：
	-
	-
- >你也可以通过让 getter 返回一个函数，来实现给 getter 传参。在你对 store 里的数组进行查询时非常有用。
	- 注意，getter 在通过方法访问时，每次都会去进行调用，而不会缓存结果。
	-
- >`mapGetters` 辅助函数仅仅是将 store 中的 getter 映射到局部计算属性
	-
	-