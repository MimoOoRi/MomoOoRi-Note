- # 属性概览
	- ## 表格
		- `cellspacing` 单元格之间的间隙，默认为 ==1==
		- `cellpadding` 单元格内，内容距离边框的距离 默认为 ==0==
	- ## 表单 form
		- action：表单数据提交的目标页面
		- type：`submit` | `reset`
			- submit：默认，提交数据
			- reset：重置表单，清空所有表单元素数据，重置为默认
			- method：数据传递方式，参数为 post | get
	- ## Input
		- radio单选框，value 和 name 什么作用？ #card #css
		  id:: 62061932-8158-4f0d-a17a-33ffde4b9e68
			- 两者值的组合，构成键值对，方便后续数据的传递  `key: value`
			- name: 作为后续传递的键名 key
			- value: 设置之后，为输入框的默认数据，不会显示出来，但作为后续传递的值 value
			- 如何达成单选效果？
				- {{cloze 所有input框 name属性值一样}}
				  id:: 62061a43-2dc5-4dbe-a51f-b842d91e1b5c
			- value 和 input对应的label效果一样吗？
				- {{cloze input自闭合，选中后无法直接获取textContent，可以用value。但是获取对应label的textContent也可实现相同效果。但是仅设置value，则只有radio按钮，value值不会显示。label的for需要对应radio的id}}
				  id:: 62061a71-ec3f-4d02-9506-1a7202e250da
			- 同时有多个checked怎么办？
				- {{cloze 前面的覆盖后面的}}
				  id:: 620619f3-2f18-442f-92c7-774c576c1314
	- ## checkbox
		- 配合`&:checked` 可以实现按钮效果
	- ## select
		- 有独立的关闭标签</select>
		- 常见select标签的属性有什么效果？  #card #css
		  id:: 62062566-72e6-4500-8fab-823d68ce7011
			- 提示：disabled | hidden | selected
			- selected {{cloze 默认选中}}
			  id:: 62062666-156d-4082-aadb-beef0b28e5c8
			- disabled {{cloze 当前option不能选中}}
			  id:: 62062692-cf53-4bbb-80f3-2606e84b418a
			- hidden {{cloze 隐藏当前option}}
			  id:: 6206269a-fb87-4993-ac17-c5d8f179d8a2
			- hidden可以替代disabled吗？
				- {{cloze 不能，hidden之后不会显示，disabled之后能显示，不能选中}}
				  id:: 620626f0-7ae7-4e76-bc27-31677ddc8560
	- ### datalist
		- 怎么理解 datalist标签？什么时候用？ #card #css
		  id:: 62075051-1320-4eb4-bf2d-b46db0958f28
			- 实现预选框，起到提示作用，常用在 搜索引擎的联想内容
				- datalist 列举选项，需要和input 中的list属性联动，此类input中，type非必须
				- datalist 中的 id 需要和 input中list属性的值一致
			- 如果option value为空，==不显示==该选项
				- option中，value的值 = 标签内容文本
		- 如何获取input中，下拉datalist选中的值？ #card #操作手册 #JavaScript
		  id:: 62077855-b51a-419b-9edd-cd310145c36e
			- ```js
			  input.addEventListener('change',function(e){
			  var value = e.target.value;
			  });
			  ```
	- ## Animation
