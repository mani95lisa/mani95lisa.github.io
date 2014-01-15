> 初级教程针对第一次接触JavaScript或接触过但想再系统梳理下基础知识的朋

[TOC]

# 使用

JavaScript在浏览器中使用的时候，一般是同HTML和CSS一起使用的，可以通过`<script>`标签以内部和外部的方式进行使用：

内部

```javascript
<script>
    alert("Hello World!");
</script>
```

外部，直接引用.js格式文件，就像外部CSS文件以.css为后缀一样

```javascript
<script src="script.js"/>
```

还有一个不推荐用的使用方式：`标签属性内`

```javascript
<a href="test.html" onclick="alert('不推荐使用这种调用方式')">链接</a>
```

除了上述方式之外，还有一种开发者常用的在开发者工具控制台进行调用，比如Chrome浏览器的JavaScript Console.

# 变量和数据

<span style="color:red">var </span><sup>关键词</sup> <span style="color:blue">yourname</span><sup>名称</sup> = <span style="color:green">promt</span><sup>方法名</sup>('请输入您的姓名');

```javascript

<script>
    function test(){
        var yourname = prompt('请输入您的姓名');
        alert('您输入的姓名是：'+yourname);
    }
</script>

<button type="button" onclick="test()">测试</button>
```

<button type="button" onclick="yourname = prompt('请输入您的姓名'); alert('您输入的姓名是：'+yourname)">测试</button>

上面的例子声明了一个方法，点击按钮调用方法的时候创建了一个局部变量，在你输入信息后又将存储于局部变量的数据显示了出来。变量的作用可以简单的理解为供程序存取值，创建变量分为声明和初始化两个阶段，`var`是声明变量的关键词，`=`号后的赋值就是变量的初始化，完成创建后该变量即可用于存储和读取值。关于变量总的来说涉及以下三个情况：

1. 声明变量： `var yourname;`，此时该变量为`undefined`，也就是未定义。
2. 初始化变量：<br>`var yourname="test";`此时变量初始化为`string`类型，值为`test`<br>`var yourage=18;`此时变量初始化为`number`类型，值为`20`，只有字符串类型才需要用引号包含起来
3. 赋值：`youname = "Test";` 改变已声明的变量的值

JavaScript的变量属于动态类型，也就是说一个变量可以赋任意类型的值，它支持的数据类型包括：

- `String` 字符串 `var s = "test"`
- `Number` 数字 
 - 普通数字：`var n = 1 //整数1` 或 `var n = 1.1 //小数1.1`
 - 超大或超小数字可以使用科学符号`e`：<br>`var n = 123e5 //超大数字12300000`<br>`var n=123e-5 //超小数字0.00123`
- `Boolean` 只有两个值`true`和`false` 
- `Array` 数组，有三种初始化方式
 - `var arr = new Array()`<br>`arr[0]=0;`<br>`arr[1]="1";`
 - `var arr = new Array(0, "1")`
 - `var arr = [0, "1"]`
- `Object` 对象，其中的value可以为任意数据类型，方法也是一个对象 <br>`var object = {key:"value"}` <br>`object.key = object["key"] = "value"`<br>`object.call=function(){}`
- `Undefined` 声明变量时变量的默认值，也就是没有值
- `null` 用以清空变量的值


# 操作符

JavaScript的操作符相较其他语言会简单一些

## 算术操作符

操作符 | 描述 | 示例 | x | y 
--- | --- | --- | --- | ---
+|加|x=y+1|2|1
-|减|x=y-1|0|1
*|乘|x=y*2|4|2
/|除|x=y/2|1|2
%|求余|x=y%2|1|3
++|递增|x=++y<br>y=1; x=y++|1<br>1|1<br>2
`--`|递减|x=--y<br>y=1; x=y`--`|1<br>1|1<br>0

其中`x=y++`需要注意，该操作相当于`x=y; y++;`，所以x的值就是y的值，但y的值递增了。

## 赋值操作符

默认`x=2,y=3`

