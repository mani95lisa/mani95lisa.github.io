> 初级教程针对第一次接触HTML或接触过但想再系统梳理下基础知识的朋友

<p id="start"></p>

[TOC]
# 开始 
使用任何文本编辑器，创建一个新的文本，并输入以下信息：
```
Hello World!
```
保存文本并将其命名为`index.html`，这就完成了我们第一个HTML页面的实现，用浏览器打开即可看到实际效果。

# 标签、属性和元素 #
##标签
HTML文档的基础结构里包含很多标签，将之前内容改为：
```
<!DOCTYPE html>
<html>
<body>
    Hello World!
</body>
</html>
```
这样保存后浏览，跟之前的看起来一样，因为html标签的作用只是赋予含义而已。[`<!DOCTYPE html>`][1]就是`document type declaration`，比如说这里的标识就是告诉浏览器这是HTML5文档便其识别处理，记住在任何html页面都加上该标识即可，IE6也是兼容的，如[这篇文章][2]所言。

`<html>`和`</html>`分别是起始标签和结束标签，它们用以告诉浏览器所有网页的内容都在它们之间了，至于`<body>`和`</body>`之间的就是所有网页能看到的内容了。只有标签之间有其他内容的时候才必须结对出现，比如[`<br>`][3]换行标签就可以单独出现。

##属性
属性都在起始标签里，比如：`<tag attribute="value">Content</tag>`

##元素
一个标签对即称之为一个元素。比如body`标签对`叫做一个body`元素`，一个元素里可能还会有多个其它元素

# 页面标题 #

将之前内容改为：
```
<!DOCTYPE html>
<html>
<head>
    <title>我的第一个页面</title>
</head>
<body>
    Hello World!
</body>
</html>
```
这里新加了`head`和`title`标签，其中`head`标签包含了所有页面内不显示出来的信息，其中`title`又是这些信息中最重要的，它显示在浏览器的选项卡或窗口标题上，包括你收藏该页面的时候也会看到该信息。

# 段落 #

将之前内容改为：
```
<!DOCTYPE html>
<html>
<head>
    <title>我的第一个页面</title>
</head>
<body>
    Hello World!
    你好，世界！
</body>
</html>
```
打开浏览器后发现显示的结果其实是：
```
Hello World! 你好，世界！
```
因为浏览器不能识别内容所在行，也不能识别多空格，会将代码里的多个空格当做一个空格处理，比如这样的代码跟上面的代码结果一样：
```
Hello World!    你好，世界！
```
这时候就需要借助`<p>`标签来实现段落功能：
```
<p>Hello World!</p>
<p>你好，世界！</p>
```
与段落密切相关的还有前面提到过的换行标签`<br>`，一般来说换行标签这样简单使用即可，除非是在XHTML页面的时候才必须使用`<br/>`。但是使用`<br/>`也不会有错，不过根据不包含内容元素不使用闭合标签的约定，HTML中仍然建议使用`<br>`的格式，与之类似的还有`<img>,<input>`。

除了换行之外，段落内还有常用的标签：
```
<p>Hello<br>World!</p>
<p><em>表示重要的斜体</em>和<strong>更重要的粗体</strong></p>
```
默认`<em>`是斜体，`<strong>`是粗体，从表现层面来说`<i>`和`<em>`一样，`<b>`和`<strong>`一样，但推荐使用`<em>`和`<strong>`，因为`i`仅仅表达视觉呈现，`em`还带有语义，对`搜索引擎`及`语音`都更友好，比如有的语音在阅读`<em>`标签的内容时会加强语气。仅在明确不需要语义的情况下才使用`<i>`这样的标签，具有语义的`phase tag`列表如下：

标签 | 描述 | 例子
---  | --- | ---
`<em>` | 表示强调或重要 | `你<em>必须</em>记住`<br>你<em>必须</em>记住
`<strong>` | 表示比em更重要 | `你<strong>必须</strong>记住`<br>你<strong>必须</strong>记住
`<dfn>` | 表示定义术语 | `<dfn>XHTML</dfn>中的元素必须闭合`<br><dfn>XHTML</dfn>中的元素必须闭合
`<code>` | 表示一段代码，通常呈现为计算机书常用的monospaced字体 | `<code>I'm code/cdoe>`<br><code>I'm code</cdoe>
`<samp>` | 表示计算机程序输出，通常在程序文档中使用 | `<samp>I'm output</samp>`<br><samp>I'm output</samp>
`<kbd>` | 表示键盘输入，通常呈现字体跟`<code>`一样，用以提示需要键盘输入的内容 | `<kbd>输入文本提示</kbd>`<br><kbd>输入文本提示</kbd>
`<var>` | 表示程序变量，通常于`<pre>`和`<code>`一起使用 | `<code>document.write("<var>name</var>")</code>`<br><code>document.write("<var>name</var>")</code>

# 文本标题

