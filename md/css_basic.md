<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>CSS基础教程</title>
<link rel="stylesheet" href="http://iiiui.qiniudn.com/base.css" />
<script type="text/javascript" src="http://iiiui.qiniudn.com/MathJax.js"></script>
</head>
<body><div class="container"><blockquote>
  <p>初级教程针对第一次接触CSS或接触过但想再系统梳理下基础知识的朋友</p>
</blockquote>

<p><div class="toc"><div class="toc">
<ul>
<li><a href="#赋值">赋值</a><ul>
<li><a href="#标签内">标签内</a></li>
<li><a href="#html内">HTML内</a></li>
<li><a href="#html外">HTML外</a></li>
</ul>
</li>
<li><a href="#选择器属性和值">选择器、属性和值</a></li>
<li><a href="#颜色">颜色</a><ul>
<li><a href="#颜色和背景色">颜色和背景色</a></li>
</ul>
</li>
<li><a href="#文本">文本</a><ul>
<li><a href="#font-family">font-family</a></li>
<li><a href="#font-size">font-size</a></li>
<li><a href="#font-weight">font-weight</a></li>
<li><a href="#font-style">font-style</a></li>
<li><a href="#text-decoration">text-decoration</a></li>
<li><a href="#text-transform">text-transform</a></li>
<li><a href="#文本间距">文本间距</a></li>
</ul>
</li>
<li><a href="#元素间距">元素间距</a></li>
</ul>
</div>
</div>
</p>

<h1 id="赋值">赋值</h1>

<p>有三种赋值CSS到HTML的方法，如果以不同方法对同一元素赋值CSS，那么最终只由作用域小的方法决定。</p>

<h2 id="标签内">标签内</h2>

<p>直接通过<code>style</code>属性给HTML标签赋值，只作用于当前标签</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">style</span><span class="pun">=</span><span class="atv">"</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="atv">"</span><span class="tag">&gt;</span><span class="pln">红色文字</span><span class="tag">&lt;/p&gt;</span></code></pre>

<p style="color:red">红色文字</p>

<h2 id="html内">HTML内</h2>

<p>通过<code>&lt;style&gt;</code>标签进行赋值，该标签处于<code>&lt;head&gt;</code>标签之间，其定义的样式作用于整个<code>当前页面</code></p>

<pre class="prettyprint prettyprinted" style=""><code><span class="tag">&lt;style&gt;</span><span class="pln">
    p </span><span class="pun">{</span><span class="pln">
        color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
    a </span><span class="pun">{</span><span class="pln">
        color</span><span class="pun">:</span><span class="pln"> blue</span><span class="pun">;</span><span class="pln">
    </span><span class="pun">}</span><span class="pln">
</span><span class="tag">&lt;/style&gt;</span></code></pre>

<h2 id="html外">HTML外</h2>

<p>外部的样式是供全站页面使用的，以独立的CSS文件形式存在，比如创建style.css</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-css"><span class="pln">p </span><span class="pun">{</span><span class="pln">
    color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;</span><span class="pln">
</span><span class="pun">}</span><span class="pln">
a </span><span class="pun">{</span><span class="pln">
    color</span><span class="pun">:</span><span class="pln"> blue</span><span class="pun">;</span><span class="pln">
</span><span class="pun">}</span></code></pre>

<p>在HTML内使用</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
</span><span class="tag">&lt;head&gt;</span><span class="pln">
    </span><span class="tag">&lt;title&gt;</span><span class="pln">CSS示例</span><span class="tag">&lt;/title&gt;</span><span class="pln">
    </span><span class="tag">&lt;link</span><span class="pln"> </span><span class="atn">rel</span><span class="pun">=</span><span class="atv">"stylesheet"</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"style.css"</span><span class="tag">&gt;</span><span class="pln">
...</span></code></pre>

<h1 id="选择器属性和值">选择器、属性和值</h1>

<div><span style="color:green">body<sup>选择器</sup>{</span></div>

<div style="text-indent: 2em;"><span style="color:blue">font-size<sup>属性</sup></span> : <span style="color:orange">14px<sup>值</sup></span></div>

<p><span style="color:green">}</span></p>

<p>上述CSS代码会将body元素内的文本字体大小设置为14px，其中选择器对应的就是HTML里的标签，属性针对不同标签也有所不同，值的话也是如此，在CSS里有很多东西来度量值，常用的如下：</p>

<ul>
<li><code>px</code> 这是像素的单位，比如 <code>font-size:14px</code></li>
<li><code>em</code> 这是字体的尺寸单位，比如<code>font-size:2em</code>就是当前字体尺寸的2倍，比如你把body的font-size设置为14px，然后将某个body内元素的font-size设置为2em，那么该元素的font-size跟28px等同</li>
<li><code>pt</code> 这是点的单位，主要用以印刷，比如<code>font-size:14pt</code></li>
<li><code>%</code> 这是百分比，不属于任何单位但是很常用，比如<code>width:80%</code></li>
</ul>

