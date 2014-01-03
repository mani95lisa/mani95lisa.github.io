<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>HTML初级教程</title>
<link rel="stylesheet" href="http://iiiui.qiniudn.com/base.css" />
<script type="text/javascript" src="http://iiiui.qiniudn.com/MathJax.js"></script>
</head>
<body><div class="container"><blockquote>
  <p>初级教程针对第一次接触HTML或接触过但想再系统梳理下基础知识的朋友</p>
</blockquote>

<p id="start"></p>

<p><div class="toc">
<ul>
<li><a href="#开始">开始</a></li>
<li><a href="#标签属性和元素">标签、属性和元素</a><ul>
<li><a href="#标签">标签</a></li>
<li><a href="#属性">属性</a></li>
<li><a href="#元素">元素</a></li>
</ul>
</li>
<li><a href="#页面标题">页面标题</a></li>
<li><a href="#段落">段落</a></li>
<li><a href="#文本标题">文本标题</a></li>
<li><a href="#列表">列表</a></li>
<li><a href="#链接">链接</a></li>
<li><a href="#图片">图片</a></li>
<li><a href="#表格">表格</a></li>
<li><a href="#表单">表单</a><ul>
<li><a href="#form">form</a></li>
<li><a href="#input">input</a></li>
<li><a href="#textarea">textarea</a></li>
<li><a href="#select">select</a></li>
</ul>
</li>
</ul>
</div>
</p>

<h1 id="开始">开始</h1>

<p>使用任何文本编辑器，创建一个新的文本，并输入以下信息：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="typ">Hello</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span></code></pre>

<p>保存文本并将其命名为<code>index.html</code>，这就完成了我们第一个HTML页面的实现，用浏览器打开即可看到实际效果。</p>

<h1 id="标签属性和元素">标签、属性和元素</h1>

<h2 id="标签">标签</h2>

<p>HTML文档的基础结构里包含很多标签，将之前内容改为：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
</span><span class="tag">&lt;body&gt;</span><span class="pln">
    Hello World!
</span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>这样保存后浏览，跟之前的看起来一样，因为html标签的作用只是赋予含义而已。<a href="http://www.w3schools.com/tags/tag_doctype.asp"><code>&lt;!DOCTYPE html&gt;</code></a>就是<code>document type declaration</code>，比如说这里的标识就是告诉浏览器这是HTML5文档便其识别处理，记住在任何html页面都加上该标识即可，IE6也是兼容的，如<a href="https://hsivonen.fi/doctype/">这篇文章</a>所言。</p>

<p><code>&lt;html&gt;</code>和<code>&lt;/html&gt;</code>分别是起始标签和结束标签，它们用以告诉浏览器所有网页的内容都在它们之间了，至于<code>&lt;body&gt;</code>和<code>&lt;/body&gt;</code>之间的就是所有网页能看到的内容了。只有标签之间有其他内容的时候才必须结对出现，比如<a href="http://www.w3schools.com/tags/tag_br.asp"><code>&lt;br&gt;</code></a>换行标签就可以单独出现。</p>

<h2 id="属性">属性</h2>

<p>属性都在起始标签里，比如：<code>&lt;tag attribute="value"&gt;Content&lt;/tag&gt;</code></p>

<h2 id="元素">元素</h2>

<p>一个标签对即称之为一个元素。比如body<code>标签对</code>叫做一个body<code>元素</code>，一个元素里可能还会有多个其它元素</p>

<h1 id="页面标题">页面标题</h1>

<p>将之前内容改为：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
</span><span class="tag">&lt;head&gt;</span><span class="pln">
    </span><span class="tag">&lt;title&gt;</span><span class="pln">我的第一个页面</span><span class="tag">&lt;/title&gt;</span><span class="pln">
</span><span class="tag">&lt;/head&gt;</span><span class="pln">
</span><span class="tag">&lt;body&gt;</span><span class="pln">
    Hello World!
</span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>这里新加了<code>head</code>和<code>title</code>标签，其中<code>head</code>标签包含了所有页面内不显示出来的信息，其中<code>title</code>又是这些信息中最重要的，它显示在浏览器的选项卡或窗口标题上，包括你收藏该页面的时候也会看到该信息。</p>

<h1 id="段落">段落</h1>

