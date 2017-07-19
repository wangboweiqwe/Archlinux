# Css
- border:5px solid red;
- margin: top left-right button;
- line-height:
- display：inline-block;
- position: relative - absolute;
- cursor: point;
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

# javaScript
- Boolean && 变量;
* Boolean || 变量;

# React
- 组件的属性(className)给children：{...this.props}

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
- ssh root@114.215.30.227	Zhoushanshan1988

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
# Archlinux
study

# 状态提升
你一定听说过变量提升，函数提升，那么状态提升是什么呢？

首先你得了解双向绑定和单向数据流，双向绑定中，数据可以在不同的组件之间实现共享，这样做的确有很大的好处，但是在react中，不推荐使用双向绑定，而是使用状态提升的方式。

状态提升：state推崇单向数据流，数据从父组件通过props流向子组件，如果你在子组件中，需要修改state来和其他子组件共享数据更新，你需要使用回调函数给使数据更新给父组件，然后从父组件流向其他的子组件，这样做是保证数据有单一的来源。

如果实子组件和子组件之间任意共享数据，那么，后期维护会比较痛苦，特别是找bug的时候。

看一个状态提升的例子吧。
<pre><code>

class Child extends React.Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
  }

  handleChange(e) {
    this.props.upDateValue(e.target.value);
  }

  render() {
    const {name, value} = this.props;
    return (
      <div>
        <p>{name}：</p>
        <input value={value}
               onChange={this.handleChange}
          />
      </div>
    );
  }
}

class Demo extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: '', name: ''};

    this.upDateValue = this.upDateValue.bind(this);
  }

  upDateValue(value) {
    this.setState({value: value})
  }

  render() {
    const {value} = this.state;

    return (
      <div>
        <Child name="组件1" value={value} upDateValue={this.upDateValue} />
        <Child name="组件2" value={value} upDateValue={this.upDateValue} />
      </div>
    );
  }
}

ReactDOM.render(
  <Demo />,
  document.getElementById('root')
);
</pre></code>
<pre><code>传递属性给子组件
const childrenWithProps = React.Children.map(this.props.children,
	child => React.cloneElement(child, {
		publish: this.publishTasks,
	})
);
</pre></code>
