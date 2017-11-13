# Css
- border:5px solid red;
- margin: top left-right button;
- display：inline-block;
- position: relative - absolute;
- cursor: point;
- 填满整个元素：父元素设置高度，子元素`height: 100%`
- css度量运算calc(100% - 36px)
- hover显示新元素

		<parent>
			<child1/>
			<child2/>
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
# 对齐
- margin: auto;
- 父元素text-align: left | right | center | justify | inherit;
- 子元素为inline，table-cell或者inline-block时`vertical-align: top | text-top | middle | bottom | text-bottom;`table-cell与inline-block中middle显示不同
- line-height:
- 图文并排

		.dom {
			background:url('/images.jpg') no-repeat;
			padding-left:
			width:
		}
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
- 多根轴线align-content: flex-start | flex-end | center | space-between | space-around | stretch;
- 保留空白符white-space: normal|pre|nowrap|pre-wrap|pre-line|inherit;
# Css单位
- vh：屏幕比例。px:像素。
# Css选择器
- .class	#id	element
- 直接子元素：>

# Html
- 图片按钮`<input name="submit" type="image" value="ee" src="12.jpg" />`
- 赋值`localStorage.abc = string`，数字存入localStorage后变为string :(
- 使用title属性显示提示信息
- 空格：`&nbsp;`
- `<hr />` color属性设置颜色
- ie兼容性`<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">`
- 只要是有src或href的HTML标签都有跨域的能力。
# javaScript
- Boolean && 变量;
* Boolean || 变量;
- `JSON.stringify(json)`, arr也是json格式 `JSON.parse(string)`
- `[...arr, ele, ele]`
- `t=setTimeout(fun(), N毫秒);`与`clearTimeout(t)`;`t=setInterval();`,`clearInterval(t)`;
- `a.indexOf(b)`a为字符串或者--数组
- `a.toFixed(2)`a必须为number，保留小数
- `Array(len).fill(true)` 填满数组
- 数组操作： shift(),unshift(),pop(),push()。改变原数组。
- `window.location`获取当前页面网址信息，可进行页面跳转
- 箭头函数的this，指向其定义位置的this。
- if块级作用域在ES5与ES6中不同
- const a = func; 与function a(){}的变量提升方式不同；
- Object.keys(obj)得到对象的可枚举属性
- `delete 'Obj.prop'`删除对象属性
- 简单的拷贝：`const a = {}`和`a = [...ArrObj]``拷贝属性值，属性值为引用值则拷贝该引用：Object.assign({}, Obj)`
- 字符串变量d的特殊用法：{ [d]: !this.state[d] }
- js不支持负向零宽断言`(?<=aaa)`
- for循环中let 与var i = 0,在函数中不同
- 前端全局对象window，node.js全局变量global。全局变量可以用来设置全局变量window.abc
- async await

		var start = async function () {
			for (var i = 1; i <= 10; i++) {
				console.log(`当前是第${i}次等待..`);
				await sleep(1000);
			}
		};
# node.js
- string操作不改变原string，只会返回新string。Buffer只改变原Buffer。
- bin => dup

		var dup = new Buffer(bin.length);
		bin.copy(dup);
- 附件上传
		const uploadFile = (req, res, next) => {
			//生成multiparty对象，并配置上传目标路径
			var form = new multiparty.Form({uploadDir: './public/files/'});
			//上传完成后处理
			form.parse(req, function(err, fields, files) {
				var inputFile = files.file[0].path;
				console.log('inputFile', inputFile);
				res.writeHead(200, {'content-type': 'text/plain;charset=utf-8'});
				res.end(inputFile);
				//res.end(util.inspect({files: inputFile}));
		});
		};
- 实现文件下载

		router.get('/file/:fileName', function(req, res, next) {
			var fileName = req.params.fileName;
			var filePath = path.join(__dirname, fileName);
			var stats = fs.statSync(filePath);
			if(stats.isFile()){
				res.set({
					'Content-Type': 'application/octet-stream',
					'Content-Disposition': 'attachment; filename='+fileName,
					'Content-Length': stats.size
				});
				fs.createReadStream(filePath).pipe(res);
			} else {
				res.end(404);
			}
		});
前端`<a>`标签加上download属性后就可以下载了

# express
- 使用session
		app.use(session({
			secret: 'recommand 128 bytes random string', // 建议使用 128 个字符的随机字符串
			cookie: { maxAge: 60 * 1000 },
			resave: true,
			saveUninitialized: true
		}));

# git
- git记录删除动作：`rm + git commit -am "abc"` 和`git rm + git commit -m "abc"`
- 更新.gitignore本地缓存删除（改变成未track状态）`git rm -r --cached build/`，然后再修改.gitignore

# Atom快捷键
- Ctrl+( 查看git改动
- Ctrl+shift+m 预览markdown

# 服务器操作
- pm2 list
- pm2 restart 1
- pm2 start backend/bin/xiaochuang
- npm run build
- ssh root@114.123.123.123
- close stuck SSH sessions: `~.`

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
- 代码段落：缩进四个空格

# mongodb
- mongo:打开命令行
- use DBname: 进入数据库 show dbs | show collections
- 导入数据要避免与原来的数据重复：db.COLname.drop 再mongoimport

# Archlinux
study
