> [模板语法 — Vue.js](https://cn.vuejs.org/v2/guide/syntax.html#%E5%8A%A8%E6%80%81%E5%8F%82%E6%95%B0)
    Tags:
    Date:  [[2022_05_28  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >动态参数预期会求出一个字符串，异常情况下值为 `null`。这个特殊的 `null` 值可以被显性地用于移除绑定。任何其它非字符串类型的值都将会触发一个警告。
	-
	-
- >如空格和引号，放在 HTML attribute 名里是无效的
	- 变通的办法是使用没有空格或引号的表达式，或用计算属性替代这种复杂表达式。
	-
- >需要避免使用大写字符来命名键名，因为浏览器会把 attribute 名全部强制转为小写：
	-
	-