<p>将之前内容改为：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
</span><span class="tag">&lt;head&gt;</span><span class="pln">
    </span><span class="tag">&lt;title&gt;</span><span class="pln">我的第一个页面</span><span class="tag">&lt;/title&gt;</span><span class="pln">
</span><span class="tag">&lt;/head&gt;</span><span class="pln">
</span><span class="tag">&lt;body&gt;</span><span class="pln">
    Hello World!
    你好，世界！
</span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>打开浏览器后发现显示的结果其实是：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="typ">Hello</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span><span class="pln"> </span><span class="pun">你好，世界！</span></code></pre>

<p>因为浏览器不能识别内容所在行，也不能识别多空格，会将代码里的多个空格当做一个空格处理，比如这样的代码跟上面的代码结果一样：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="typ">Hello</span><span class="pln"> </span><span class="typ">World</span><span class="pun">!</span><span class="pln">    </span><span class="pun">你好，世界！</span></code></pre>

<p>这时候就需要借助<code>&lt;p&gt;</code>标签来实现段落功能：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="tag">&lt;p&gt;</span><span class="pln">Hello World!</span><span class="tag">&lt;/p&gt;</span><span class="pln">
</span><span class="tag">&lt;p&gt;</span><span class="pln">你好，世界！</span><span class="tag">&lt;/p&gt;</span></code></pre>

<p>与段落密切相关的还有前面提到过的换行标签<code>&lt;br&gt;</code>，一般来说换行标签这样简单使用即可，除非是在XHTML页面的时候才必须使用<code>&lt;br/&gt;</code>。但是使用<code>&lt;br/&gt;</code>也不会有错，不过根据不包含内容元素不使用闭合标签的约定，HTML中仍然建议使用<code>&lt;br&gt;</code>的格式，与之类似的还有<code>&lt;img&gt;,&lt;input&gt;</code>。</p>

<p>除了换行之外，段落内还有常用的标签：</p>

<pre class="prettyprint prettyprinted" style=""><code><span class="tag">&lt;p&gt;</span><span class="pln">Hello</span><span class="tag">&lt;br&gt;</span><span class="pln">World!</span><span class="tag">&lt;/p&gt;</span><span class="pln">
</span><span class="tag">&lt;p&gt;&lt;em&gt;</span><span class="pln">表示重要的斜体</span><span class="tag">&lt;/em&gt;</span><span class="pln">和</span><span class="tag">&lt;strong&gt;</span><span class="pln">更重要的粗体</span><span class="tag">&lt;/strong&gt;&lt;/p&gt;</span></code></pre>

<p>默认<code>&lt;em&gt;</code>是斜体，<code>&lt;strong&gt;</code>是粗体，从表现层面来说<code>&lt;i&gt;</code>和<code>&lt;em&gt;</code>一样，<code>&lt;b&gt;</code>和<code>&lt;strong&gt;</code>一样，但推荐使用<code>&lt;em&gt;</code>和<code>&lt;strong&gt;</code>，因为<code>i</code>仅仅表达视觉呈现，<code>em</code>还带有语义，对<code>搜索引擎</code>及<code>语音</code>都更友好，比如有的语音在阅读<code>&lt;em&gt;</code>标签的内容时会加强语气。仅在明确不需要语义的情况下才使用<code>&lt;i&gt;</code>这样的标签，具有语义的<code>phase tag</code>列表如下：</p>

<table>
<thead>
<tr>
  <th>标签</th>
  <th>描述</th>
  <th>例子</th>
</tr>
</thead>
<tbody><tr>
  <td><code>&lt;em&gt;</code></td>
  <td>表示强调或重要</td>
  <td><code>你&lt;em&gt;必须&lt;/em&gt;记住</code><br>你<em>必须</em>记住</td>
</tr>
<tr>
  <td><code>&lt;strong&gt;</code></td>
  <td>表示比em更重要</td>
  <td><code>你&lt;strong&gt;必须&lt;/strong&gt;记住</code><br>你<strong>必须</strong>记住</td>
</tr>
<tr>
  <td><code>&lt;dfn&gt;</code></td>
  <td>表示定义术语</td>
  <td><code>&lt;dfn&gt;XHTML&lt;/dfn&gt;中的元素必须闭合</code><br><dfn>XHTML</dfn>中的元素必须闭合</td>
