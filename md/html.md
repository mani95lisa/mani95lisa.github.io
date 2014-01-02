> 初级教程针对第一次接触HTML或接触过但想再系统梳理下基础知识的朋友

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
- 定义列表：`<dl>`也就是`d`efinition lists的缩写

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

定义列表很少见，也很少用，主要在术语描述的时候使用，其中`<dt>`表示（ **d** efinition **t** erm）`定义术语`，`<dd>`表示（ **d** efinition **d** escriptions ）`定义描述`

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

  [1]: http://www.w3schools.com/tags/tag_doctype.asp
  [2]: https://hsivonen.fi/doctype/
  [3]: http://www.w3schools.com/tags/tag_br.asp