collapsed:: true
		- name和duration必须要写
		- ### animation-direction
			- `animation-direction:alternate;` 如何理解？ #card #css #animation
			  id:: 620640f6-98b2-4aad-865e-f9a4aa3d87c5
				- 动画循环播放时，每次都是从结束状态跳回到起始状态，再开始播放。animation-direction属性可以重写该行为。
				-
				- 为什么有的时候没有往返效果？
				- {{cloze 动画只运行一次时，无法触发效果。理解为，第一次顺序播放，第二次从结束位置逆序播放回到起点，但是是两次独立的动画。即前提条件是，循环次数animation-iteration>1。}}
				  id:: 620644c8-8f0b-4d96-8e65-c75cf5b2686e
		- ### animation-fill-mode
			- 如何理解animation-fill-mode？ #card #css #animation
			  id:: 620645bd-0aa0-4075-8ffd-240a90ebaf16
				- 规定当动画不播放时（当动画完成时，或当动画有一个延迟未开始播放时），要应用到元素的样式。
				-
				- 关键值 `forward | backward | both` 有什么区别？
					- forward: {{cloze 动画完成后保持最后一帧动画效果}}
					  id:: 62064644-916e-4aad-a1ce-1736a07fe2d3
					- backward: {{cloze 延迟时间内时，保持第一帧动画效果}}
					  id:: 62064685-da52-4cdd-9b99-33790ba29c50
					- both: {{cloze 延迟时间内保持第一帧，动画完成后保持最后一帧}}
					  id:: 6206468e-87d3-4638-93b9-2f55f1de367d
					- none:{{cloze 延迟时间内，没有动画效果；动画结束后，直接消失}}
					  id:: 6206476c-04e4-4d80-8b4d-2bb80cd8ee72
				-
		- 下列哪些是主动继承哪些是被动继承
		- a标签 伪类选择器书写顺序规则？ #card #css
		  id:: 620664e8-42d9-4850-bfff-99db54852840
			- {{cloze HALV：hover | active | link | visited，active必须放在对应hover之后}}
			  id:: 62066529-4e66-4eb8-ab29-d01a9200855e
			- :active 什么时候触发？
				- {{cloze 用户点击不释放时}}
				  id:: 62066575-2277-40a8-a046-29be141fbe4a
	- ## Background 相关属性
		- ### background-size
collapsed:: true
			- 为什么有时候调节bg-size百分比没有用？ #card #css #background
			  id:: 62070d30-605b-44af-86fc-91de63b2c139
				- {{cloze 如果是img标签，图片大小根据img标签的高宽进行拉伸，bg-size仅能调节作为元素背景的图片大小。}}
				  id:: 62070d6d-dea5-4029-8b5a-946e1578a4a5
				- 百分比是以谁作为参考？
					- {{cloze 父元素}}
					  id:: 62078011-301b-4600-b8e8-c8254ad1a00d
		- ### background-position
			- background-position 控制的是谁的位置？ #card #background #css
			  id:: 62070f13-5467-4474-a5d2-741b7b1ce913
				- {{cloze 控制背景图片，在框内以左上角为原点进行移动。理解为背景图片仅在元素规定高宽、位置内显示，其他部分隐藏，为了展示特定部分而移动。}}
				  id:: 62070f8e-c9b5-410a-913a-970175b46447
				- 该属性默认值是什么？
					- {{cloze 水平垂直居中，即 center center}}
					  id:: 62070ff8-4c8a-4603-8811-ef565de50ca4
		- ### background-attachment
			- 概念：背景图片是否固定，是否不随scroll滚动
	- ## flex 相关属性
collapsed:: true
		- 怎样理解 `flex: 1 1 0;`? #card #css #flex
		  id:: 6207145b-b081-4f62-b462-46b355991811
			- 所有元素平均分配富余空间
			- basis = 0，完全忽略弹性项目自身尺寸 如何理解？
				- {{cloze basis优先级>弹性项目自身高宽，则目前高宽从0开始随缩放变化，则高宽完全由缩放决定。}}
				  id:: 62071556-7a15-4b03-9f9e-9f11ce46a933
		- 怎样理解 `flex: 1 0 auto;` ？ #card #css #flex
		  id:: 62074533-8b0c-4279-93fe-a64bc2c49f15
			- 对于富余空间，弹性项目只增长，不缩进。
			- `flex-basis : auto;`  弹性项目由内容撑开
				- 等同于 `width = fit-content = flex-basis;`
				- 当弹性项目定义了width之后，`flex-basis = width;`
		- 怎样理解 `flex-basis` ？ #card #css #flex
		  id:: 620720a9-f5b2-4c5b-bd26-b67e4fa3f6c2
			- 概念：缩放时，元素的基础值。元素从basis的值开始变化。
			- 宽度属性优先级：{{cloze 不换行的缩放 > `flex-basis` > width}}
			  id:: 62074689-3ee9-4c66-8f5e-79159270d9d3
		- 怎样理解 `flex-shrink` ？ #card #flex #css
		  id:: 620722fc-c64e-4025-8c51-2be6c50f80ed
			- 默认值： {{cloze 1}}
			  id:: 62072309-7933-4526-8518-2bcf81dc4b2e
			- 概念：