</tr>
<tr>
  <td><code>&lt;code&gt;</code></td>
  <td>表示一段代码，通常呈现为计算机书常用的monospaced字体</td>
  <td><code>&lt;code&gt;I'm code/cdoe&gt;</code><br><code>I’m code</code></td>
</tr>
<tr>
  <td><code>&lt;samp&gt;</code></td>
  <td>表示计算机程序输出，通常在程序文档中使用</td>
  <td><code>&lt;samp&gt;I'm output&lt;/samp&gt;</code><br><samp>I’m output</samp></td>
</tr>
<tr>
  <td><code>&lt;kbd&gt;</code></td>
  <td>表示键盘输入，通常呈现字体跟<code>&lt;code&gt;</code>一样，用以提示需要键盘输入的内容</td>
  <td><code>&lt;kbd&gt;输入文本提示&lt;/kbd&gt;</code><br><kbd>输入文本提示</kbd></td>
</tr>
<tr>
  <td><code>&lt;var&gt;</code></td>
  <td>表示程序变量，通常于<code>&lt;pre&gt;</code>和<code>&lt;code&gt;</code>一起使用</td>
  <td><code>&lt;code&gt;document.write("&lt;var&gt;name&lt;/var&gt;")&lt;/code&gt;</code><br><code>document.write("<var>name</var>")</code></td>
</tr>
</tbody></table>


<h1 id="文本标题">文本标题</h1>

