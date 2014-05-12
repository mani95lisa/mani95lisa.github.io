> **host**: http://db.pamakids.com
**image_host:**http://drawingboard.qiniudn.com
**\***号的参数是必须的

[TOC]

#API
##User

URI|Request|[ResultVO][1]
---|---|---
/user/signup/app<br>**POST**|***username**<br>***password**<br>***email**<br>***come_from** `用户来源，比如一起画画则固定为DrawingBoard`|results:[UserVO][2]
/user/login/platform<br>**POST**|***come_from**<br>***access_token**<br>***platform**<br>***usid**<br>portrait`头像`<br>nickname`昵称`|results:[UserVO][3]
/user/login<br>**POST**|***username**`该属性可以赋值用户名或者是邮箱`<br>***password**|results:[UserVO][4]
/user/exist<br>**GET**|***username \| email \| usid**`三个属性中必须传一个`|results:true 用户存在<br>results:false 用户不存在
/user/update<br>**POST**|nickname<br>email 如果没有email可以更新，有则不行<br>portrait<br>mobile<br>address<br>birthday`需要使用NodeUtil转换日期格式为：2013-08-30`|status:true 更新成功<br>status:false 更新失败
/user/update/password<br>**POST**|***new** 新密码<br>***old**旧密码|status:true 更新成功<br>status:false 更新失败
/user/relationship<br>**POST**|***friend** 操作对象ID<br>follow `true:关注对方 false:取消关注`|staus:true 成功 <br>status:false 失败
/user/friends<br>**GET**|user_id `为空则默认获取自己的，不为空则获取别人的`<br>***followed** `true：我关注的 false:我的粉丝`<br>***perPage**每页显示多少个<br>***page**当前显示页码|results: [RelationshipVO]


##Upload

URI|Request|[ResultVO][5]
---|---|---
/upload/token<br>**GET**||results:用户上传秘钥凭证
/upload/audio/token<br>**GET**||results:用户上传秘钥凭证，专用于音频上传

##Paint

URI|Request|[ResultVO][6]
---|---|---
/paint/add<br>**POST**|`相关文件都上传成功后再调用该方法，地址为相对路径即可`<br>***cover**`封面地址`<br>***data**`绘图数据地址`<br>audio`录音地址`<br>theme `关联的主题路径`|results:[PaintVO][7]
/paint/list<br>**GET**|***page**`请求页码`<br>result_type` 返回结果类型，默认为 1 返回画廊结构类型，为 2 返回普通类型`<br>author`作者ID，为空则请求所有用户的`<br>favorited`是否只显示已收藏的，默认为flase`<br>followed`是否只显示我关注的，默认为false`<br>theme `关联的主题路径`|`result_type=1`results:[[[PaintVO][7]],[[PaintVO][7]],[PaintVO][7]],[PaintVO][7]],[PaintVO][7]]]<br>返回一组数组，只有一个元素的则显示为大图，多个元素的则显示为小图<br><br>`result_type=2`results:[[PaintVO][7]]
/paint/new<br>**GET**|paint_id` 参照画的ID，判断是否有比它更新的画`|`暂未实现`
/paint/praise<br>**POST**|***paint** 画的ID<br>***status** true 赞 false 取消
/paint/praise/get<br>**GET**|***paint** 画的ID，获取是否赞过某个画|status:true 赞过 status:false 没赞过 
/paint/praise/list<br>**POST**|***paint** 画的ID<br>***page** 请求页码 | results:[PraiseVO][8]
/paint/count<br>**GET**|***paint** 查看的画的ID <br> ***type** 1 统计查看次数 2 统计播放次数
/paint/get<br>**GET**|***paint** 查看的画的ID|resutls:PaintVO 所有详细数据，包括作者信息

##Message
URI|Request|[ResultVO][6]
---|---|---
/message/list<br>**GET**| ***page** 页码| [[MessageVO]][9]
/message/count<br>**GET**| | 未读消息数

#Model
##ResultVO

property|	type|	description|	remark
---|---|---|---
status	|Boolean	|true:接口请求成功<br>false:接口请求失败	
results|	Object|	任意数据对象，出错后返回错误原因	
errorResult|	String|	出错时将结果对象转换为字符串	

##UserVO


property|	type|	description|	remark
---|---|---|---
username	|String|	用户名|	唯一，可做登录
password|	String|	密码	
email|	String|	邮箱|	唯一，可做登录及找回密码
portrait|	String|	头像|	157*157：个人中心<br>100*100：关注列表<br>50*50：画作详情作者
nickname|	String|	昵称|	不唯一，画作作者
come_from|	String|	用户来源|	画板默认DrawingBoard


##PaintVO


property|	type|	description|	remark
---|---|---|---
author|	UserVO|	画作者，可以获取到用户昵称和id	
cover|	String|	封面地址|	634*477：显示于作品详情页<br>441*332：显示于画廊列表大图<br>300*226：显示于用户个人中心<br>213*160：显示于画廊列表小图<br>58*43：显示于消息列表
data|	String|	绘图数据文件地址	
audio|	String|	音频文件地址	
theme|String|关联主题路径
views|	Number|	浏览数	
plays|	Number|	播放数	
comments|	Number|	评论数	
favorites|	Number|	收藏数	
agrees|	Number|	赞数	
shares	|Number|	分享数	
created_at |Date|创建日期

##RelationshipVO
property|	type|	description|	remark
---|---|---|---
friend|UserVO|用户对象|{nickname:昵称,portrait:头像,_id:用户id}
followed|Boolean|是否是关注我的
following|Boolean|是否是我关注的

##PraiseVO
property|	type|	description|	remark
---|---|---|---
user | UserVO | 用户对象 | {nickname:昵称,portrait:头像,_id:用户id}
created_at | Date |赞的时间

##MessageVO
property|	type|	description|	remark
---|---|---|---
type | Number | 消息类型 | 1 别人关注了我 2 别人赞了我的画
creator|[UserVO][3]|触发消息的人
paint|[PaintVO][7]|关联的画
readed|Boolean|是否已读
created_at | Date |消息时间


#Usage
```actionscript
ServiceBase.HOST = 'http://db.pamakids.com';

getSB('/user/signup').call(function(result:ResultVO):void{
            var user:UserVO = CloneUtil.convert(result.results, UserVO); //自动转换Object对象为VO对象
            ServiceBase.id = user._id; //用户登录后设置用户ID，以便访问某些需要权限的接口时检测用户是否已登录
            },{username:'admin2', password:'ads', come_from:'DrawingBoard', email:'test'});

private function getSB(uri:String):ServiceBase
{
    var sb:ServiceBase = new ServiceBase(uri, 'POST');
    return sb;
}           
```
  [1]: #resultvo
  [2]: #uservo
  [3]: #uservo
  [4]: #uservo
  [5]: #resultvo
  [6]: #resultvo
  [7]: #paintvo
  [8]: #praisevo
  [9]: #messagevo