collapsed:: true
				- 控制收缩比例，设置为非0时，缩放最小值为弹性项目的min-content
				- min-content: 由文本中 长度最大的单词决定
					- ![https://i.imgur.com/gsSwXyq.png](https://i.imgur.com/gsSwXyq.png){:height 112, :width 93}
			- 弹性盒子缩小时，项目会小于已设置flex-basis的值吗？
				- {{cloze 会，因为优先级 缩放>basis。但不会小于min-content。}}
				  id:: 62072f09-b4cc-4bc0-9f20-0b55428b8f3b
			- 盒子越来越小，小于 所有弹性项目min-content之和 后，会发生什么？1
				- {{cloze 随着盒子变小，弹性盒子继续变小，弹性项目溢出}}
				  id:: 620729fd-fe76-4dc5-bf25-55e911257759
					- ![https://i.imgur.com/AYD3KLq.gif](https://i.imgur.com/AYD3KLq.gif){:height 123, :width 259}
	- ## 列表 ul | ol
		- `list-style-type` 列表项前面的符号
			- circle 空心
			- ==disc== 默认，实心圆点
			- square
			- none
	- ## 其他属性
		- 怎样理解 `white-space` ？ #card #css
		  id:: 6206321b-5e4f-42e9-acc6-2bcb43b57e22
			- 控制如何处理元素中文本的换行和空格
			- ![https://i.imgur.com/QlogbvB.jpg](https://i.imgur.com/QlogbvB.jpg){:height 290, :width 569}
		- table有8px margin？ ul 有8px padding？ 到底是谁有8px的啥？ #card #css
		  id:: 620710c9-3038-4b26-b8c6-aa36ad2ddf79
			- 已查 {{cloze body : 8px(ie.10px) margin |  ul、ol、dd : margin-left:40px padding-left   }}
			  id:: 6207111c-0639-4efb-bb1e-96ec793e03ae
		- ### text-shadow
			- offset-x | offset-y | blur-radius | color
		- ### vertical-align
			- `vertical-align` : 各参数值的区别  #card #css
			  id:: 6209b244-adbc-4e98-b9f2-9de8ac3c9957
				- 一个元素的有六条线，顶线，文本顶线，中线，基线，文本底线，底线
				- 把所有子元素看做父元素的组成部分，父元素的六条线，由所有子元素共同决定。
				- 六条线可能超出父元素设定的高宽，所以有时候子元素bottom对齐会超出父元素
					- ![https://i.imgur.com/xGCm8SU.png](https://i.imgur.com/xGCm8SU.png){:height 89, :width 222}
				-
				- 该属性仅针对标签居中，不针对文本。
				- basement： {{cloze 最高元素顶部对齐父元素content，其基线所在位置是对齐线，其他元素移动，令自身的基线于此处对齐}}
				  id:: 620a0619-1987-4efb-9caa-fb3085c9af18
				- middle：按照中线对齐
				- top：行内最高==行内标签==的顶部对齐，包含最高元素的margin
				- baseline：对齐文字的基线，以X为参考，个别字母超出
				- **text-bottom**：跟父标签的==内容区域==(content)底部对齐
				- **text-top**：跟父标签的==内容区域==(content)顶部对齐,即受父元素padding影响
				- text-top：包含文本元素中，最高元素的content顶部对齐。
				- text-bottom：
				- bottom：跟行内最底部元素的底线对齐
				- 对齐的是border以内的padding+content部分
			- vertical-align的默认值，对于不同的元素，有什么区别？ #card #css
			  id:: 6209cc43-4347-4b07-a10d-c70fc72d10fb
				- 提示：img  |  inline  | inlne-block  默认值： {{cloze baseline}}
				  id:: 6209cc6f-8eee-4a43-a303-2c30479fd0b8
					- 关键区别在于是否是inline-block元素、元素内是否有文本
					- inline元素，无论是否有文本，行高默认，都以有文本的情况下，文本的基线为准
					- inline-block元素
						- **包含文本**，无论inline、inline-block、img、input、button...
							- 都是以==文本的基线==参与对齐，参考字符x的下边缘
						- **不包含文本**，无论inline-block、img、input、button...
							- 都以元素自身的==底部外边缘==参与对齐
							- 包括该元素的padding、border、margin
					- ![https://i.imgur.com/oqtElaC.png](https://i.imgur.com/oqtElaC.png){:height 103, :width 236}
		- `line-height` #居中 #垂直居中
			- 该标签能使==单行==内容垂直居中
			- 参数设置百分比，以元素自身的字体大小为基础。默认==16px==
			- 与其父元素无关，除非继承父元素字体大小
- # 理论整理
	- ## CSS 基础
		- ### 加权计算
			- 4个0
			- 加法
			- 按加法计算法，类、伪类、属性、标签的权重是多少？ #card #css
			  id:: 6207839d-9b6e-422f-a366-0680ec70d44c
				- class  |  [name]  |  :hover    权重为10
				- :before  |  标签    权重为1
		- ### 样式表优先级
collapsed:: true
			- 内嵌 外联 内联 的优先级如何？ #card #css
			  id:: 4348732c-b7d7-4f91-bbdf-b372fbfae5da
				- 内嵌 > 内联 ≈ 外联 (就近原则)
				- 外联和内联都是class，根据头部文件中`<head>`中，引入css文件和<style>标签的先后为止，决定谁优先
			- html、css、js 中的注释行符号分别是什么？ #card #css
			  id:: 9a8b8200-e535-495a-93c8-9be041b4ec14
				- html `<!-- -->`
				- css `/**/`
				- js `//` `/**/`
	- BFC
		- 三栏布局
	- IFC
- # 操作手册
	- 如何实现 下拉框功能中，-请选择xxx-，作为默认选项，点击下拉框后不显示 #card #css
	  id:: 62062f30-fe43-446b-b0d7-7c2fa3d36e80
		-
	- 如何 利用伪元素 实现下方图像 #card #css #brand-new-word
	  id:: 62062fc8-2ca0-4516-9c25-0c65db5e1566
		-
	- 如何 不使用js 实现按钮点击触发效果 #card #css #brand-new-word
	  id:: 6206498a-3c66-48ad-ac48-00a344b1e492
		-
	- 如何 不使用js 实现switch按钮效果？ #card #brand-new-word #css
	  id:: 62064a21-3cb8-48e1-b30a-5c11a8cff3ec
		- ```JavaScript
		  ```
	-
	-
- # BUG合集
	- 为什么直接写行内样式，有时候触发，有时候不会   |  <p width:100px> #card #css
	  id:: 6205fe79-574a-4a35-b856-f618e17c0fe1
		- style标签<style></style>内定义过的属性，行内元素需要写成 {{cloze style='width:100px;'}}
		  id:: 6205feef-33ca-4027-a95f-fa37af01b884
		- 未定义过，行内写 {{cloze width:100px}}
		  id:: 6205ff45-0b05-4fc5-adad-2529e39835aa
		- 但两种写法略有不同
			- style内 `background-color: blue;`
			- html内 `bgcolor = 'blue';`  不推荐
- # 查漏补缺
	- `thead | tbody | th | td | tr` 该怎么组合使用？ #card #css
	  id:: 620601ef-3f6e-4ce1-bad3-998e35a7068d
		- 提示：tr可以放在thead吗？
		- {{cloze thead >tr >th | tbody >tr >td}}
		  id:: 620602b4-5eba-483d-9838-d5c3733a1610
	- 表格中，跨行合并是`colspan` 还是 `rowspan` #card #css
	  id:: 620602f5-9189-496d-a213-002680d8ae3f
		- 行 = row
		- 实践：如果想要同一行两个相邻元素合并，应该用哪一个？
			- {{cloze `colspan` ，也就是跨列合并，横向合并}}
			  id:: 620603f5-a0df-46b0-aa93-65af55d4af89
	- <style> 内写过的元素，直接写行内元素被忽略
		- ((6205fe79-574a-4a35-b856-f618e17c0fe1))
	- 什么时候写href ？ 什么时候写 src ？ #card #css 
	  id:: 62072271-9690-4fd9-86db-698616250ef4
		- ？？？？
	-
- 期末问答整理
	- BFC实现三栏布局 #card #css
	  id:: 6205fe53-8f32-4fce-86d2-21431bd83ee6
		- 浮动、BFC元素同行显示？？？？？？
	- 什么元素自带高度 #card #css
	  card-last-interval:: 4
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2022-02-15T05:52:27.803Z
	  card-last-reviewed:: 2022-02-11T05:52:27.806Z
	  card-last-score:: 3
	  id:: 6205f94b-d26f-4c38-a871-170a498f91bf
		- hr
		- 考虑自闭合元素中，不需要元素撑开，也自带样式
			- {{cloze checkbox，radio等，input 很多都有样式}}
			  id:: 620711b3-66ac-480f-94a2-da16bdfdfff4
	- flex布局相关属性`order`有什么用？数值大小有区别吗？ #card #flex #css
	  id:: 620608bb-b1f1-455f-ae3f-77cd7a1b3275
		- 调整单个弹性项目顺序
		- 两个弹性项目，order参数为 -1 和 1，谁先谁后？
			- {{cloze order 数值越大，弹性项目显示顺序越靠后}}
			  id:: 62060905-85c2-4177-80a4-6dd97bd824b5
		- 如果有两个弹性项目设置相同的order，谁先谁后？
			- {{cloze 按照书写顺序}}
			  id:: 62060b8e-d5b9-47cc-a8f6-a096c94c7d5c
	- align-self 怎么理解？和 align-items、justify-content如何区分？#flex #card #css
	  id:: 62060919-1868-4f51-8289-a3ee300b7a60
		- 提示：以 `flex-direction:row;` 为例
		- justify-content {{cloze 同行元素如何分隔左右富余空间}}
		  id:: 62060ff5-38ce-4ff2-8ea1-f24c619aadd1
		- align-items {{cloze 每行元素作为独立整体，如何分隔上下富余空间}}
		  id:: 6206100c-b38d-47ee-94b2-9d77c5314602
		- align-self {{cloze 针对一行元素中每个弹性项目，分隔这一行的上下富余空间}}
		  id:: 62061016-1e9c-49f7-a6de-73767651e06a
	- flex复合属性拆解成哪几个？有什么用？默认值是多少？ #card #css #flex
	  id:: 6205f9cc-a0cd-4c01-b153-2387c2d061e3
		- flex-grow flex-shrink flex-basis
		- 默认：shrink：1，grow：0
		- 概念：
			- shrink：控制弹性项目缩进
			- grow：控制弹性项目拉伸
		- 对于两者来说，数值越大代表了什么？
			- {{cloze 数值越大，拉伸、缩放效果、比例越明显}}
			  id:: 620607bd-63a4-4b1e-aedd-1e732a26a859
	- 理想视口 | 布局视口 | 视觉视口 区别是什么？ #card #css
	  id:: 6205f976-b7b5-4c47-842f-32c26f57bc26
		- **理想视口**：{{cloze 逻辑}}分辨率，厂商调节后适合手机屏幕大小的视口高宽
		  id:: 6205fa50-cb4a-420b-9f5d-96a774da37e6
		- **布局视口**：默认 ，{{cloze 物理}}分辨率，使用物理像素进行页面布局所使用视口。
		  id:: 6205fa85-87b8-4c41-83a5-b9855d294222
		- **视觉视口**：页面放缩后看到的视口
	- html5　表单元素属性增强了哪些？ 四个 #card #html
	  id:: 6205fc4a-174d-4a15-a3fe-d12b4f22ceb9
		- required：{{cloze 必需填写才能提交}}
		  id:: 6205fc8d-e66a-4a40-a825-d75c85b25bb1
		- autofocus：{{cloze 自动聚焦}}
		  id:: 6205fc99-5a52-4b7a-b225-8e73c8596029
		- disabled：{{cloze 禁止修改，**可以复制**，不能提交}}
		  id:: 6205fc9f-ddd8-43c9-862f-555c841123d9
		- readonly：{{cloze 只能读，不能改，可以提交}}
		  id:: 6205fcab-9859-4e2e-8f12-d73f44e84f7d
	- overflow：hidden 的常见作用 #card #css
	  id:: 6205fc81-e1e1-49e0-bd26-db50b62bdfa0
		- 触发BFC
		- 解决 margin-top 的传递性
	- vertical-align 各个值怎么理解？ #card #css
	  id:: 620606d5-9264-4d3e-a9ee-de585a45535d
		- 提示：top | text-top | middle | baseline | bottom
	-
-