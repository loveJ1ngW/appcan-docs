#uexJPush插件接口文档
封装了极光推送的相关功能：您可以主动、及时地向您的用户发起交互，向其发送聊天消息、日程提醒、活动预告、进度提示、动态更新等，精准的目标用户和有价值的推送内容可以提升用户忠诚度，提高留存率与收入。
	
## 方法
### init 初始化（已废弃，现在插件会自动初始化）
### stopPush 停止推送服务
### resumePush 恢复推送服务
### setAlias 设置别名
### setTags 设置标签
### setAliasAndTags 同时设置别名和标签
### getRegistrationID 取得App对应的registrationID
### clearAllNotifications 清除所有通知
### clearNotificationById 根据Id清除某条通知
### getConnectionState 获取推送连接状态
### addLocalNotification 添加一个本地通知
### removeLocalNotification 移除一个本地通知
### clearLocalNotifications 移除所有本地通知

## 回调方法
### cbSetAlias 设置别名的回调方法
### cbSetTags 设置标签的回调方法
### cbSetAliasAndTags 同时设置别名和标签的回调方法
### cbGetRegistrationID 取得程序对应的registrationID的回调方法
### cbGetConnectionState 获取推送连接状态的回调方法

## 监听方法
### onReceiveNotification 收到通知的监听方法
### onReceiveMessage 收到自定义消息的监听方法
### onReceiveNotificationOpen 用户点击通知打开APP的监听方法
### onReceiveConnectionChange 连接状态的监听方法
### onReceiveRegistration App注册成功的监听方法


***
##方法
***
### init（已废弃）
初始化

```
uexJPush.init()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
uexJPush.init();
```
### stopPush
停止推送服务

```
uexJPush.stopPush()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
```
### 版本支持
```
Android 3.0.0+
```
###示例
```
uexJPush.stopPush();
```
### resumePush
恢复推送服务

```
uexJPush.resumePush()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
```
### 版本支持
```
Android 3.0.0+
```
###示例
```
uexJPush.resumePush();
```

### setAlias
设置别名

```
uexJPush.setAlias(json)
```
### 参数

```
var json={
	alias:,//String 设置的别名
};
说明：传""(空字符串)表示取消之前的设置。
	每次调用设置有效的别名，覆盖之前的设置。
	有效的别名组成：字母（区分大小写）、数字、下划线、汉字。
	限制：alias 命名长度限制为 40 字节。（判断长度需采用UTF-8编码）
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
var params = {
	alias:"alias22"
};
var data = JSON.stringify(params);
uexJPush.setAlias(data);
```
### setTags
设置标签

```
uexJPush.setTags(json)
```
### 参数

```
var json={
	tags:,//Set<String>  设置的标签
};
说明：空数组或列表表示取消之前的设置。
	每次调用设置有效的标签，覆盖之前的设置。
	有效的标签组成：字母（区分大小写）、数字、下划线、汉字。
	限制：每个tag命名长度限制为 40 字节，最多支持设置 100 个 tag，但总长度不得超过1K字节。（判断长度需采用UTF-8编码）
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
var tags=new Array("tag1","tag2","tag3");
var params = {
	tags:tags
};
var data = JSON.stringify(params);
uexJPush.setTags(data);
```

### setAliasAndTags
同时设置别名与标签

```
uexJPush.setAliasAndTags(json)
```
### 参数

```
var json={
	alias:,//string 设置的别名
	tags:,//Set<String> 设置的标签
	}
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
var tags=new Array("tag4","tag5","tag6");
var params = {
	alias:"alias66",
	tags:tags
};
var data = JSON.stringify(params);
uexJPush.setAliasAndTags(data);
```


### getRegistrationID
取得应用程序对应的 RegistrationID

```
uexJPush.getRegistrationID()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
uexJPush.getRegistrationID();
```

### clearAllNotifications
清除所有通知

```
uexJPush.clearAllNotifications()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
```
### 版本支持
```
Android 3.0.0+
```
###示例
```
uexJPush.clearAllNotifications();
```