<p>当值是0的时候，可以不用带上单位</p>

<h1 id="颜色">颜色</h1>

<p>CSS有16777216种颜色，可以通过<code>名称</code>、<code>RGB</code>值及<code>hex</code>代码使用，比如红色的值可以用以下几种方式设定：</p>

<ul>
<li>red (名称)</li>
<li>rgb(255,0,0) (RGB)</li>
<li>rgb(100%,0%,0%) (RGB)</li>
<li>#ff0000 (hex)</li>
<li>#ff (hex)</li>
</ul>

<p>通过名称的方式只能使用预定义好的颜色值，包括：aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, orange, purple, red, silver, teal, white 以及 yellow 和 transparent，不过不建议使用名称的方式来设置颜色，因为太局限了。</p>

<h2 id="颜色和背景色">颜色和背景色</h2>

<p><code>color</code>和<code>background-color</code>是可以设置颜色的两个属性，比如想要红色文字，黑色背景的文字可以这样实现：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="pln">    </span><span class="tag">&lt;span</span><span class="pln"> </span><span class="atn">style</span><span class="pun">=</span><span class="atv">"</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;</span><span class="pln"> background</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln">black</span><span class="atv">"</span><span class="tag">&gt;</span><span class="pln">红色文字，黑色背景</span><span class="tag">&lt;/span&gt;</span></code></pre>

<p><span style="color:red; background-color:black">红色文字，黑色背景</span></p>

<h1 id="文本">文本</h1>

<p>CSS样式可以控制文本格式的方方面面</p>

<h2 id="font-family">font-family</h2>

<p>文本字体，比如常见的<code>arial</code>,<code>\5b8b\4f53</code>,<code>sans-serif</code>，其中Unicode编码是为了避免因写入中文字体CSS出现“乱码”现象，因此建议写入对应的英文名或是Unicode码。比如<code>\5b8b\4f53</code>对应的就是<code>宋体</code>，<a href="blog/css_fount_unicode.html">更多见此</a>。其中设置的字体是指用户电脑上安装的字体，因为不同用户安装的字体不尽相同，所以一般来说字体都需要设置几种，然后浏览器会自动地从前到后去找匹配的字体使用，比如：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-css"><span class="pln">font</span><span class="pun">-</span><span class="pln">family</span><span class="pun">:</span><span class="pln"> arial</span><span class="pun">,</span><span class="pln"> \5b8b\4f53</span><span class="pun">,</span><span class="pln"> sans</span><span class="pun">-</span><span class="pln">serif</span><span class="pun">,</span><span class="pln"> </span><span class="str">"Times New Roman"</span></code></pre>

<p>还需要注意的就是字体名称如果有空格，就需要使用引号才行。</p>

<h2 id="font-size">font-size</h2>

<p>顾名思义就是字体大小，可以给所有显示文本的标签设置，比如可以将<code>p</code>字体大小设置得比<code>h1</code>还大，不过不推荐这样做。</p>

<h2 id="font-weight">font-weight</h2>

<p>这个属性一般就表示是否是<strong>粗体</strong>，通常来说老的浏览器只支持<code>font-weight:bold</code>和<code>font-weight:normal</code>，新的还有<code>bolder</code>更粗，<code>lighter</code>更细，<code>100,200,300,400(等同于normal)</code>,<code>500,600,700(等同于bold),800,900</code>，新的这些属性一般看不出来差别，因为大多数浏览器不支持，而且也不是所有字体都支持，<a href="http://www.w3.org/TR/CSS2/fonts.html#propdef-font-weight">更多见此</a>。</p><div class="se-section-delimiter"></div>

<h2 id="font-style">font-style</h2>

<p>这个属性就只表示字体是否是斜体，可能的值为：</p>

<ol>
<li><code>font-style:italic</code> <i>斜体</i></li>
<li><code>font-style:normal</code> 正常</li>
</ol><div class="se-section-delimiter"></div>

<h2 id="text-decoration">text-decoration</h2>

<p>这个属性表示是否有横线在字的上面、下面或穿过文字，可能的值为：</p>

<ol>
<li><span style="text-decoration: underline"><code>text-decoration: underline</code></span> 一般用来表示可点击的链接</li>
<li><span style="text-decoration: line-through"><code>text-decoration: line-through</code></span> 一般用来表示内容错误纠正</li>
<li><span style="text-decoration: overline"><code>text-decoration: overline</code></span> 一般没啥用</li>
<li><code>text-decoration: none</code> 想取消上面的状态就设置为<code>none</code>即可</li>
</ol>

<h2 id="text-transform">text-transform</h2>

<p>这个会改变文本的大小写状态：</p>