它们分别是`h1,h2,h3,h4,h5,h6`，其中默认h1最大，h6最小，具体字体大小也可以通过css来进行定义：
```javascript
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Styled heading styles</title>
	<style>
		h1 {
		  font-size: 0.67em;
		  margin: 2.33em 0;
		}

		h2 {
		  font-size: 0.83em;
		  margin: 1.67em 0;
		}

		h3 {
		  margin: 1.33em 0;
		}

		h4 {
		  font-size: 1.17em;
		  margin: 1em 0;
		}
		
		h5 {
		  font-size: 1.5em;
		  margin: .83em 0;
		}
		
		h6 {
		  font-size: 2em;
		  margin: .67em 0;
		}
	</style>
</head>

<body>
	<h1>Heading 1 (h1)</h1>
	<h2>Heading 2 (h2)</h2>
	<h3>Heading 3 (h3)</h3>
	<h4>Heading 4 (h4)</h4>
	<h5>Heading 5 (h5)</h5>
	<h6>Heading 6 (h6)</h6>
</body>
</html>
```
# 列表

列表分为三种：

- 无序列表：`<ul>`也就是`u`nordered `l`ists的缩写
- 有序列表：`<ol>`也就是`o`rdered `l`ists的缩写
- 定义列表：`<dl>`也就是`d`efinition `l`ists的缩写

前两类列表差不多，一般前者列表项标识表现为圆点，后者表现为序列数字，`<li>`(`l`ist `i`tem)标签用以定义列项：

```javascript
<!DOCTYPE html>
<html>
    <body>
     
    <ul>
        <li>1</li>    
        <ul>
            <li>3</li>
        </ul>
        <li>2</li>
    </ul>
        
    <ol>
        <li>1</li>    
        <li>2</li>
    </ol>
        
    </body>
</html>
```

定义列表很少见，也很少用，主要在术语描述的时候使用，其中`<dt>`表示（`d`efinition `t`erm）`定义术语`，`<dd>`表示（`d`efinition `d`escriptions ）`定义描述`

```javascript
<!DOCTYPE html>
<html>
    <body>
     
    <h1>一些术语定义</h1>
<dl>
    <dt>HTML</dt>
    <dd>Abbreviation for HyperText Markup Language - a language used to make web pages.</dd>

    <dt>HTML定义</dt>
    <dd>描述1</dd>
    <dd>描述2</dd>
</dl>
        
    </body>
</html>
```

# 链接

**HTML**中的`H`和`T`表示`hypertext`，其基本含义就是一个链接文本的系统。锚点标签**a**(anchor)就是用来定义链接的，该标签需要结合链接信息一起使用：

```javascript```
<!DOCTYPE html>
<html>
    <body>
    
    <h1 id="h1">测试链接</h1>
    
    <p><a href="http://www.iiiui.com">我的博客</a></p>
    <p><a href="index.html">iiiui</a></p>
    <p><a href="#h1">回到标题</a></p>
        
    </body>
</html>
```

其中的`href`是(`h`ypertext `ref`erence)链接的目标，可以是：

- 绝对路径，任意网址
- 相对路径，相对该网页的路径
- 锚点，该页面内id为锚点值的元素，如上面的h1，点击<a href="#start">这里</a>就可以回到当前页面开始位置

# 图片

```javascript
<img src="https://1.gravatar.com/avatar/9b3c7e83caa581e968624a3cd5af11f8?d=https%3A%2F%2Fidenticons.github.com%2F64d01d0c72ab6d7577ed190b45acfaef.png&r=x&s=140" width="20" height="20" alt="我的GitHub头像">
```

如上所示，`<img>`标签就表示图片了，其中`src`表示图片地址，可以是任意图片的绝对地址，也可以是相对于当前页面的相对地址，比如`assets/1.jpg`，跟`<a>`很像。
`width`和`height`的属性是很必要的，建议一开始就赋值好，这样页面渲染时就会为图片预留好空间，否则图片加载完成后页面布局会发生变化，影响用户体验。
`alt`属性表示（`alt`ernative description）另一种图片的描述，在图片加载不成功的时候，如果你设置了宽高属性，就会显示出来。

# 表格

直接上代码：

```javascript
<!DOCTYPE html>
<html>
    <body>
    
    <table>
        <tr>
            <td>Row 1, cell 1</td>
            <td>Row 1, cell 2</td>
            <td>Row 1, cell 3</td>
        </tr>
        <tr>
            <td>Row 2, cell 1</td>
            <td>Row 2, cell 2</td>
        </tr>
        <tr>
            <td>Row 3, cell 1</td>
        </tr>
        <tr>
            <td>Row 4, cell 1</td>        
            <td>Row 4, cell 2</td>
            <td>Row 4, cell 3</td>
        </tr>
    </table>
        
    </body>