<p>它们分别是<code>h1,h2,h3,h4,h5,h6</code>，其中默认h1最大，h6最小，具体字体大小也可以通过css来进行定义：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
</span><span class="tag">&lt;head&gt;</span><span class="pln">
    </span><span class="tag">&lt;meta</span><span class="pln"> </span><span class="atn">charset</span><span class="pun">=</span><span class="atv">"utf-8"</span><span class="tag">&gt;</span><span class="pln">
    </span><span class="tag">&lt;title&gt;</span><span class="pln">Styled heading styles</span><span class="tag">&lt;/title&gt;</span><span class="pln">
    </span><span class="tag">&lt;style&gt;</span><span class="pln">
        h1 </span><span class="pun">{</span><span class="pln">
          font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln"> </span><span class="lit">0.67em</span><span class="pun">;</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="lit">2.33em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">

        h2 </span><span class="pun">{</span><span class="pln">
          font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln"> </span><span class="lit">0.83em</span><span class="pun">;</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1.67em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">

        h3 </span><span class="pun">{</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1.33em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">

        h4 </span><span class="pun">{</span><span class="pln">
          font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1.17em</span><span class="pun">;</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">

        h5 </span><span class="pun">{</span><span class="pln">
          font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1.5em</span><span class="pun">;</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="pun">.</span><span class="lit">83em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">

        h6 </span><span class="pun">{</span><span class="pln">
          font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln"> </span><span class="lit">2em</span><span class="pun">;</span><span class="pln">
          margin</span><span class="pun">:</span><span class="pln"> </span><span class="pun">.</span><span class="lit">67em</span><span class="pln"> </span><span class="lit">0</span><span class="pun">;</span><span class="pln">
        </span><span class="pun">}</span><span class="pln">
    </span><span class="tag">&lt;/style&gt;</span><span class="pln">
</span><span class="tag">&lt;/head&gt;</span><span class="pln">

</span><span class="tag">&lt;body&gt;</span><span class="pln">
    </span><span class="tag">&lt;h1&gt;</span><span class="pln">Heading 1 (h1)</span><span class="tag">&lt;/h1&gt;</span><span class="pln">
    </span><span class="tag">&lt;h2&gt;</span><span class="pln">Heading 2 (h2)</span><span class="tag">&lt;/h2&gt;</span><span class="pln">
    </span><span class="tag">&lt;h3&gt;</span><span class="pln">Heading 3 (h3)</span><span class="tag">&lt;/h3&gt;</span><span class="pln">
    </span><span class="tag">&lt;h4&gt;</span><span class="pln">Heading 4 (h4)</span><span class="tag">&lt;/h4&gt;</span><span class="pln">
    </span><span class="tag">&lt;h5&gt;</span><span class="pln">Heading 5 (h5)</span><span class="tag">&lt;/h5&gt;</span><span class="pln">
    </span><span class="tag">&lt;h6&gt;</span><span class="pln">Heading 6 (h6)</span><span class="tag">&lt;/h6&gt;</span><span class="pln">
</span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<h1 id="列表">列表</h1>

<p>列表分为三种：</p>

<ul>
<li>无序列表：<code>&lt;ul&gt;</code>也就是<code>u</code>nordered <code>l</code>ists的缩写</li>
<li>有序列表：<code>&lt;ol&gt;</code>也就是<code>o</code>rdered <code>l</code>ists的缩写</li>
<li>定义列表：<code>&lt;dl&gt;</code>也就是<code>d</code>efinition <code>l</code>ists的缩写</li>
</ul>

<p>前两类列表差不多，一般前者列表项标识表现为圆点，后者表现为序列数字，<code>&lt;li&gt;</code>(<code>l</code>ist <code>i</code>tem)标签用以定义列项：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
    </span><span class="tag">&lt;body&gt;</span><span class="pln">

    </span><span class="tag">&lt;ul&gt;</span><span class="pln">
        </span><span class="tag">&lt;li&gt;</span><span class="pln">1</span><span class="tag">&lt;/li&gt;</span><span class="pln">    
        </span><span class="tag">&lt;ul&gt;</span><span class="pln">
            </span><span class="tag">&lt;li&gt;</span><span class="pln">3</span><span class="tag">&lt;/li&gt;</span><span class="pln">
        </span><span class="tag">&lt;/ul&gt;</span><span class="pln">
        </span><span class="tag">&lt;li&gt;</span><span class="pln">2</span><span class="tag">&lt;/li&gt;</span><span class="pln">
    </span><span class="tag">&lt;/ul&gt;</span><span class="pln">

    </span><span class="tag">&lt;ol&gt;</span><span class="pln">
        </span><span class="tag">&lt;li&gt;</span><span class="pln">1</span><span class="tag">&lt;/li&gt;</span><span class="pln">    
        </span><span class="tag">&lt;li&gt;</span><span class="pln">2</span><span class="tag">&lt;/li&gt;</span><span class="pln">
    </span><span class="tag">&lt;/ol&gt;</span><span class="pln">

    </span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>定义列表很少见，也很少用，主要在术语描述的时候使用，其中<code>&lt;dt&gt;</code>表示（<code>d</code>efinition <code>t</code>erm）<code>定义术语</code>，<code>&lt;dd&gt;</code>表示（<code>d</code>efinition <code>d</code>escriptions ）<code>定义描述</code></p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
    </span><span class="tag">&lt;body&gt;</span><span class="pln">

    </span><span class="tag">&lt;h1&gt;</span><span class="pln">一些术语定义</span><span class="tag">&lt;/h1&gt;</span><span class="pln">
</span><span class="tag">&lt;dl&gt;</span><span class="pln">
    </span><span class="tag">&lt;dt&gt;</span><span class="pln">HTML</span><span class="tag">&lt;/dt&gt;</span><span class="pln">
    </span><span class="tag">&lt;dd&gt;</span><span class="pln">Abbreviation for HyperText Markup Language - a language used to make web pages.</span><span class="tag">&lt;/dd&gt;</span><span class="pln">

    </span><span class="tag">&lt;dt&gt;</span><span class="pln">HTML定义</span><span class="tag">&lt;/dt&gt;</span><span class="pln">
    </span><span class="tag">&lt;dd&gt;</span><span class="pln">描述1</span><span class="tag">&lt;/dd&gt;</span><span class="pln">
    </span><span class="tag">&lt;dd&gt;</span><span class="pln">描述2</span><span class="tag">&lt;/dd&gt;</span><span class="pln">
</span><span class="tag">&lt;/dl&gt;</span><span class="pln">

    </span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<h1 id="链接">链接</h1>

<p><strong>HTML</strong>中的<code>H</code>和<code>T</code>表示<code>hypertext</code>，其基本含义就是一个链接文本的系统。锚点标签<strong>a</strong>(anchor)就是用来定义链接的，该标签需要结合链接信息一起使用：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript```"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
    </span><span class="tag">&lt;body&gt;</span><span class="pln">

    </span><span class="tag">&lt;h1</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"h1"</span><span class="tag">&gt;</span><span class="pln">测试链接</span><span class="tag">&lt;/h1&gt;</span><span class="pln">

    </span><span class="tag">&lt;p&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.iiiui.com"</span><span class="tag">&gt;</span><span class="pln">我的博客</span><span class="tag">&lt;/a&gt;&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"index.html"</span><span class="tag">&gt;</span><span class="pln">iiiui</span><span class="tag">&lt;/a&gt;&lt;/p&gt;</span><span class="pln">
    </span><span class="tag">&lt;p&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"#h1"</span><span class="tag">&gt;</span><span class="pln">回到标题</span><span class="tag">&lt;/a&gt;&lt;/p&gt;</span><span class="pln">

    </span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>其中的<code>href</code>是(<code>h</code>ypertext <code>ref</code>erence)链接的目标，可以是：</p>

<ul>
<li>绝对路径，任意网址</li>
<li>相对路径，相对该网页的路径</li>
<li>锚点，该页面内id为锚点值的元素，如上面的h1，点击<a href="#start">这里</a>就可以回到当前页面开始位置</li>
</ul>

<h1 id="图片">图片</h1>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="tag">&lt;img</span><span class="pln"> </span><span class="atn">src</span><span class="pun">=</span><span class="atv">"https://1.gravatar.com/avatar/9b3c7e83caa581e968624a3cd5af11f8?d=https%3A%2F%2Fidenticons.github.com%2F64d01d0c72ab6d7577ed190b45acfaef.png&amp;r=x&amp;s=140"</span><span class="pln"> </span><span class="atn">width</span><span class="pun">=</span><span class="atv">"20"</span><span class="pln"> </span><span class="atn">height</span><span class="pun">=</span><span class="atv">"20"</span><span class="pln"> </span><span class="atn">alt</span><span class="pun">=</span><span class="atv">"我的GitHub头像"</span><span class="tag">&gt;</span></code></pre>

<p>如上所示，<code>&lt;img&gt;</code>标签就表示图片了，其中<code>src</code>表示图片地址，可以是任意图片的绝对地址，也可以是相对于当前页面的相对地址，比如<code>assets/1.jpg</code>，跟<code>&lt;a&gt;</code>很像。 <br>
<code>width</code>和<code>height</code>的属性是很必要的，建议一开始就赋值好，这样页面渲染时就会为图片预留好空间，否则图片加载完成后页面布局会发生变化，影响用户体验。 <br>
<code>alt</code>属性表示（<code>alt</code>ernative description）另一种图片的描述，在图片加载不成功的时候，如果你设置了宽高属性，就会显示出来。</p>

<h1 id="表格">表格</h1>

<p>直接上代码：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="dec">&lt;!DOCTYPE html&gt;</span><span class="pln">
</span><span class="tag">&lt;html&gt;</span><span class="pln">
    </span><span class="tag">&lt;body&gt;</span><span class="pln">

    </span><span class="tag">&lt;table&gt;</span><span class="pln">
        </span><span class="tag">&lt;tr&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 1, cell 1</span><span class="tag">&lt;/td&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 1, cell 2</span><span class="tag">&lt;/td&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 1, cell 3</span><span class="tag">&lt;/td&gt;</span><span class="pln">
        </span><span class="tag">&lt;/tr&gt;</span><span class="pln">
        </span><span class="tag">&lt;tr&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 2, cell 1</span><span class="tag">&lt;/td&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 2, cell 2</span><span class="tag">&lt;/td&gt;</span><span class="pln">
        </span><span class="tag">&lt;/tr&gt;</span><span class="pln">
        </span><span class="tag">&lt;tr&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 3, cell 1</span><span class="tag">&lt;/td&gt;</span><span class="pln">
        </span><span class="tag">&lt;/tr&gt;</span><span class="pln">
        </span><span class="tag">&lt;tr&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 4, cell 1</span><span class="tag">&lt;/td&gt;</span><span class="pln">        
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 4, cell 2</span><span class="tag">&lt;/td&gt;</span><span class="pln">
            </span><span class="tag">&lt;td&gt;</span><span class="pln">Row 4, cell 3</span><span class="tag">&lt;/td&gt;</span><span class="pln">
        </span><span class="tag">&lt;/tr&gt;</span><span class="pln">
    </span><span class="tag">&lt;/table&gt;</span><span class="pln">

    </span><span class="tag">&lt;/body&gt;</span><span class="pln">
</span><span class="tag">&lt;/html&gt;</span></code></pre>

<p>效果如下：</p>

<table>
    <tbody><tr>
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
</tbody></table>

<p>其中<code>table</code>元素定义了表格，<code>tr</code>（<code>t</code>able <code>r</code>ow）元素定义了表格行，<code>td</code>（<code>t</code>able <code>d</code>ata cell）元素定义了表格单元，它必须在<code>tr</code>标签内。</p>

<h1 id="表单">表单</h1>

<p>表单是用来收集用户输入数据的，一般在收集后会将数据通过网页发送到服务器进行处理，主要涉及这几个标签：<code>form</code>,<code>input</code>,<code>textarea</code>,<code>select</code>和<code>option</code>。</p>

<h2 id="form">form</h2>

<p><code>&lt;form&gt;</code>标签表示的就是表单，如果表单是给用户提交数据的，那<code>action</code>属性也必须填写上数据提交的地址，与之相关的还有<code>method</code>这个方法，默认是<code>get</code>，如果你提交的数据比较大而且希望安全一些的话，可以改为<code>post</code>，大概就是这样：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="tag">&lt;form</span><span class="pln"> </span><span class="atn">action</span><span class="pun">=</span><span class="atv">"send.php"</span><span class="pln"> </span><span class="atn">method</span><span class="pun">=</span><span class="atv">"post"</span><span class="tag">&gt;</span><span class="pln">
</span><span class="tag">&lt;/form&gt;</span></code></pre>

<p>其中<code>action</code>的地址由后台决定，可以是相对地址或绝对地址。</p>

<h2 id="input">input</h2>

<p><code>input</code>元素这样使用<code>&lt;input type=""&gt;</code>，其中<code>type</code>有很多种，最常用的有：</p>

<ul>
<li><code>text</code>，这也是不指定<code>type</code>时的默认类型</li>
<li><code>password</code>，这是专用于输入密码的，跟<code>text</code>类似，只是会隐藏输入内容</li>
<li><code>checkbox</code>是复选，其中<code>checked</code>属性描述其是否选中</li>
<li><code>radio</code>是单选，在一组<code>radio</code>里只能选择一个，也有<code>checked</code>属性</li>
<li><code>submit</code>是提交按钮，可以通过<code>value</code>控制按钮上的文本</li>
<li><code>image</code>是将图片作为提交按钮</li>
</ul>

<p>还有一些常用的属性：</p>

<ul>
<li><code>name</code> 当作为数据传递的时候，name就是数据的属性，用户输入的信息就是数据的值。</li>
<li><code>value</code> 作为用户输入的值</li>
<li><code>checked</code> 是否核对，用以单选和复选框</li>
<li><code>maxlength</code> 限制文本输入长度</li>
<li><code>src</code> 图片地址</li>
<li><code>readonly="readonly"</code> 不能更改 <code>disabled="disabled"</code> 不能使用</li>
<li><code>tabindex</code> 按<code>Tab</code>键时焦点的顺序索引，默认是按渲染的从先到后的顺序</li>
</ul>

<p>比如写一个注册的表单就是：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="tag">&lt;form</span><span class="pln"> </span><span class="atn">action</span><span class="pun">=</span><span class="atv">"send"</span><span class="pln"> </span><span class="atn">method</span><span class="pun">=</span><span class="atv">"post"</span><span class="tag">/&gt;</span><span class="pln">
        </span><span class="tag">&lt;div&gt;</span><span class="pln">账户： </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text"</span><span class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span class="atv">"account"</span><span class="tag">&gt;</span><span class="pln"> </span><span class="tag">&lt;/div&gt;</span><span class="pln">
        </span><span class="tag">&lt;div&gt;</span><span class="pln">密码： </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"password"</span><span class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span class="atv">"password"</span><span class="tag">&gt;</span><span class="pln"> </span><span class="tag">&lt;/div&gt;</span><span class="pln">
        </span><span class="tag">&lt;div&gt;</span><span class="pln">性别：男 </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"radio"</span><span class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span class="atv">"sex"</span><span class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span class="atv">"1"</span><span class="pln"> </span><span class="atn">checked</span><span class="pun">=</span><span class="atv">"checked"</span><span class="tag">&gt;</span><span class="pln"> 女 </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"radio"</span><span class="pln"> </span><span class="atn">name</span><span class="pun">=</span><span class="atv">"sex"</span><span class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span class="atv">"0"</span><span class="pln"> </span><span class="tag">&gt;&lt;/div&gt;</span><span class="pln">
        </span><span class="tag">&lt;div&gt;</span><span class="pln">同意注册协议 </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"checkbox"</span><span class="tag">&gt;</span><span class="pln">   </span><span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"index.html"</span><span class="tag">&gt;</span><span class="pln">注册协议</span><span class="tag">&lt;/a&gt;&lt;/div&gt;</span><span class="pln">
        </span><span class="tag">&lt;div&gt;&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"image"</span><span class="pln"> </span><span class="atn">src</span><span class="pun">=</span><span class="atv">"http://i202.photobucket.com/albums/aa252/wayneg_03/Website%20Images/submit.png"</span><span class="pln"> </span><span class="tag">/&gt;&lt;/div&gt;</span><span class="pln">
        </span><span class="tag">&lt;button</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"submit"</span><span class="tag">&gt;</span><span class="pln">注册</span><span class="tag">&lt;/button&gt;</span><span class="pln">
        </span><span class="tag">&lt;input</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"submit"</span><span class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span class="atv">"注册"</span><span class="tag">&gt;</span><span class="pln">
</span><span class="tag">&lt;/form&gt;</span></code></pre>

<hr>

<form action="send" method="post">
        <div>账户： <input type="text" name="account"> </div>
        <div>密码： <input type="password" name="password"> </div>
        <div>性别：男 <input type="radio" name="sex" value="1" checked="checked"> 女 <input type="radio" name="sex" value="0"></div>
        <div>同意注册协议 <input type="checkbox">   <a href="index.html">注册协议</a></div>
        <div><input type="image" value="Login" src="http://i202.photobucket.com/albums/aa252/wayneg_03/Website%20Images/submit.png"></div>
        <button type="submit">注册</button>
        <input type="submit" value="注册">
</form>

<hr>

<p>其中写了三种提交触发的实现，分别是<code>image</code>类型和<code>submit</code>类型的<code>input</code>及<code>button</code>，三种实现的作用是一样的，但使用<code>image</code>的时候传递的数据中会携带<code>x,y</code>这样的点击坐标信息。 <br>
HTML5 新增了一些类型: color, date, datetime, datetime-local, month, week, time, email, number, range, search, tel, 及 url，详情<a href="http://www.w3schools.com/tags/att_input_type.asp">见此</a></p>

<h2 id="textarea">textarea</h2>

<p><code>textarea</code>是多行文本输入框，可以通过<code>rows</code>和<code>cols</code>来定义行列大小，一般来说都是用CSS来控制其大小：</p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="tag">&lt;textarea</span><span class="pln"> </span><span class="atn">rows</span><span class="pun">=</span><span class="atv">"4"</span><span class="pln"> </span><span class="atn">cols</span><span class="pun">=</span><span class="atv">"7"</span><span class="tag">&gt;</span><span class="pln">测试下文本框</span><span class="tag">&lt;/textarea&gt;</span></code></pre>

<hr>

<p><textarea rows="4" cols="7">测试下文本框</textarea></p>

<hr>

<h2 id="select">select</h2>

<p>该标签同<code>option</code>标签一起生成下拉选择框，表单发送数据的时候会将其选中的值一起发送，发送的值默认是<code>option</code>标签内的文本，如果有为其指定<code>value</code>则<code>value</code>为发送的值。<code>option</code>可以通过<code>selected</code>属性来实现预选择功能，比如 <select> 
    <option selected="">默认选项</option> 
    <option>选项2</option> 
    <option value="3">选项3</option> 
</select></p>

<pre class="prettyprint prettyprinted" style=""><code class="language-javascript"><span class="tag">&lt;select&gt;</span><span class="pln">
    </span><span class="tag">&lt;option</span><span class="pln"> </span><span class="atn">selected</span><span class="tag">&gt;</span><span class="pln">默认选项</span><span class="tag">&lt;/option&gt;</span><span class="pln">
    </span><span class="tag">&lt;option&gt;</span><span class="pln">选项2</span><span class="tag">&lt;/option&gt;</span><span class="pln">
    </span><span class="tag">&lt;option</span><span class="pln"> </span><span class="atn">value</span><span class="pun">=</span><span class="atv">"3"</span><span class="tag">&gt;</span><span class="pln">选项3</span><span class="tag">&lt;/option&gt;</span><span class="pln">
</span><span class="tag">&lt;/select&gt;</span></code></pre></div></body>
</html>