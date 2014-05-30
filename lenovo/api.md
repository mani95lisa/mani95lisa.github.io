> **API地址**: http://le.pamakids.com/api
**资源地址**:http://lenovour.qiniudn.com
**\***号的参数是必须的
返回的数据对象可能带有**_id**作为唯一标识属性
所有文本输入长度不超过200字
所有语音和视频输入长度不超过60秒
Date类型是国际日期，需要前端进行本地化处理

[TOC]

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
/research/submit<br>**POST**|提交问卷报告<br>`*id` 活动ID<br>`*udid` 设备唯一号<br>`*uid` 用户登录后返回的`_id`<br>`*report` [ReportVO][7]数组JSON字符串|status:true 提交成功 <br> status:false 提交失败

```json
//report示例，JSON后的数组字符串
[{"qid":"5338e3caa3fd4d878e2a9e93","type":4,"value":"3","remark":"test","user_key":"education","user_value":"高中"},{"qid":"5338e3c1a3fd4d878e2a9e91","type":1,"value":[0,1]},{"qid":"5338e3c5a3fd4d878e2a9e92","type":2,"value":0}]
```
##Message
消息通知
URI|Request|[ResultVO][4]
---|---|---
/message/new<br>**GET**|`*uid` 用户ID| result:新消息数，为0则无新消息
/message/list<br>**GET**|`*uid` 用户ID<br>`*page` 页码，默认每页10条|result:[[MessageVO][11]]<br>打开消息列表的时候调用，调用后所有获取到的消息自动read变为true

##Info
资讯
URI|Request|[ResultVO][4]
---|---|---
/info/list<br>**GET**|`*page` 页码|result:[[InfoVO][12]]

##Feedback
反馈
URI|Request|[ResultVO][4]
---|---|---
/feedback/types 获取问题类型数组<br>**GET**||result:[{key:'选项键值',list:['选项']}]
/feedback/submit<br>**POST**|`*user` 用户`_id`<br>`*phone_model` 产品型号<br>`*rom` rom版本<br>`types:[{key:string,value:string}]`选项的key和选择的值value的数组JSON字符串<br>`contact`联系方式，可以是手机号或者邮箱，无需验证数据格式<br>`detail`反馈问题详情<br>`images`图片key值的JSON数组<br>`audio`音频<br>`video`视频<br>|status:true 提交成功
/feedback/list<br>**GET**|`*user`用户id<br>`*page`当前页码，每页默认10条|result:[[FeedbackVO][13]]

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
intro |String|活动介绍，活动开始页显示
thanks |String|感谢语，活动结束后显示，暂时还没出设计稿
questions|[\[QuestionVO\]][8]|问题数组，目前是直接返回所有问题数据|
must_loged_in|Boolean|要参加该活动是否必须登录<br>如果为true，点击开始直接跳转到登录页面，登录后再返回第一题

###QuestionVO
**题目数据对象**
property|	type|	description|	remark
---|---|---|---
title	|String	|问题题目
type|Number|问题类型|`1` 多选 `2` 单选 `3` 排序 `4` 评分 `5` 输入 `6` 星星
image|String|问题配图
user_key|String|问题涉及的用户属性|如果该属性不为空，用户答题后需要赋值到[ReportVO][9]
score_min|Number|评分题最低分
score_max|Number|评分题最高分
score_step|Number|评分题滑动间隔值
star|Number|星星类型的评分，多少星
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
type|Number|问题类型
value|Object|`单选` 选项索引<br>`多选` 选项索引数组<br>`排序` 最终排序索引数组<br>`评分` 分值<br>`星星` 星值<br>`输入` 输入的值|`排序` 比较特殊，返回最终排序的数组就行，比如之前是[0,1,2]<br> 排序后是[2,1,0]表示原始数据的第一个跟第三个调换了顺序
remark|String|选中某些选项需要输入原因的值<br>如果是文本则输入文本，不超过`200`字<br>如果是语音输入则是语音的相对路径
user_key|String|用户信息Key值|`key`为问题的`user_key`
user_value|String|用户信息value值|`value`为答案的`content` `输入`类型题目则不需要填写，会直接使用`value`

##MessageVO
用户收到的消息
property|	type|	description|	remark
---|---|---|---
read|Boolean|是否已读
type|int|消息类型|`1` 活动相关消息
content|String|消息内容|比如邀请您参与什么什么活动之类的
reference|String|关联ID|比如type是1，则是活动的ID，在用户处理消息的时候可以根据活动的ID进入到活动答题首页

##InfoVO
资讯
property|	type|	description|	remark
---|---|---|---
title|String|资讯标题
url|String|完整的资讯html地址|http://lenovour.qiniudn.com/FuD6jsqG7LStzChkL5oc7ETULhbH

##FeedbackVO
反馈
property|	type|	description|	remark
---|---|---|---
types|Array|选择的选项数组|[{key:String,value:String}]
contact|String|联系方式
detail|String|问题详情
images|Array|图片数组
audio|String|音频
video|String|视频

#Flow
##每次打开应用后
```flow
st=>start: 打开应用
e=>end: 登录成功
login1=>operation: 设备号自动登录
login2=>operation: 手机号自动登录
c_signuped=>condition: 已注册
cond=>condition: 手机登录过
st->cond->login1->login2
cond(yes)->login2->e
cond(no)->login1->e
```
##活动
```flow
research_list=>operation: 获取列表
in_research=>operation: 参加活动
c_need_login=>condition: 需登录
c_logined=>condition: 已手机登录
login=>subroutine: 手动登录
feedback=>subroutine: 反馈
submit=>operation: 提交反馈
st_r=>start: 登录成功
research=>subroutine: 活动
feedback=>subroutine: 反馈
info=>subroutine: 资讯
mine=>subroutine: 我的
begin_a=>operation: 开始
answer=>inputoutput: 依次逐题回答
e=>end: 活动结束

st_r->research->research_list->in_research->begin_a->c_need_login
c_need_login(yes)->login->answer
c_need_login(no, left)->answer
answer->research_list
```
##资讯
```flow
st_r=>start: 登录成功
list=>operation: 获取列表
in_list=>operation: 阅读资讯
st_r->list->in_list->list
```


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
  [11]: #messagevo
  [12]: #infovo
  [13]:#feedbackvo