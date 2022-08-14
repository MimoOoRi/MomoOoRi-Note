> [计算属性和侦听器 — Vue.js](https://cn.vuejs.org/v2/guide/computed.html)
    Tags:
    Date:  [[2022_05_05  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >不同的是**计算属性是基于它们的响应式依赖进行缓存的**。只在相关响应式依赖发生改变时它们才会重新求值。这就意味着只要 `message` 还没有发生改变，多次访问 `reversedMessage` 计算属性会立即返回之前的计算结果，而不必再次执行函数。
	-
	-
- >我们为什么需要缓存？假设我们有一个性能开销比较大的计算属性 **A**，它需要遍历一个巨大的数组并做大量的计算。然后我们可能有其他的计算属性依赖于 **A**。如果没有缓存，我们将不可避免的多次执行 **A** 的 getter
	-
	-
- >```
  computed: {
  now: function () {
    return Date.now()
  }
  }
  ```
	- 这也同样意味着下面的计算属性将不再更新，因为 Date.now() 不是响应式依赖
	-
- >当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的。
	-
	-
-
-
-