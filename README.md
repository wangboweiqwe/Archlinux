# Css
- border:5px solid red;
- margin: top left-right button;
- line-height:
- display：inline-block;
- position: relative - absolute;
- cursor: point;
- hover显示新元素
- display: table-cell; - vertical-align: middle;
<pre><code>
<parent>
	<child1 />
	<child2 />
</parent>
.parent {
	position: relative;
	.child1, .child2 {
		height: 100px;
		width: 100px;
	}
	.child2 {
		display: none;
		background: rgba(230, 230, 230, 0.9);
	}
}
.parent:hover .child2 {
	display: block;
	position: absolute;
	top: 0;
	cursor: pointer;
}
</code></pre>
# 对齐
- margin: auto;
- 父元素text-align: left | right | center | justify | inherit;
- 子元素vertical-align: top | text-top | middle | bottom | text-bottom;
- 图文并排
<pre><code>
{
	background:url('images.jpg') no-repeat;
	padding-left:
	width:
}
</pre></code>
- a {display:inline-block;}再设置 width height
- a {color: #000;}		* 未被访问的链接 *
- a:visited {color: #3ac1bd;}	* 已被访问的链接 *
- a:hover {color: #3ac1bd;}	* 鼠标指针移动到链接上 *
- a:active {color: #3ac1bd;}
# Flex
- 子元素的float、clear和vertical-align属性将失效。
- flex-direction: row | row-reverse | column | column-reverse;
- flex-flow: `flex-direction` || `flex-wrap`;
- justify-content: flex-start | flex-end | center
- align-items: flex-start | flex-end | center
- align-content: flex-start | flex-end | center | space-between | space-around | stretch;

- 保留空白符white-space: normal|pre|nowrap|pre-wrap|pre-line|inherit;
# Css单位
- vh：屏幕比例。px:像素。
# Css选择器
- .class	#id	element

# Html
- 图片按钮`<input name="submit" type="image" value="ee" src="12.jpg" />`
- 赋值`localStorage.abc = string`，数字存入localStorage后变为string :(
- 使用title属性显示提示信息
# javaScript
- Boolean && 变量;
* Boolean || 变量;
- `JSON.stringify(json)`, arr也是json格式 `JSON.parse(string)`
- `[...arr, ele, ele]`
- `t=setTimeout();`与`clearTimeout(t)`;`t=setInterval();`,`clearInterval()`;
- `a.indexOf(b)`a为字符串或者--数组
- `a.toFixed(2)`a必须为number，保留小数
- `Array(len).fill(true)` 填满数组
- `window.location`获取当前页面网址信息，可进行页面跳转
- 箭头函数的this，指向其定义位置的this。
- if块级作用域在ES5与ES6中不同
- const a = func; 与function a(){}的变量提升方式不同；
# node.js
- string操作不改变原string，只会返回新string。Buffer只改变原Buffer。
<pre><code>bin => dup
var dup = new Buffer(bin.length);
bin.copy(dup);
</code></pre>
# git
- git记录删除动作：`rm + git commit -am "abc"` 和`git rm + git commit -m "abc"`

# Atom快捷键
- Ctrl+( 查看git改动
- Ctrl+shift+m 预览markdown

# 服务器操作
- pm2 list
- pm2 restart 1
- pm2 start backend/bin/xiaochuang
- npm run build
- ssh root@114.123.123.123

# Yarn
- yarn add [package]
- yarn add [package]@[version]
- yarn add [package]@[tag]
- yarn upgrade [package]
- yarn remove [package]
- yarn install

# Markdown
- `# ## ###`表示h1,h2,h3
- `-` 代表无序列表
- ` `` `代码字段
- `<pre><code></code></pre>`代码段落
#mongodb
- mongo:打开命令行
- use DBname: 进入数据库 show dbs | show collections
- db.COLname.drop 再mongoimport

# Archlinux
study