</html>
```

效果如下：

<table>
    <tr>
        <td>Row 1, cell 1</td>
        <td>Row 1, cell 2</td>
        <td>Row 1, cell 3</td>
    </tr>
    <tr>
        <td>Row 2, cell 1</td>
        <td>Row 2, cell 2</td>
    </tr>
    <tr>
        <td>Row 3, cell 1</td>
    </tr>
    <tr>
        <td>Row 4, cell 1</td>
        <td>Row 4, cell 2</td>
        <td>Row 4, cell 3</td>
    </tr>
</table>

其中`table`元素定义了表格，`tr`（`t`able `r`ow）元素定义了表格行，`td`（`t`able `d`ata cell）元素定义了表格单元，它必须在`tr`标签内。

# 表单

表单是用来收集用户输入数据的，一般在收集后会将数据通过网页发送到服务器进行处理，主要涉及这几个标签：`form`,`input`,`textarea`,`select`和`option`。

## form

`<form>`标签表示的就是表单，如果表单是给用户提交数据的，那`action`属性也必须填写上数据提交的地址，与之相关的还有`method`这个方法，默认是`get`，如果你提交的数据比较大而且希望安全一些的话，可以改为`post`，大概就是这样：

```javascript
<form action="send.php" method="post">
</form>
```

其中`action`的地址由后台决定，可以是相对地址或绝对地址。

## input

`input`元素这样使用`<input type="">`，其中`type`有很多种，最常用的有：

- `text`，这也是不指定`type`时的默认类型
- `password`，这是专用于输入密码的，跟`text`类似，只是会隐藏输入内容
- `checkbox`是复选，其中`checked`属性描述其是否选中
- `radio`是单选，在一组`radio`里只能选择一个，也有`checked`属性
- `submit`是提交按钮，可以通过`value`控制按钮上的文本
- `image`是将图片作为提交按钮

还有一些常用的属性：

- `name` 当作为数据传递的时候，name就是数据的属性，用户输入的信息就是数据的值。
- `value` 作为用户输入的值
- `checked` 是否核对，用以单选和复选框
- `maxlength` 限制文本输入长度
- `src` 图片地址
- `readonly="readonly"` 不能更改 `disabled="disabled"` 不能使用
- `tabindex` 按`Tab`键时焦点的顺序索引，默认是按渲染的从先到后的顺序

比如写一个注册的表单就是：

```javascript
<form action="send" method="post"/>
        <div>账户： <input type="text" name="account"> </div>
        <div>密码： <input type="password" name="password"> </div>
        <div>性别：男 <input type="radio" name="sex" value="1" checked="checked"> 女 <input type="radio" name="sex" value="0" ></div>
        <div>同意注册协议 <input type="checkbox">   <a href="index.html">注册协议</a></div>
        <div><input type="image" src="http://i202.photobucket.com/albums/aa252/wayneg_03/Website%20Images/submit.png" /></div>
        <button type="submit">注册</button>
        <input type="submit" value="注册">
</form>
```

---

<form action="send" method="post"/>
        <div>账户： <input type="text" name="account"> </div>
        <div>密码： <input type="password" name="password"> </div>
        <div>性别：男 <input type="radio" name="sex" value="1" checked="checked"> 女 <input type="radio" name="sex" value="0" ></div>
        <div>同意注册协议 <input type="checkbox">   <a href="index.html">注册协议</a></div>
        <div><input type="image" value="Login" src="http://i202.photobucket.com/albums/aa252/wayneg_03/Website%20Images/submit.png" /></div>
        <button type="submit">注册</button>
        <input type="submit" value="注册">
</form>

---

其中写了三种提交触发的实现，分别是`image`类型和`submit`类型的`input`及`button`，三种实现的作用是一样的，但使用`image`的时候传递的数据中会携带`x,y`这样的点击坐标信息。
HTML5 新增了一些类型: color, date, datetime, datetime-local, month, week, time, email, number, range, search, tel, 及 url，详情[见此][4]

## textarea

`textarea`是多行文本输入框，可以通过`rows`和`cols`来定义行列大小，一般来说都是用CSS来控制其大小：

```javascript
<textarea rows="4" cols="7">测试下文本框</textarea>
```

---

<textarea rows="4" cols="7">测试下文本框</textarea>

---

## select

该标签同`option`标签一起生成下拉选择框，表单发送数据的时候会将其选中的值一起发送，发送的值默认是`option`标签内的文本，如果有为其指定`value`则`value`为发送的值。`option`可以通过`selected`属性来实现预选择功能，比如 <select>
    <option selected>默认选项</option>
    <option>选项2</option>
    <option value="3">选项3</option>
</select>

```javascript
<select>
    <option selected>默认选项</option>
    <option>选项2</option>
    <option value="3">选项3</option>
</select>
```



  [1]: http://www.w3schools.com/tags/tag_doctype.asp
  [2]: https://hsivonen.fi/doctype/
  [3]: http://www.w3schools.com/tags/tag_br.asp
  [4]: http://www.w3schools.com/tags/att_input_type.asp