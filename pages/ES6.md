- ## 关键字
	- let、const、var之间的区别
- ## 数组新增
	- 扩展运算符
	- 构造函数新增(静态方法)
		- Array.of
		- Array.from
	- 数组api
		- #### copyWithin
			- 赋值当前数组其他的元素到指定位置(覆盖)
		- flat、`flatMap`
			- flat+Map：扁平化处理后，map处理每个元素，==返回新数组==
		- find、findIndex
		- fill
		- entries、keys、values
		- includes
- ## 对象新增
	- 属性的简写
		- 键值相等，简写
		- 对象中方法简写
			- ```js
			  fn:function(){...}
			  //简写
			  fn(){...}
			  ```
	- 属性名表达式 (方括号)
	- super关键字
		- this指向当前对象(可能是实例)
		- ==super指向当前实例的原型对象==
	- 扩展运算符 (浅拷贝)
	- 属性的遍历
		- for...in
		- Object.keys(不包含Symbol、不可枚举)
		- Object.getOwnPropertyNames(不包含Symbol，包含不可枚举)
		- Object.getOwnPropertySymbols(只包含Symbol) ：键名
		- Reflect.ownKeys：返回自身，不含继承，(包含Symbol、不可枚举)
		- ==属性遍历顺序==
			- 首先遍历所有数值键，按照数值升序排列
			- 其次遍历所有字符串键，按照加入时间升序排列
			- 最后遍历所有 Symbol 键，按照加入时间升序排
			- ```js
			  Reflect.ownKeys({ [Symbol()]:0, b:0, 10:0, 2:0, a:0 })
			  // ['2', '10', 'b', 'a', Symbol()]
			  ```
	- #### 对象新增的方法
		- `Object.is()`：两个值是否相等 (===)
			- +0 和 -0 不等
			- NaN和NaN相等
			- ```js
			  +0 === -0 //true
			  NaN === NaN // false
			  
			  Object.is(+0, -0) // false
			  Object.is(NaN, NaN) // true
			  ```
		- Object.assign()：复制==可枚举==属性，浅拷贝，同名替换
		- `Object.getOwnPropertyDescriptors`()
		- `Object.setPrototypeOf`()，`Object.getPrototypeOf`()
		- Object.keys()，Object.values()，Object.entries()
		- `Object.fromEntries`()
- ## 函数新增
	- 参数
		- 设置默认值
		- 默认声明
		- 解构赋值
			- 参数默认值应该是函数的尾参数，如果不是非尾部的参数设置默认值，实际上这个参数是没发省略的
	- 属性
		- `length`：将返回没有指定默认值的参数个数
			- ```js
			  (function (a) {}).length // 1
			  (function (a = 5) {}).length // 0
			  (function (a, b, c = 5) {}).length // 2
			  ```
			- 截止到==默认值之前==的参数个数
			- 如果设置了默认值的参数不是尾参数，那么length属性也不再计入后面的参数了
			- ```js
			  (function (a = 0, b, c) {}).length // 0
			  (function (a, b = 1, c) {}).length // 1
			  ```
		- `name`
			- `bind`返回的函数，name属性值会加上`bound`前缀
			- Function`构造函数`返回的函数实例，name属性的值为`anonymous`
			- 将一个具名函数赋值给一个变量，则 name属性都返回这个具名函数原本的名字
				- ```js
				  const bar = function baz() {};
				  bar.name // "baz"
				  ```
	- 作用域
	- 严格模式
	- 箭头函数
	  collapsed:: true
		- 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象
		- 不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误
		- 不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替
		- 不可以使用yield命令，因此箭头函数不能用作 Generator 函数
- ## 数据结构新增
	- Set
		- 遍历
		  collapsed:: true
			- `keys`()：返回键名的遍历器
			  `values`()：返回键值的遍历器
			  `entries`()：返回键值对的遍历器
			  `forEach`()：使用回调函数遍历每个成员
			- ```js
			  let set = new Set(['red', 'green', 'blue']);
			  
			  for (let item of set.keys()) {
			    console.log(item);
			  }
			  // red
			  // green
			  // blue
			  
			  for (let item of set.values()) {
			    console.log(item);
			  }
			  // red
			  // green
			  // blue
			  
			  for (let item of set.entries()) {
			    console.log(item);
			  }
			  // ["red", "red"]
			  // ["green", "green"]
			  // ["blue", "blue"]
			  ```
	- Map
		- 遍历：同Set，Iterator对象
	- ### `WeakSet`
		- API
			- 没有遍历操作的API
			  没有size属性
		- WeackSet只能==成员==只能是引用类型，而不能是其他类型的值
			- ```js
			  let ws=new WeakSet();
			  
			  // 成员不是引用类型
			  let weakSet=new WeakSet([2,3]);
			  console.log(weakSet) // 报错
			  
			  // 成员为引用类型
			  let obj1={name:1}
			  let obj2={name:1}
			  let ws=new WeakSet([obj1,obj2]); 
			  console.log(ws) //WeakSet {{…}, {…}}
			  ```
		- WeakSet里面的引用只要在外部消失，它在 WeakSet里面的引用就会自动消失
	- ### `WeakMap`
		- API
			- 没有遍历操作的API
			  没有clear清空方法
- ## Promise
- ## Generator
- ## Proxy
- ## Module
- ## Decorator