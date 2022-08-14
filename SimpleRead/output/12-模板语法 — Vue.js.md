> [模板语法 — Vue.js](https://cn.vuejs.org/v2/guide/syntax.html)
    Tags:
    Date:  [[2022_05_05  ]]
    Describe:Vue.js - The Progressive JavaScript Framework

- >双大括号会将数据解释为普通文本，而非 HTML 代码。
	- 即不能解析html
	-
- >这个 `span` 的内容将会被替换成为 property 值 `rawHtml`，直接作为 HTML——会忽略解析 property 值中的数据绑定。
	-
	-
- >你的站点上动态渲染的任意 HTML 可能会非常危险，因为它很容易导致 [XSS 攻击](https://en.wikipedia.org/wiki/Cross-site_scripting)。请只对可信内容使用 HTML 插值，**绝不要**对用户提供的内容使用插值。
	- 用户输入内容不能直接插入，比如评论之类
	-
- >如果 `isButtonDisabled` 的值是 `null`、`undefined` 或 `false`，则 `disabled` attribute 甚至不会被包含在渲染出来的 `<button>` 元素中。
	-
	-
-