### clearNotificationById
根据Id清除某条通知

```
uexJPush.clearNotificationById(json)
```
### 参数

```
var json={
	notificationId:,//int 通知Id
}
```
### 平台支持
```
Android 2.2+

```
### 版本支持
```
Android 3.0.0+

```
###示例
```
var params = {
	notificationId:123456789
};
var data = JSON.stringify(params);
uexJPush.clearNotificationById(data);

```
### getConnectionState
获取推送连接状态

```
uexJPush.getConnectionState()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
uexJPush.getConnectionState();
```

### addLocalNotification
添加一个本地通知

```
uexJPush.addLocalNotification(json)
```
### 参数

```
var json={
	builderId:,//long 设置本地通知样式(仅Android有效)
	title:,//本地通知的title
	content:,//设置本地通知的content
	extras:,//额外的数据信息extras为json字符串
	notificationId:,//int 设置本地通知的ID
	broadCastTime:,//long 设置本地通知延迟触发时间，毫秒为单位，如设置10000为延迟10秒添加通知
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
var params = {
	builderId:0,
	title:"这是title",
	content:"这是内容",
	extras:{"key":"value"},
	notificationId:3,
	broadCastTime:10000
};
var data = JSON.stringify(params);
uexJPush.addLocalNotification(data);
```

### removeLocalNotification
移除一个本地通知

```
uexJPush.removeLocalNotification(json)
```
### 参数

```
var json={
	notificationId://int 通知id
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
var notificationId=3;
var params = {
	notificationId:notificationId
};
var data = JSON.stringify(params);
uexJPush.removeLocalNotification(data);
```

### clearLocalNotifications
移除所有的通知

```
uexJPush.clearLocalNotifications()
```
### 参数

```
无
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
uexJPush.clearLocalNotifications();
```
 
 
 ##回调方法
 ***
### cbSetAlias
设置别名的回调方法

```
uexJPush.cbSetAlias(json)
```
### 参数

```
var json={
	result://0-成功,其他-失败 具体失败代码解释见文末附录
	alias://设置的别名
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.cbSetAlias=function(data){
		alert(data);
	}

	...(其他回调或监听)
}

```
### cbSetTags
设置别名的回调方法

```
uexJPush.cbSetTags(json)
```
### 参数

```
var json={
	result://0-成功,其他-失败 具体失败代码解释见文末附录
	tags://设置的标签
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.cbSetTags=function(data){
		alert(data);
	}

	...(其他回调或监听)
}

```
### cbSetSetAliasAndTags
同时设置别名和标签的回调方法

```
uexJPush.SetAliasAndTags(json)
```
### 参数

```
var json={
	result://0-成功,其他-失败 具体失败代码解释见文末附录
	alias://设置的别名
	tags://设置的标签
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.cbSetAlias=function(data){
		alert(data);
	}

	...(其他回调或监听)
}

```
### cbGetRegistrationID
取得应用程序对应的RegistrationID的回调方法

```
uexJPush.cbGetRegistrationID(json)
```
### 参数

```
var json={
	registrationID://String 应用程序对应的RegistrationID
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.cbGetRegistrationID=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```

### cbGetConnectionState
获取连接状态回调

```
uexJPush.cbGetConnectionState(json)
```
### 参数

```
var json={
	result://0-已连接上，1-未连接
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.cbGetConnectionState=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```
###监听方法
***

### onReceiveMessage
收到了自定义消息

```
uexJPush.onReceiveMessage(json)
```
### 参数

```
var json={
	message:,//String 对应 Portal 推送消息界面上的"自定义消息内容”字段
	extras:,// 对应 Portal 推送消息界面上的“可选设置”里的附加字段	
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.onReceiveMessage=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```

### onReceiveNotification
收到了通知

```
uexJPush.onReceiveNotification(json)
```
### 参数