操作符 | 示例 | 等同于 | x 
--- | ---|--- | --- | ---
= | x=y || 3
+=|x+=y |x=x+y|5
-=|x-=y |x=x-y|-1
*=|x*=y|x=x*y|6
/=|x/=y|x=x/y|2/3
%=|x%=y|x=x%y|2

如果是字符串相加会将字符串`拼接`起来，如果是字符串和数字相加会将数字转换为字符串，然后`拼接`起来。

# 比较和逻辑判断

默认`x=1`

## 条件语句

只有`if`或`if-else`，比如：

```javascript
//如果x等于1，x递增1
if(x == 1){
    x++;
}

//如果x等于1，x递增1；否则如果x等于2，x递增2；如果上述2个条件都不满足，那x递减1
if(x == 1){
    x++;
}else if(x == 2){
    x+=2;
}else{
    x--;
}
```

## 比较操作符

操作符 | 描述 | 比较 | 结果 
--- | ---|--- | --- |
== | 相等 | x==2<br>x==1|false<br>true
=== |全等(值和类型都相等)|x=="1"<br>x==="1"<br>x===1|true<br>false<br>true
!=|不等|x!=2|true
!==|不全等（值或类型不等）|x!=="1"<br>x!==1|true<br>false
>|大于|x>2|false
<|小于|x<2|true
`>=`|大于等于|x>=1|true
`<=`|小于等于|x<=1|true

比较操作符可用于条件语句中，比如：
```javascript
if(x == 1)
    x++;
```

##逻辑操作符

操作符|描述|示例
-|-|-|
&&|而且|`(x<0 && x>0)`等于false
\|\||或者|`(x<0 \|\| x>0)`等于true
!|非|`!(x==1)`等于false

## 条件操作符

语法:`var result=(condition)?value1:value2`，比如
```javascript
var result=(x != 1) ? 'x不等于1' : 'x等于1';
```

# 循环遍历

用以连续执行一些代码

## while

语法：
```javascript
while(条件)
{
    执行语句
}

do
{
    执行语句
}while(条件);
```

示例：

```javascript
var x=1;
while(x<5)
{
    x++;
}
//这里while相当于if，当x<5的条件成立，就执行x递增，执行完成后x的值为5

do
{
    x--;
}while(x>0);
//于while唯一不同的是，先执行代码再进行条件判断
```

## for

语法:

```javascript
for(声明1;声明2;声明3){
    执行语句
}

//遍历对象的属性
for(var p in object){
    var value = object[p];
}
```

`声明1`在语句执行前就执行
`声明2`是一个是否执行内部代码的条件语句
`声明3`在每次内部代码执行完毕后执行

其中声明1和声明3都可以去掉

示例：

```javascript
var arr = [];
for(var i=0; i<5; i++){
    arr.push(i);
}

//去掉声明1和3
var arr = [1,2];
var i = arr.length;
for(; i<5;){
    arr.push(i);
}

//遍历数组属性获取值
for(var index in arr){
    var value = arr[index];
}
```

# 方法

一个方法就是为实现某个功能的一堆代码的集合。可以直接调用，也可以将其赋值给变量，方法还可以返回值给任意调用它的对象。

语法：
```javascript

//参数数量可以为任意个，但不建议太多
function 方法名(参数1, 参数2)
{
    执行语句
    
    //返回的结果可以赋值给任意调用的对象
    //return还可以用来结束方法的执行
    return 结果; 
}

//参数无法直接像其它语言那样赋默认值
var 方法名 = function(参数1, 参数2)
{
    执行语句
    
    //如果想为参数设置默认值，可以这样处理
    参数1 = typeof 参数1 !== 'undefined' ? 参数1 : 默认值;
}

//方法调用时参数个数不匹配也可以调用成功，调用时传入的参数于方法声明的参数一一对应
方法名();
```

例子：

```javascript
var add = function(x,y){
    if((!x && x!=0) || (!y && y!=0))
        return "x或y不能为空";
    return x+y;
}

add(1,2); //3
add(1);   //"x或y不能为空"
```