<ol>
<li><code>&lt;span style="text-transform: capitalize"&gt;have a test&lt;/span&gt;</code> =&gt; <span style="text-transform: capitalize">have a test</span></li>
<li><code>&lt;span style="text-transform: uppercase"&gt;have a test&lt;/span&gt;</code> =&gt; <span style="text-transform: uppercase">have a test</span></li>
<li><code>&lt;span style="text-transform: lowercase"&gt;HaVe a tEst&lt;/span&gt;</code> =&gt; <span style="text-transform: lowercase">HaVe a tEst</span></li>
<li><code>&lt;span style="text-transform: none"&gt;HaVe a tEst&lt;/span&gt;</code> =&gt; <span style="text-transform: none">HaVe a tEst</span></li>
</ol><div class="se-section-delimiter"></div>

<h2 id="文本间距">文本间距</h2>

<p>在文本渲染的时候，<code>letter-spacing</code>和<code>word-spacing</code>是用来定义字母和单词之间间距的，它们的值可以是一个长度或是<code>normal</code>。 <br>
<code>line-weight</code>是设置行高的，可以是相对于字体尺寸的倍数、百分比或<code>normal</code>。 <br>
<code>text-align</code>设置文本在元素内的排列规则，可以是<code>left</code>,<code>right</code>,<code>center</code>,<code>justify</code>，分别表示靠左、靠右、居中和自适应。 <br>
<code>text-indent</code>设置段落第一行的缩进，一般是相对文字尺寸的倍数或百分比，这个属性一般在印刷中使用。 <br>
下面看看这个例子：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-html"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
    </span><span class="tag">&lt;head&gt;</span><span class="pln">        
        </span><span class="tag">&lt;style&gt;</span><span class="pln">                    
            </span><span class="com">#p1 {</span><span class="pln">
                letter</span><span class="pun">-</span><span class="pln">spacing</span><span class="pun">:</span><span class="lit">0.2em</span><span class="pun">;</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln">left</span><span class="pun">;</span><span class="pln">
            </span><span class="pun">}</span><span class="pln">

            </span><span class="com">#p2 {</span><span class="pln">
                word</span><span class="pun">-</span><span class="pln">spacing</span><span class="pun">:</span><span class="lit">0.4em</span><span class="pun">;</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln">right</span><span class="pun">;</span><span class="pln">
            </span><span class="pun">}</span><span class="pln">

            </span><span class="com">#p3 {</span><span class="pln">
                line</span><span class="pun">-</span><span class="pln">height</span><span class="pun">:</span><span class="lit">3</span><span class="pun">;</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln">center</span><span class="pun">;</span><span class="pln">
            </span><span class="pun">}</span><span class="pln">

            </span><span class="com">#p4 {</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">indent</span><span class="pun">:</span><span class="lit">2em</span><span class="pun">;</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln">justify</span><span class="pun">;</span><span class="pln">
                width</span><span class="pun">:</span><span class="lit">400px</span><span class="pun">;</span><span class="pln">
            </span><span class="pun">}</span><span class="pln">

            </span><span class="com">#p5 {</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">indent</span><span class="pun">:</span><span class="lit">2em</span><span class="pun">;</span><span class="pln">
                text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln">left</span><span class="pun">;</span><span class="pln">
                width</span><span class="pun">:</span><span class="lit">400px</span><span class="pun">;</span><span class="pln">
            </span><span class="pun">}</span><span class="pln">
        </span><span class="tag">&lt;/style&gt;</span><span class="pln">        
    </span><span class="tag">&lt;/head&gt;</span><span class="pln">

    </span><span class="tag">&lt;body&gt;</span><span class="pln">

    </span><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"p1"</span><span class="tag">&gt;</span><span class="pln">Let's have a test about Text Spacing</span><span class="tag">&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"p2"</span><span class="tag">&gt;</span><span class="pln">Let's have a test about Text Spacing</span><span class="tag">&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"p3"</span><span class="tag">&gt;</span><span class="pln">Let's have a test about Text Spacing</span><span class="tag">&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"p4"</span><span class="tag">&gt;</span><span class="pln">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</span><span class="tag">&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"p5"</span><span class="tag">&gt;</span><span class="pln">Let's have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</span><span class="tag">&lt;/p&gt;</span><span class="pln">    

    </span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<hr>

<p><span style="letter-spacing:0.2em; text-align:left;">Let’s have a test about Text Spacing</span> <br>
<span style="word-spacing:0.4em;text-align:right;">Let’s have a test about Text Spacing</span> <br>
<span style="line-height:3;text-align:center;">Let’s have a test about Text Spacing</span></p>

<p style="text-indent:2em;text-align:justify;width:400px">Let’s have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>

<p style="text-indent:2em;text-align:left;width:400px">Let’s have a test about Text Spacing. justify属性需要在多行文本的时候才会看到，会自动将行撑满看起来感觉更舒服</p>

<hr><div class="se-section-delimiter"></div>

<h1 id="元素间距">元素间距</h1>

<p>设置元素间距主要跟两个属性有关：<code>margin</code>和<code>padding</code>，前者表示元素同其它<code>外部</code>元素之间的间距，后者表示元素同其它<code>内部</code>元素之间的间距</p></div></body>
</html>