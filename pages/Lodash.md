- `_.chunk`
- `_.compact(arr)`：筛选非假值
	- 假值：`false, null,0, "", undefined, 和 NaN`
- `_.concat(arr,[value])`
	- `[value]` 代表可以为 数组 或 值
- _.difference(arr,[value])
	- 在arr中过滤value中的值
	- 返回新arr
- differenceBy(arr,[value],iterator)
	- iterator：(Array | Function | Object | string)
	- ```js
	  // The `_.property` iteratee shorthand.
	  _.differenceBy([{ 'x': 2 }, { 'x': 1 }], [{ 'x': 1 }], 'x');
	  // => [{ 'x': 2 }]
	  ```
	- 第三个参数可以表明 作为判断依据的==属性==
	- 返回新数组
- differenceWith(arr,[value],comparator)
	- comparator ：Function
- drop(arr,number)
	- 返回剩余切片
	- ==从0开始==切除number个元素
- dropRight(arr,num)
	- 切除尾部num个元素
	- 返回剩余切片
- dropRightWhile：从0开始，结束索引为false(调用第二个参数后返回)
	- 包括为false的元素本身
	- 结束下标：遍历完每一个元素后，==最后一个==返回为==假值==的元素的下标
	- 不是一遇到假值就切
- dropWhile：第一个假值的下标为开始索引，一直到最后
- ==注意==：
	- 判断条件是属性的键名，值是boolean
		- 首先判断是否存在，不存在，为假值
		- 其次是判断该属性的值是否符合条件，不符合，为假值
		- `'active'` = `['active', true]`
			- 即默认为真
- fill(arr,value,start,end)
	- start = 0, end = arr.length
	- 即包含开头，不包含结尾
	- start,end 是下标
	- ```js
	  _.fill([4, 6, 8, 10], '*', 1, 3);
	  // => [4, '*', '*', 10]
	  ```
- findIndex = indexOf
	- findIndex(arr,statement,startIndex)
	- statement即判断条件
- findLastIndex = lastIndexOf
- _.flatten(arr)
	- 减少==一级==嵌套深度
- _.flattenDeep(arr)
	- 将arr递归为一维数组，即全部展开为==一维数组==
	- ```js
	  _.flattenDeep([1, [2, [3, [4]], 5]]);
	  // => [1, 2, 3, 4, 5]
	  ```
- _.flattenDepth(arr,[depth=1])
	- 减少指定层数depth
	- ```js
	  var array = [1, [2, [3, [4]], 5]];
	   
	  _.flattenDepth(array, 1);
	  // => [1, 2, [3, [4]], 5]
	   
	  _.flattenDepth(array, 2);
	  // => [1, 2, 3, [4], 5]
	  ```
- _.head 获取arr第一个元素
- _.indexOf()
- _.initial：去除最后一个元素
- _.tail：去除第一个元素
- intersection：返回交集数组
- intersectionBy：调用后，返回交集
- last：返回最后一个元素
- _.nth(arr,[n=0])：获取第n个元素
	- n为负数，倒数，-1为最后一个，0为第一个
- pull：移除相等元素，
	- 改变原数组，区别于without
- pullAll：接受要移除的数组
	- 改变原数组，区别于 difference
- pullWith：区别于 differenceWith
- pullBy：区别于differenceBy
- pullAt：移除对应元素，返回被移除元素(可移除多个)
	- 改变原数组
- remove：返回为真值的所有元素
	- 区别于filter，remove改变原数组
- reverse：改变原数组
- slice：裁剪，[0，length)，即`不包括end本身位置`
	- 返回新数组
- take(arr,num)：提取num个数组元素
	- 默认num=1
	- 返回新数组
- takeRight：从最后一个开始提取
- takeRightWhile：倒数，直到遇见假值
- takeWhile：正数，直到遇见假值
- union(...arrs)
	- 按原始顺序，依次返回唯一的元素
	- 返回唯一的新一维数组
- unionBy：调用迭代函数，返回 唯一 结果
- uniq：数组去重
	- 返回新数组
- zip、unzip
	- 打包数组
- unzipWith
	- 调用迭代函数，返回新数组
- without：剔除给定值
	- 返回新数组，pull返回原数组
- xor：返回所有数组中==只出现一次==的值
	- 返回新数组
- xorBy：接受一个迭代器
	- 返回新数组
- xorWith：接受一个比较函数
- zipObject(arr1,arr2)
	- zip属性，arr1作为属性key，arr2作为值value，一一对应
- zipObjectDeep
	- 同zipObject，但是第一个参数支持属性路径，即`[a.b, a.c]`
- zipWith(...arr, iteratee)
	- 接受一个迭代函数，指定如何组合多个arr
###  `_.camelCase([string=''])`
	- 小驼峰
###  `_.upperFirst([string=''])`
	- 首字母大写
-