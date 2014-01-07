> 初级教程针对第一次接触CSS或接触过但想再系统梳理下基础知识的朋友

[TOC]

# 赋值

有三种赋值CSS到HTML的方法，如果以不同方法对同一元素赋值CSS，那么最终只由作用域小的方法决定。

## 标签内

直接通过`style`属性给HTML标签赋值，只作用于当前标签

```
<p style="color:red">红色文字</p>
```

<p style="color:red">红色文字</p>

## HTML内

通过`<style>`标签进行赋值，该标签处于`<head>`标签之间，其定义的样式作用于整个`当前页面`

```
<style>
    p {
        color: red;
    }
    a {
        color: blue;
    }
</style>
```

## HTML外

外部的样式是供全站页面使用的，以独立的CSS文件形式存在，比如创建style.css

```css
p {
    color: red;
}
a {
    color: blue;
}
```

在HTML内使用

```
<!DOCTYPE html>
<html>
<head>
    <title>CSS示例</title>
    <link rel="stylesheet" href="style.css">
...
```

# 选择器、属性和值

<div><span style="color:green">body<sup>选择器</sup>{</span></div>
<div style="text-indent: 2em;"><span style="color:blue">font-size<sup>属性</sup></span> : <span style="color:orange">14px<sup>值</sup></span></div>
<span style="color:green">}</span>

上述CSS代码会将body元素内的文本字体大小设置为14px，其中选择器对应的就是HTML里的标签，属性针对不同标签也有所不同，值的话也是如此，在CSS里有很多东西来度量值，常用的如下：

- `px` 这是像素的单位，比如 `font-size:14px`
- `em` 这是字体的尺寸单位，比如`font-size:2em`就是当前字体尺寸的2倍，比如你把body的font-size设置为14px，然后将某个body内元素的font-size设置为2em，那么该元素的font-size跟28px等同
- `pt` 这是点的单位，主要用以印刷，比如`font-size:14pt`
- `%` 这是百分比，不属于任何单位但是很常用，比如`width:80%`

当值是0的时候，可以不用带上单位

# 颜色

CSS有16777216种颜色，可以通过`名称`、`RGB`值及`hex`代码使用，比如红色的值可以用以下几种方式设定：

- red (名称)
- rgb(255,0,0) (RGB)
- rgb(100%,0%,0%) (RGB)
- #ff0000 (hex)
- #ff (hex)

通过名称的方式只能使用预定义好的颜色值，包括：aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, orange, purple, red, silver, teal, white 以及 yellow 和 transparent，不过不建议使用名称的方式来设置颜色，因为太局限了。

## 颜色和背景色

`color`和`background-color`是可以设置颜色的两个属性，比如想要红色文字，黑色背景的文字可以这样实现：

```
    <span style="color:red; background-color:black">红色文字，黑色背景</span>
```

<span style="color:red; background-color:black">红色文字，黑色背景</span>

# 文本

CSS样式可以控制文本格式的方方面面

## font-family

文本字体，比如常见的`arial`,`\5b8b\4f53`,`sans-serif`，其中Unicode编码是为了避免因写入中文字体CSS出现“乱码”现象，因此建议写入对应的英文名或是Unicode码。比如`\5b8b\4f53`对应的就是`宋体`，[更多见此][1]。其中设置的字体是指用户电脑上安装的字体，因为不同用户安装的字体不尽相同，所以一般来说字体都需要设置几种，然后浏览器会自动地从前到后去找匹配的字体使用，比如：

```css
font-family: arial, \5b8b\4f53, sans-serif, "Times New Roman"
```

还需要注意的就是字体名称如果有空格，就需要使用引号才行。

## font-size

顾名思义就是字体大小，可以给所有显示文本的标签设置，比如可以将`p`字体大小设置得比`h1`还大，不过不推荐这样做。

## font-weight

这个属性一般就表示是否是**粗体**，通常来说老的浏览器只支持`font-weight:bold`和`font-weight:normal`，新的还有`bolder`更粗，`lighter`更细，`100,200,300,400(等同于normal)`,`500,600,700(等同于bold),800,900`，新的这些属性一般看不出来差别，因为大多数浏览器不支持，而且也不是所有字体都支持，[更多见此][2]。

## font-style

这个属性就只表示字体是否是斜体，可能的值为：

1. `font-style:italic` <i>斜体</i>
2. `font-style:normal` 正常

## text-decoration

这个属性表示是否有横线在字的上面、下面或穿过文字，可能的值为：

1. <span style="text-decoration: underline">`text-decoration: underline `</span> 一般用来表示可点击的链接
2. <span style="text-decoration: line-through">`text-decoration: line-through `</span> 一般用来表示内容错误纠正
3. <span style="text-decoration: overline">`text-decoration: overline `</span> 一般没啥用
4. `text-decoration: none` 想取消上面的状态就设置为`none`即可

## text-transform

这个会改变文本的大小写状态：

1. `<span style="text-transform: capitalize">have a test</span>` => <span style="text-transform: capitalize">have a test</span>
2. `<span style="text-transform: uppercase">have a test</span>` => <span style="text-transform: uppercase">have a test</span>
3. `<span style="text-transform: lowercase">HaVe a tEst</span>` => <span style="text-transform: lowercase">HaVe a tEst</span>
4. `<span style="text-transform: none">HaVe a tEst</span>` => <span style="text-transform: none">HaVe a tEst</span>

## 文本间距

在文本渲染的时候，`letter-spacing`和`word-spacing`是用来定义字母和单词之间间距的，它们的值可以是一个长度或是`normal`。
`line-weight`是设置行高的，可以是相对于字体尺寸的倍数、百分比或`normal`。
`text-align`设置文本在元素内的排列规则，可以是`left`,`right`,`center`,`justify`，分别表示靠左、靠右、居中和自适应。
`text-indent`设置段落第一行的缩进，一般是相对文字尺寸的倍数或百分比，这个属性一般在印刷中使用。
下面看看这个例子：

```html
<!DOCTYPE html>
<html>
    <head>        
        <style>                    
            #p1 {
                letter-spacing:0.2em;
                text-align:left;
            }
            
            #p2 {
                word-spacing:0.4em;
                text-align:right;
            }
            
            #p3 {
                line-height:3;
                text-align:center;
            }
            
            #p4 {
                text-indent:2em;
                text-align:justify;
                width:400px;
            }
            
            #p5 {
                text-indent:2em;
                text-align:left;
                width:400px;
            }
        </style>        
    </head>
    
    <body>
    
    <p id="p1">Let's have a test about Text Spacing</p>
    <p id="p2">Let's have a test about Text Spacing</p>
    <p id="p3">Let's have a test about Text Spacing</p>
    <p id="p4">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>
    <p id="p5">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>    
        
    </body>
</html>
```

---

<span style="letter-spacing:0.2em; text-align:left;">Let's have a test about Text Spacing</span>
<span style="word-spacing:0.4em;text-align:right;">Let's have a test about Text Spacing</span>
<span style="line-height:3;text-align:center;">Let's have a test about Text Spacing</span>
<p style="text-indent:2em;text-align:justify;width:400px">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>
<p style="text-indent:2em;text-align:left;width:400px">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>

---

# 元素间距

设置元素间距主要跟两个属性有关：`margin`和`padding`，前者表示元素同其它`外部`元素之间的间距，后者表示元素同其它`内部`元素之间的间距



  [1]: blog/css_fount_unicode.html
  [2]: http://www.w3.org/TR/CSS2/fonts.html#propdef-font-weight