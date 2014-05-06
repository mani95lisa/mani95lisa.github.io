> **API地址**: http://le.pamakids.com/api
**资源地址**:http://lenovour.qiniudn.com
**\***号的参数是必须的
所有返回的数据对象都带有**_id**属性，就不再赘述
所有文本输入长度不超过200字
所有语音和视频输入长度不超过60秒

[TOC]
#Flow
```flow
st=>start: 打开应用
e=>end
op=>operation: 登录
cond=>condition: 是否成功

st->op->cond
```
#API
##User
URI|Request|[ResultVO][1]
---|---|---
/user/login<br>**POST**|用户登录，每次打开应用时调用<br>如果有手机号和验证码则必填<br>`*udid` 设备号<br>`*rom` ROM版本<br>`*product_model` 产品型号<br>`mobile`手机号<br> `code` 验证码|result:[UserVO][2]
/user/code<br>**POST**|获取验证码，60秒内只能获取一次<br>`*mobile` 手机号<br>`*udid` 设备号|status:true 成功 <br>status:false 失败
##Token
需要先登录后才能使用，秘钥的有效期间是一天
URI|Request|[ResultVO][3]
---|---|---
/token|上传图片或其他文件的秘钥<br>`*id` 用户id|{status: true, result: token}
/audio/token|上传音频的秘钥<br>`*id` 用户id|{status: true, result: token}
/video/token|上传视频的秘钥<br>`*id` 用户id|{status: true, result: token}
##Research
调查研究相关活动接口
URI|Request|[ResultVO][4]
---|---|---
/research/list<br>**GET**|获取活动列表<br>`*page` 当前页数<br>`uid` 用户id，根据用id获取针对该用户的活动列表<br>`为空则获取面向所有人的活动列表`|result:[\[ResearchVO\]][5]
/research/get<br>**GET**|获取活动详情<br>`*id` 活动ID|result:[ResearchVO][6]
/research/submit<br>**POST**|提交问卷报告<br>`*id` 活动ID<br>`*udid` 设备唯一号<br>`uid` 用户登录后使用<br>`*report` 报告为[ReportVO][7]数组|status:true 提交成功 <br> status:false 提交失败

#Model

##ResultVO 
**数据请求结果通用对象**
property|	type|	description|	remark
---|---|---|---
status	|Boolean	|true:接口请求成功<br>false:接口请求失败	
result|	Object|	任意数据对象，出错后返回错误原因字符串

##UserVO
**用户数据对象，有可能没有密码，直接通过设备唯一号也可以激活一个用户，只要该用户提交了任何内容，比如参与了某个活动或提交了一个反馈**
property|	type|	description|	remark
---|---|---|---
username|String|用户姓名
email|String|用户邮箱
mobile|String|用户手机号
gender|String|性别
birthday|Date|出生日期
udid|String|唯一设备号
pros|[{key:String,value:String}]|用户的附加属性
career_style|String|职业类型
nationality|String|国籍
income|String|收入


----------


##ResearchVO
**调查研究活动数据对象**
property|	type|	description|	remark
---|---|---|---
name	|String	|活动名称|获取活动列表时仅返回该属性
thanks |String|感谢语，活动开始页显示|先不需要重点显示
questions|[\[QuestionVO\]][8]|问题数组，目前是直接返回所有问题数据|
must_loged_in|Boolean|要参加该活动是否必须登录<br>如果为true，点击开始直接跳转到登录页面，登录后再返回第一题

###QuestionVO
**题目数据对象**
property|	type|	description|	remark
---|---|---|---
title	|String	|问题题目
type|Number|问题类型|`1` 多选 `2` 单选 `3` 排序 `4` 评分 `5` 输入
user_key|String|问题涉及的用户属性|如果该属性不为空，用户答题后需要赋值到[ReportVO][9]
score_min|Number|评分题最低分
score_max|Number|评分题最高分
score_step|Number|评分题滑动间隔值
answers|[\[AnswerVO\]][10]|问题的可选答案

####AnswerVO
**题目可选答案数据对象**
property|	type|	description|	remark
---|---|---|---
content	|String	|答案文本内容|有可能为空
image|String|图片选项相对路径|通过imageView2来获得任意尺寸的图片
need_reason|Boolean|是否在选中后需要显示输入框提示用户输入理由

##ReportVO
针对不同类型的问题，选择答案后生成的数据对象
property|	type|	description|	remark
---|---|---|---
qid|String|问题ID
value|Object|`单选` 选项索引<br>`多选` 选项索引数组<br>`排序` 最终排序数组<br>`评分` 分值<br>`输入` 输入的值|`排序` 比较特殊，返回最终排序的数组就行，比如之前是[0,1,2]<br> 排序后是[2,1,0]表示原始数据的第一个跟第三个调换了顺序
remark|String|选中某些选项需要输入原因的值<br>如果是文本则输入文本，不超过`200`字<br>如果是语音输入则是语音的相对路径
user_key|String|用户信息Key值|`key`为问题的`user_key`
user_value|String|用户信息value值|`value`为答案的`content` `输入`类型题目则是 `remark`


  [1]: #resultvo
  [2]: #uservo
  [3]: #resultvo
  [4]: #resultvo
  [5]: #researchvo
  [6]: #researchvo
  [7]: #reportvo
  [8]: #questionvo
  [9]: #reportvo
  [10]: #answervo