```
var json={
	content:,//对应 Portal 推送通知界面上的“通知内容”字段。
	extras:,//对应 Portal 推送消息界面上的“可选设置”里的附加字段。	
	notificationId:,//(仅Android) 消息Id，用于清除通知  
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.onReceiveNotification=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```

### onReceiveNotificationOpen
用户点击通知打开了App

```
uexJPush.onReceiveNotificationOpen(json)
```
### 参数

```
var param={
	content:,//对应 Portal 推送通知界面上的“通知内容”字段。
	extras:,//对应 Portal 推送消息界面上的“可选设置”里的附加字段。
	notificationId:,//(仅Android)消息Id，可以用于清除通知

};
```
### 平台支持
```
Android 2.2+
iOS 6.0+

```
### 版本支持
```
Android 3.0.2+
iOS 3.0.1+

```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.onReceiveNotificationOpen=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```

### onReceiveConnectionChange
连接状态变化

```
uexJPush.onReceiveConnectionChange(json)
```
### 参数

```
var json={
	connect:,//0-已连接上，1-未连接
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.onReceiveConnectionChange=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```
### onReceiveRegistration
应用程序注册监听

```
uexJPush.onReceiveRegistration(json)
```
### 参数

```
var json={
	title:,//RegistrationID
};
```
### 平台支持
```
Android 2.2+
iOS 6.0+
```
### 版本支持
```
Android 3.0.0+
iOS 3.0.0+
```
###示例
```
window.uexOnload=function(type){
	
	uexJPush.onReceiveRegistration=function(data){
		alert(data);
	}

	...(其他回调或监听)
}
```
##附录

###别名/标签 错误代码解释
|result|描述|详细解释|
|------|---|------|
|6001|无效的设置，tag/alias 不应参数都为 null	
|6002|	设置超时	|建议重试
|6003|	alias 字符串不合法	|有效的别名、标签组成：字母（区分大小写）、数字、下划线、汉字。
|6004|	alias超长。最多 40个字节	|中文 UTF-8 是 3 个字节
|6005|	某一个 tag 字符串不合法	|有效的别名、标签组成：字母（区分大小写）、数字、下划线、汉字。
|6006|	某一个 tag 超长。一个 tag 最多 40个字节	|中文 UTF-8 是 3 个字节
|6007|	tags 数量超出限制。最多 100个	|这是一台设备的限制。一个应用全局的标签数量无限制。
|6008|	tag/alias 超出总长度限制	|总长度最多 1K 字节
|6011|	10s内设置tag或alias大于10次|	短时间内操作过于频繁

### 通知/自定义消息/本地通知的接收情况
|操作系统|通知|自定义消息|本地通知|
|------|---|------|------|
|Andriod|前台、后台 均能接收|前台、后台 均能接收|前台、后台 均能接收|	
|iOS|	前台、后台、进程关闭状态 均能接收	|仅前台|前台、后台 均能接收|
 
 
### Android插件配置说明

插件需要在`AndroidManifest.xml`中查找替换所有的`org.zywx.wbpalmstar.widgetone.uexJPushDemo`改为自己的包名。

并将`<meta-data android:name="JPUSH_APPKEY" android:value=""/>`中的value替换为自己在极光推送申请的appkey


#### iOS插件配置说明
**本插件需要下载插件包配置plist文件后作为自定义插件上传才能正常使用。**

所需配置的文件为插件包解压缩后的文件夹中的`PushConfig.plist`。
键值说明：

```
CHANNEL
指明应用程序包的下载渠道,为方便分渠道统计。根据你的需求自行定义即可。

APP_KEY
在管理Portal上创建应用时自动生成的(AppKey)用以标识该应用。请确保应用内配置的 AppKey 与在 Portal 上创建应用时生成的 AppKey 一致,AppKey 可以在应用详情中查询。


APS_FOR_PRODUCTION
表示应用是否采用生产证书发布( Ad_Hoc 或 APP Store ),0 (默认值)表示采用的是开发者证书,1 表示采用生产证书发布应用。请注意此处配置与 Web Portal 应用环境设置匹配。

```



