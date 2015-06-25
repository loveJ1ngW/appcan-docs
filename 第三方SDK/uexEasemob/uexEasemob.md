<html>
<head>
<meta charset="utf-8">
<title>uexEasemob插件接口文档</title>
</head>
<body>
<div class="md-section-divider"></div>

<div class="md-section-divider"></div>

<h1 id="uexeasemob插件接口文档" data-anchor-id="nu5l">uexEasemob插件接口文档</h1>

<div class="md-section-divider"></div>

<h2 id="简介" data-anchor-id="wdpj">简介：</h2>

<hr>

<p data-anchor-id="6194">本插件是基于环信API封装的AppCan平台的插件模块，用户可以使用本插件实现基本的即时通讯功能，包括——</p>

<p data-anchor-id="q4bj">单聊功能：支持发送语音，图片，表情，文字，位置，名片，附件；</p>

<p data-anchor-id="poue">群聊功能：支持500人到2000人大群，拥有完善的群组权限管理；</p>

<p data-anchor-id="gl0t">实时语音 ：基于IP网络的点对点实时语音，适应低带宽要求；</p>

<div class="md-section-divider"></div>

<h2 id="changelog" data-anchor-id="vzmh">changelog</h2>

<hr>

<p data-anchor-id="2j1t">2015-04-17 </p>

<ul data-anchor-id="vd0d">
<li>初稿</li>
</ul>

<p data-anchor-id="3h3p">2015-04-20  </p>

<ul data-anchor-id="b151">
<li>新增[2.12][2.13]方法;</li>
<li>修改了[2.1]的回调值的结构;</li>
<li>统一了Android和iOS返回的json对象的结构，对附录做了大量修订。</li>
</ul>

<p data-anchor-id="485n">2015-04-28 </p>

<ul data-anchor-id="1nwv">
<li>新增方法[3.15]获取聊天对象信息及其回调[3.16];</li>
<li>[4.6][5.14]改用异步方法获得回调。</li>
</ul>

<p data-anchor-id="omzp">2015-05-04 </p>

<ul data-anchor-id="4q96">
<li>新增方法[1.12]设置是否自动登录;</li>
<li>现在iOS也支持回调 [1.10]onConnected 了。</li>
</ul>

<p data-anchor-id="jrk6">2015-05-05</p>

<ul data-anchor-id="ixcv">
<li>更新环信iOS SDK版本至V2.1.6(2015-04-30版)，部分代码做了优化以支持此新版本;</li>
<li>现在所有的回调函数都会返回给进行 [1.1]初始化 操作的那个网页了。</li>
<li>[1.9]现在也会返回 是否开启自动登录 的信息了。</li>
</ul>

<p data-anchor-id="w63f">2015-05-06</p>

<ul data-anchor-id="v4tk">
<li>删去方法 [1.12]设置是否自动登录 ，改为在 [1.1]初始化 中添加相关参数</li>
</ul>

<p data-anchor-id="87ka">2015-5-25</p>

<ul data-anchor-id="ynjo">
<li>iOS插件版本更新至3.0.8</li>
<li>新增方法[2.14]sendVedio 发送视频消息；</li>
<li>EMMessage回调中，添加length 长度（单位：秒，仅语音、视频消息）；</li>
<li>EMMessage回调中，添加ext 扩展属性；发送消息的各个API也添加此项作为可选参数；（扩展属性为一个自定义的字典，用以携带开发者可能需要的其他参数）</li>
<li>新增方法[2.15]sendHasReadResponseForMessage 发送已读回执;(对方会触发回调[2.3]，插件不再自动发送此回执)</li>
<li>方法[2.12]根据消息id获取消息记录及其回调[2.13]也支持iOS了</li>
</ul>

<p data-anchor-id="bn5s">2015-6-18</p>

<ul data-anchor-id="09ql">
<li>iOS插件版本更新至3.0.9，用以支持新版SDK （iOS V2.1.7）</li>
<li>Android插件版本更新至3.0.6 用以支持新版SDK（AndroidV2.1.9） </li>
<li>方法[5.16]getAllPublicGroupsFromServer添加的参数，变得更加实用了（详情见接口说明）</li>
<li>新增方法[3.17]getTotalUnreadMsgCount() 获取总计未读消息数 及其回调[3.18]</li>
<li>开放Apns离线推送相关接口(仅限iOS)</li>
<li>所有参数中的"isGroup"即将废弃，改用"chatType"(详见附录)</li>
</ul>

<p data-anchor-id="jyfc"><div class="toc">

<li><a href="#api">API</a><ul>
<li><a href="#1initialization">[1]Initialization</a><ul>

<li><a href="#11-initeasemobparam-初始化">[1.1] initEasemob(param) //初始化</a></li>
<li><a href="#12loginparam-登陆">[1.2]login(param) //登陆</a></li>
<li><a href="#13cbloginparam登陆回调">[1.3]cbLogin(param)//登陆回调</a></li>
<li><a href="#14logout-退出登录">[1.4]logout() //退出登录</a></li>
<li><a href="#15registeruserparam注册">[1.5]registerUser(param)//注册</a></li>
<li><a href="#16cbregisteruserparam注册回调">[1.6]cbRegisterUser(param)//注册回调</a></li>
<li><a href="#17updatecurrentusernicknameparam-更新当前用户的昵称">[1.7]updateCurrentUserNickname(param) // 更新当前用户的昵称</a></li>
<li><a href="#18getlogininfo获取当前登陆信息仅ios可用">[1.8]getLoginInfo()//获取当前登陆信息(仅iOS可用)</a></li>
<li><a href="#19cbgetlogininfoparam获取当前登陆信息的回调仅ios">[1.9]cbGetLoginInfo(param)//获取当前登陆信息的回调（仅iOS）</a></li>
<li><a href="#110onconnected已连接上">[1.10]onConnected();//已连接上</a></li>
<li><a href="#111ondisconnectedparam链接断开">[1.11]onDisconnected(param)//链接断开</a></li>

</ul>
</li>
<li><a href="#2message">[2]Message</a><ul>

<li><a href="#21onnewmessageparam收到新消息监听">[2.1]onNewMessage（param）//收到新消息监听</a></li>
<li><a href="#22oncmdmessagereceiveparam透传消息监听">[2.2]onCmdMessageReceive(param)//透传消息监听</a></li>
<li><a href="#23onackmessageparam消息已读监听">[2.3]onAckMessage(param)//消息已读监听</a></li>
<li><a href="#24ondeliverymessageparam消息送达监听">[2.4]onDeliveryMessage(param)//消息送达监听</a></li>
<li><a href="#25sendtextparam发送文本消息及表情">[2.5]sendText(param)//发送文本消息及表情</a></li>
<li><a href="#26sendvoiceparam发送语音">[2.6]sendVoice(param)//发送语音</a></li>
<li><a href="#27sendpictureparam发送图片">[2.7]sendPicture(param)//发送图片</a></li>
<li><a href="#28sendlocationmsgparam发送地理位置信息">[2.8]sendLocationMsg(param)//发送地理位置信息</a></li>
<li><a href="#29sendfileparam发送文件">[2.9]sendFile(param)//发送文件</a></li>
<li><a href="#210sendcmdmessageparam发送透传消息">[2.10]sendCmdMessage(param)//发送透传消息</a></li>
<li><a href="#211setnotifybysoundandvibrateparam消息提醒相关配置">[2.11]setNotifyBySoundAndVibrate(param)//消息提醒相关配置</a></li>
<li><a href="#212getmessagebyidparam根据id获取消息记录">[2.12]getMessageById(param)//根据id获取消息记录</a></li>
<li><a href="#213cbgetmessagebyidparam得到一条消息记录">[2.13]cbGetMessageById(param)//得到一条消息记录</a></li>
<li><a href="#214sendvideoparam发送视频">[2.14]sendVideo(param)//发送视频</a></li>
<li><a href="#215sendhasreadresponseformessageparam发送消息已读回执">[2.15]sendHasReadResponseForMessage(param)//发送消息已读回执</a></li>

</ul>
</li>
<li><a href="#3conversation">[3]Conversation</a><ul>

<li><a href="#31getconversationbynameparam根据用户名获取conversation对象">[3.1]getConversationByName(param)//根据用户名获取conversation对象</a></li>
<li><a href="#32cbgetconversationbynameparam回调">[3.2]cbGetConversationByName(param)//回调</a></li>
<li><a href="#33getmessagehistoryparam获取聊天记录">[3.3]getMessageHistory(param)//获取聊天记录</a></li>
<li><a href="#34cbgetmessagehistoryparam获取聊天记录回调">[3.4]cbGetMessageHistory(param)//获取聊天记录回调</a></li>
<li><a href="#35getunreadmsgcountparam获取未读消息数量">[3.5]getUnreadMsgCount(param)//获取未读消息数量</a></li>
<li><a href="#36cbgetunreadmsgcountparam获取未读消息数量回调">[3.6]cbGetUnReadMsgCount(param)//获取未读消息数量回调</a></li>
<li><a href="#37resetunreadmsgcountparam指定会话未读消息数清零">[3.7]resetUnreadMsgCount(param)//指定会话未读消息数清零</a></li>
<li><a href="#38resetallunreadmsgcount所有未读消息数清零仅android可用">[3.8]resetAllUnreadMsgCount();//所有未读消息数清零（仅Android可用）</a></li>
<li><a href="#39getmsgcountparam获取消息总数仅android可用">[3.9]getMsgCount(param)//获取消息总数（仅Android可用）</a></li>
<li><a href="#310cbgetmsgcountparam获取消息总数回调仅android可用">[3.10]cbGetMsgCount(param)//获取消息总数回调（仅Android可用）</a></li>
<li><a href="#311clearconversationparam清空会话聊天记录仅android可用">[3.11]clearConversation(param)//清空会话聊天记录（仅Android可用）</a></li>
<li><a href="#312deleteconversationparam删除和某个user的整个的聊天记录包括本地">[3.12]deleteConversation(param)//删除和某个user的整个的聊天记录(包括本地)</a></li>
<li><a href="#313removemessageparam删除当前会话的某条聊天记录">[3.13]removeMessage(param)//删除当前会话的某条聊天记录</a></li>
<li><a href="#314deleteallconversation删除所有会话记录包括本地">[3.14]deleteAllConversation();//删除所有会话记录(包括本地)</a></li>
<li><a href="#315getchatterinfo获取聊天对象信息">[3.15]getChatterInfo();//获取聊天对象信息</a></li>
<li><a href="#316cbgetchatterinfoparam获取聊天对象信息回调">[3.16]cbGetChatterInfo(param);//获取聊天对象信息回调</a></li>
<li><a href="#317gettotalunreadmsgcount获取总计未读消息数">[3.17]getTotalUnreadMsgCount();//获取总计未读消息数</a></li>
<li><a href="#317cbgettotalunreadmsgcountparam获取总计未读消息数回调">[3.18]cbGetTotalUnreadMsgCount(param);//获取总计未读消息数回调</a></li>

</ul>
</li>
<li><a href="#4friend">[4]Friend</a><ul>

<li><a href="#41oncontactaddedparam新增联系人监听仅android">[4.1]onContactAdded(param)//新增联系人监听（仅Android）</a></li>
<li><a href="#42oncontactdeletedparam删除联系人监听仅android">[4.2]onContactDeleted(param)//删除联系人监听（仅Android）</a></li>
<li><a href="#43oncontactinvitedparam接到好友申请">[4.3]onContactInvited(param)//接到好友申请</a></li>
<li><a href="#44oncontactagreedparam好友请求被同意">[4.4]onContactAgreed(param)//好友请求被同意</a></li>
<li><a href="#45oncontactrefusedparam好友请求被拒绝">[4.5]onContactRefused(param)//好友请求被拒绝</a></li>
<li><a href="#46getcontactusernames获取好友列表">[4.6]getContactUserNames();//获取好友列表</a></li>
<li><a href="#47cbgetcontactusernamesparam获取好友列表回调">[4.7]cbGetContactUserNames(param)//获取好友列表回调</a></li>
<li><a href="#48addcontactparam添加好友">[4.8]addContact(param)//添加好友</a></li>
<li><a href="#49deletecontactparam删除好友">[4.9]deleteContact(param)//删除好友</a></li>
<li><a href="#410acceptinvitationparam同意username的好友请求">[4.10]acceptInvitation(param)//同意username的好友请求</a></li>
<li><a href="#411refuseinvitationparam拒绝username的好友请求">[4.11]refuseInvitation(param)//拒绝username的好友请求</a></li>
<li><a href="#412getblacklistusernames获取黑名单列表">[4.12]getBlackListUsernames();//获取黑名单列表</a></li>
<li><a href="#413cbgetblacklistusernamesparam获取黑名单列表回调">[4.13]cbGetBlackListUsernames(param)//获取黑名单列表回调</a></li>
<li><a href="#414addusertoblacklistparam把用户加入到黑名单">[4.14]addUserToBlackList(param)//把用户加入到黑名单</a></li>
<li><a href="#415deleteuserfromblacklistparam把用户从黑名单中移除">[4.15]deleteUserFromBlackList(param)//把用户从黑名单中移除</a></li>

</ul>
</li>
<li><a href="#5group">[5]Group</a><ul>

<li><a href="#51oninvitationdeclinedparam群聊邀请被拒绝">[5.1]onInvitationDeclined(param)//群聊邀请被拒绝</a></li>
<li><a href="#52onuserremovedparam当前用户被管理员移除出群聊">[5.2]onUserRemoved(param)//当前用户被管理员移除出群聊</a></li>
<li><a href="#53ongroupdestroyparam群聊被创建者解散">[5.3]onGroupDestroy(param)//群聊被创建者解散</a></li>
<li><a href="#54onapplicationreceivedparam用户申请加入群聊收到加群申请">[5.4]onApplicationReceived(param)//用户申请加入群聊，收到加群申请</a></li>
<li><a href="#55onapplicationacceptparam-加群申请被同意">[5.5]onApplicationAccept(param)// // 加群申请被同意</a></li>
<li><a href="#56onapplicationdeclinedparam加群申请被拒绝">[5.6]onApplicationDeclined(param)//加群申请被拒绝</a></li>
<li><a href="#57createprivategroupparam创建私有群">[5.7]createPrivateGroup(param)//创建私有群</a></li>
<li><a href="#58createpublicgroupparam创建公开群">[5.8]createPublicGroup(param)//创建公开群</a></li>
<li><a href="#59adduserstogroupparam群聊加人">[5.9]addUsersToGroup(param)//群聊加人</a></li>
<li><a href="#510removeuserfromgroupparam群聊减人">[5.10]removeUserFromGroup(param)//群聊减人</a></li>
<li><a href="#511joingroupparam加入某个群聊只能用于加入公开群">[5.11]joinGroup(param)//加入某个群聊，只能用于加入公开群</a></li>
<li><a href="#512exitfromgroupparam退出群聊">[5.12]exitFromGroup(param)//退出群聊</a></li>
<li><a href="#513exitanddeletegroupparam解散群聊">[5.13]exitAndDeleteGroup(param)//解散群聊</a></li>
<li><a href="#514getgroupsfromserverparam从服务器获取自己加入的和创建的群聊列表">[5.14]getGroupsFromServer(param)//从服务器获取自己加入的和创建的群聊列表</a></li>
<li><a href="#515cbgetgroupsfromserverparam从服务器获取自己加入的和创建的群聊列表回调">[5.15]cbGetGroupsFromServer(param)//从服务器获取自己加入的和创建的群聊列表回调</a></li>
<li><a href="#516getallpublicgroupsfromserverparam获取所有公开群列表">[5.16]getAllPublicGroupsFromServer(param);//获取所有公开群列表</a></li>
<li><a href="#517cbgetallpublicgroupsfromserverparam获取所有公开群列表回调">[5.17]cbGetAllPublicGroupsFromServer(param)//获取所有公开群列表回调</a></li>
<li><a href="#518getgroupparam获取单个群聊信息">[5.18]getGroup(param)//获取单个群聊信息</a></li>
<li><a href="#519cbgetgroupparam获取单个群聊信息回调">[5.19]cbGetGroup(param)//获取单个群聊信息回调</a></li>
<li><a href="#520blockgroupmessageparam屏蔽群消息">[5.20]blockGroupMessage(param)//屏蔽群消息</a></li>
<li><a href="#521unblockgroupmessageparam解除屏蔽群">[5.21]unblockGroupMessage(param)//解除屏蔽群</a></li>
<li><a href="#522changegroupnameparam修改群组名称">[5.22]changeGroupName(param)//修改群组名称</a></li>
<li><a href="#523setreceivenotnoifygroupparam群聊不提醒只显示数目仅android可用">[5.23]setReceiveNotNoifyGroup(param)//群聊不提醒只显示数目（仅Android可用）</a></li>
<li><a href="#524blockuserparam将群成员拉入群组的黑名单仅android可用">[5.24]blockUser(param)//将群成员拉入群组的黑名单（仅Android可用）</a></li>
<li><a href="#525unblockuserparam将拉入黑名单的群成员移除仅android可用">[5.25]unblockUser(param)//将拉入黑名单的群成员移除（仅Android可用）</a></li>
<li><a href="#526getblockedusersparam获取群组的黑名单用户列表仅android可用">[5.26]getBlockedUsers(param)//获取群组的黑名单用户列表（仅Android可用）</a></li>
<li><a href="#527cbgetblockedusersparam获取群组的黑名单用户列表回调仅android">[5.27]cbGetBlockedUsers(param)//获取群组的黑名单用户列表回调（仅Android）</a></li>
<li><a href="#528ongroupupdateinfoparam群组信息更新的监听仅ios">[5.28]onGroupUpdateInfo(param)//群组信息更新的监听（仅iOS）</a></li>

</ul>
</li>
<li><a href="#6call">[6]Call</a><ul>

<li><a href="#61oncallreceiveparam-实时语音监听">[6.1]onCallReceive(param)// 实时语音监听</a></li>
<li><a href="#62oncallstatechangedparam通话状态监听">[6.2]onCallStateChanged(param)//通话状态监听</a></li>
<li><a href="#63makevoicecallparam拨打语音通话">[6.3]makeVoiceCall(param)//拨打语音通话</a></li>
<li><a href="#64answercall接听通话">[6.4]answerCall();//接听通话</a></li>
<li><a href="#65rejectcall拒绝接听">[6.5]rejectCall();//拒绝接听</a></li>
<li><a href="#66endcall挂断通话">[6.6]endCall();//挂断通话</a></li>
</ul>
</li>
<li><a href="#7apns以下方法全部仅限ios">[7]Apns（以下方法全部仅限iOS）</a><ul>

<li><a href="#71registerremotenotification注册apns推送">[7.1]registerRemoteNotification();//注册Apns推送</a></li>
<li><a href="#72-cbregisterremotenotificationparam回调">[7.2] cbRegisterRemoteNotification(param);//注册Apns推送回调</a></li>
<li><a href="#73onapnslaunchparam">[7.3]onApnsLaunch(param);//应用被Apns调起的监听</a></li>
<li><a href="#74updatepushoptionsparam设置apns全局属性">[7.4]updatePushOptions(param);//设置apns全局属性</a></li>
<li><a href="#75cbupdatepushoptionsparam设置apns全局属性回调">[7.5]cbUpdatePushOptions(param);//设置apns全局属性回调</a></li>
<li><a href="#76ignoregrouppushnotificationparam设置指定群组是否接收">[7.6]ignoreGroupPushNotification(param)://设置指定群组是否接收Apns</a></li>
<li><a href="#77cbignoregrouppushnotificationparam回调">[7.7]cbIgnoreGroupPushNotification(param)://设置指定群组是否接收Apns回调</a></li>

</ul>
</li>
</ul>
</li>
<li><a href="#附录">附录</a><ul>

<li><a href="#emmessage-json字符串返回值结构">EMMessage json字符串返回值结构</a><ul>
<li><a href="#普通文本消息">普通文本消息</a></li>
<li><a href="#透传消息">透传消息</a></li>
<li><a href="#位置消息">位置消息</a></li>
<li><a href="#视频语音图片文件消息">视频/语音/图片/文件消息</a></li>
</ul>
</li>
<li><a href="#emconversation-json字符串返回值结构">EMConversation json字符串返回值结构</a></li>
<li><a href="#emgroup-json字符串返回值结构">EMGroup json字符串返回值结构</a></li>
<li><a href="#isgroup参数废弃-改用chattype的相关说明">"isGroup"参数废弃 改用“chatType”的相关说明</a></li>

</ul>
</li>
</ul>
</li>
</ul>
</div>
</p>

<div class="md-section-divider"></div>

<h2 id="api" data-anchor-id="kh5l">API</h2>

<div class="md-section-divider"></div>

<h3 id="1initialization" data-anchor-id="f5cl">[1]Initialization</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="11-initeasemobparam-初始化" data-anchor-id="edgf">[1.1] initEasemob(param) //初始化</h5>

<p data-anchor-id="08ho">var param{</p>

<pre data-anchor-id="cv78"><code>appKey:,//区别app的标识（仅iOS）     
apnsCertName:,//iOS中推送证书名称（仅iOS）
isAutoLoginEnabled:,//可选参数 是否开启自动登录功能 1-开启 2-关闭
</code></pre>

<p data-anchor-id="tjsk">}</p>

<pre data-anchor-id="nu1w"><code>注：Android中 初始化需要在AndroidManifest.xml中配置；
   自动登录功能Android SDK 默认开启，iOS SDK默认关闭。
</code></pre>

<div class="md-section-divider"></div>

<h5 id="12loginparam-登陆" data-anchor-id="hyoq">[1.2]login(param) //登陆</h5>

<p data-anchor-id="gaxn">var param = {</p>

<pre data-anchor-id="rid3"><code>username:,//用户名
password:,//密码
</code></pre>

<p data-anchor-id="yaie">};</p>

<div class="md-section-divider"></div>

<h5 id="13cbloginparam登陆回调" data-anchor-id="eo8g">[1.3]cbLogin(param)//登陆回调</h5>

<p data-anchor-id="6jx9">var param = {</p>

<pre data-anchor-id="a3y5"><code>result:,//1-成功，2-失败
msg:,//提示信息
</code></pre>

<p data-anchor-id="t2h8">};</p>

<div class="md-section-divider"></div>

<h5 id="14logout-退出登录" data-anchor-id="4u3u">[1.4]logout() //退出登录</h5>

<div class="md-section-divider"></div>

<h5 id="15registeruserparam注册" data-anchor-id="i4dz">[1.5]registerUser(param)//注册</h5>

<p data-anchor-id="0f6b">var param = {</p>

<pre data-anchor-id="xv6l"><code>username:,//用户名
password:,//密码
</code></pre>

<p data-anchor-id="zljy">};</p>

<div class="md-section-divider"></div>

<h5 id="16cbregisteruserparam注册回调" data-anchor-id="zky5">[1.6]cbRegisterUser(param)//注册回调</h5>

<p data-anchor-id="liy7">var param = {</p>

<pre data-anchor-id="j6l0"><code>result:,//1-成功，2-失败
msg:,//提示信息
</code></pre>

<p data-anchor-id="ehfe">};</p>

<div class="md-section-divider"></div>

<h5 id="17updatecurrentusernicknameparam-更新当前用户的昵称" data-anchor-id="rg7d">[1.7]updateCurrentUserNickname(param) // 更新当前用户的昵称</h5>

<p data-anchor-id="mged">var param = {   </p>

<pre data-anchor-id="1n2p"><code>nickname:,
</code></pre>

<p data-anchor-id="bnab">}</p>

<pre data-anchor-id="gxxd"><code>注：此方法主要为了在苹果推送时能够推送昵称(nickname)而不是userid,一般可以在登陆成功后从自己服务器获取到个人信息，然后拿到nick更新到环信服务器。并且，在个人信息中如果更改个人的昵称，也要把环信服务器更新下nickname 防止显示差异。
</code></pre>

<div class="md-section-divider"></div>

<h5 id="18getlogininfo获取当前登陆信息仅ios可用" data-anchor-id="c85k">[1.8]getLoginInfo()//获取当前登陆信息(仅iOS可用)</h5>

<div class="md-section-divider"></div>

<h5 id="19cbgetlogininfoparam获取当前登陆信息的回调仅ios" data-anchor-id="nwm1">[1.9]cbGetLoginInfo(param)//获取当前登陆信息的回调（仅iOS）</h5>

<p data-anchor-id="7a48">var param={</p>

<pre data-anchor-id="4vuo"><code>userInfo://当前登陆用户信息
isLoggedIn://当前是否已有登录用户  1-是 2-否
isConnected://是否连上聊天服务器   1-是 2-否
isAutoLoginEnabled://是否自动登录  1-是 2-否
</code></pre>

<p data-anchor-id="ljry">}</p>

<div class="md-section-divider"></div>

<h5 id="110onconnected已连接上" data-anchor-id="1d6h">[1.10]onConnected();//已连接上</h5>

<div class="md-section-divider"></div>

<h5 id="111ondisconnectedparam链接断开" data-anchor-id="n73w">[1.11]onDisconnected(param)//链接断开</h5>

<p data-anchor-id="mrf5">var param = {</p>

<pre data-anchor-id="e12h"><code>error:,//1-账号被移除，2-账号其他设备登陆，3-连接不到聊天服务器，4-当前网络不可用 
</code></pre>

<p data-anchor-id="4xg8">};</p>

<div class="md-section-divider"></div>

<h3 id="2message" data-anchor-id="k47g">[2]Message</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="21onnewmessageparam收到新消息监听" data-anchor-id="ic50">[2.1]onNewMessage（param）//收到新消息监听</h5>

<pre data-anchor-id="fnh4"><code>注：param为EMMessage的json格式对象
EMMessage具体结构见文末附录
所有离线和在线时接受到的的非透传消息，都通过此回调传递
</code></pre>

<div class="md-section-divider"></div>

<h5 id="22oncmdmessagereceiveparam透传消息监听" data-anchor-id="6yj2">[2.2]onCmdMessageReceive(param)//透传消息监听</h5>

<p data-anchor-id="wbx3">var param = {</p>

<pre data-anchor-id="vljr"><code>msgId:,
message:,//EMMessage 对象json格式
action:,
</code></pre>

<p data-anchor-id="0b9s">}</p>

<div class="md-section-divider"></div>

<h5 id="23onackmessageparam消息已读监听" data-anchor-id="rg9x">[2.3]onAckMessage(param)//消息已读监听</h5>

<p data-anchor-id="r7yn">var param = {</p>

<pre data-anchor-id="3mw6"><code>msgId:,//消息ID
username:,//来源
</code></pre>

<p data-anchor-id="vs3h">};</p>

<div class="md-section-divider"></div>

<h5 id="24ondeliverymessageparam消息送达监听" data-anchor-id="xsia">[2.4]onDeliveryMessage(param)//消息送达监听</h5>

<p data-anchor-id="0xn2">var param = {</p>

<pre data-anchor-id="e3pr"><code>msgId:,//消息ID
username:,//来源
</code></pre>

<p data-anchor-id="6419">};</p>

<div class="md-section-divider"></div>

<h5 id="25sendtextparam发送文本消息及表情" data-anchor-id="vpp9">[2.5]sendText(param)//发送文本消息及表情</h5>

<p data-anchor-id="dywa">var param = {</p>

<pre data-anchor-id="xycy"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
content:,//文本内容
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="vu6d">}</p>

<div class="md-section-divider"></div>

<h5 id="26sendvoiceparam发送语音" data-anchor-id="4yvq">[2.6]sendVoice(param)//发送语音</h5>

<p data-anchor-id="hyrx">var param = {</p>

<pre data-anchor-id="2yel"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
filePath:,//语音文件路径
length:,//长度(Android必选，iOS可选)
displayName：//对方接收时显示的文件名（仅iOS需要）
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="ajih">}</p>

<div class="md-section-divider"></div>

<h5 id="27sendpictureparam发送图片" data-anchor-id="j9yf">[2.7]sendPicture(param)//发送图片</h5>

<p data-anchor-id="xq78">var param = {</p>

<pre data-anchor-id="tti9"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
filePath:,//图片文件路径
displayName:,//对方接收时显示的文件名（仅iOS需要）
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="ooqs">}</p>

<div class="md-section-divider"></div>

<h5 id="28sendlocationmsgparam发送地理位置信息" data-anchor-id="9vv5">[2.8]sendLocationMsg(param)//发送地理位置信息</h5>

<p data-anchor-id="hpvl">var param = {</p>

<pre data-anchor-id="vlfs"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
locationAddress:,//图片文件路径
latitude:,
longitude:,
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="ih88">}</p>

<div class="md-section-divider"></div>

<h5 id="29sendfileparam发送文件" data-anchor-id="sidn">[2.9]sendFile(param)//发送文件</h5>

<p data-anchor-id="9vqf">var param = {</p>

<pre data-anchor-id="2d6u"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
filePath:,//文件路径
displayName:,//对方接收时显示的文件名（仅iOS需要）
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="52cq">}</p>

<div class="md-section-divider"></div>

<h5 id="210sendcmdmessageparam发送透传消息" data-anchor-id="umui">[2.10]sendCmdMessage(param)//发送透传消息</h5>

<pre data-anchor-id="5x4w"><code>var param = {
chatType:,//1-单聊，2-群聊
action:,//
toUsername:,//
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="i357">}</p>

<div class="md-section-divider"></div>

<h5 id="211setnotifybysoundandvibrateparam消息提醒相关配置" data-anchor-id="mpnh">[2.11]setNotifyBySoundAndVibrate(param)//消息提醒相关配置</h5>

<p data-anchor-id="6nsc">var param = {</p>

<pre data-anchor-id="u6zu"><code>enable:,//0-关闭，1-开启。默认为1 开启新消息提醒
soundEnable:,// 0-关闭，1-开启。默认为1 开启声音提醒
vibrateEnable:,// 0-关闭，1-开启。默认为1 开启震动提醒
userSpeaker:,// 0-关闭，1-开启。默认为1 开启扬声器播放（仅Android可用）
showNotificationInBackgroud:// 0-关闭，1-开启。默认为1。设置后台接收新消息时是否通过通知栏提示 （仅Android可用）
acceptInvitationAlways:,// 0-关闭，1-开启。默认添加好友时为1，是不需要验证的，改成需要验证为0（仅Android可用）
deliveryNotification:，// 0-关闭 1-开启  默认为1 开启消息送达通知   （仅iOS可用）
</code></pre>

<p data-anchor-id="s9s2">}</p>

<div class="md-section-divider"></div>

<h5 id="212getmessagebyidparam根据id获取消息记录" data-anchor-id="7b8p">[2.12]getMessageById(param)//根据id获取消息记录</h5>

<p data-anchor-id="ncah">var param = {</p>

<pre data-anchor-id="0fxw"><code>msgId:,//消息ID
</code></pre>

<p data-anchor-id="yp5g">};</p>

<div class="md-section-divider"></div>

<h5 id="213cbgetmessagebyidparam得到一条消息记录" data-anchor-id="vins">[2.13]cbGetMessageById(param)//得到一条消息记录</h5>

<p data-anchor-id="49po">var param = {</p>

<pre data-anchor-id="7kzj"><code>msg:,// EMMessage的json格式对象
</code></pre>

<p data-anchor-id="a6o7">};</p>

<div class="md-section-divider"></div>

<h5 id="214sendvideoparam发送视频" data-anchor-id="5gc9">[2.14]sendVideo(param)//发送视频</h5>

<p data-anchor-id="pr3a">var param = {</p>

<pre data-anchor-id="qoh7"><code>username:,//单聊时聊天人的userid或者群聊时groupid
chatType:,//1-单聊，2-群聊
filePath:,//视频文件路径
length:,//长度(Android必选，iOS可选)
displayName：//对方接收时显示的文件名（仅iOS需要）
ext:,//扩展属性（可选参数，String)
</code></pre>

<p data-anchor-id="8ug0">}</p>

<div class="md-section-divider"></div>

<h5 id="215sendhasreadresponseformessageparam发送消息已读回执" data-anchor-id="dmp1">[2.15]sendHasReadResponseForMessage(param)//发送消息已读回执</h5>

<p data-anchor-id="b7a3">var param ={</p>

<pre data-anchor-id="0ij8"><code>msgId:,//消息Id
</code></pre>

<p data-anchor-id="1k85">}</p>

<div class="md-section-divider"></div>

<h3 id="3conversation" data-anchor-id="pz24">[3]Conversation</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="31getconversationbynameparam根据用户名获取conversation对象" data-anchor-id="3vx3">[3.1]getConversationByName(param)//根据用户名获取conversation对象</h5>

<p data-anchor-id="xelg">var param = {</p>

<pre data-anchor-id="37ar"><code>username:,
chatType:,//聊天类别 0 - 个人 1 - 群组(仅iOS需要，默认0)
</code></pre>

<div class="md-section-divider"></div>

<h5 id="32cbgetconversationbynameparam回调" data-anchor-id="kbbx">[3.2]cbGetConversationByName(param)//回调</h5>

<p data-anchor-id="pq9e">var param = {</p>

<pre data-anchor-id="3bf0"><code>conversation:,// EMConversation的json格式对象，格式见附录
</code></pre>

<p data-anchor-id="9ger">};</p>

<div class="md-section-divider"></div>

<h5 id="33getmessagehistoryparam获取聊天记录" data-anchor-id="5zcv">[3.3]getMessageHistory(param)//获取聊天记录</h5>

<p data-anchor-id="qlqi">var param = {</p>

<pre data-anchor-id="fcqm"><code>username:,//单聊时聊天人的userName或者群聊时groupid
chatType:,//1-单聊，2-群聊
startMsgId:,//获取startMsgId之前的pagesize条消息
pagesize:,//分页大小，为0时获取所有消息，startMsgId可不传
</code></pre>

<p data-anchor-id="2726">}</p>

<div class="md-section-divider"></div>

<h5 id="34cbgetmessagehistoryparam获取聊天记录回调" data-anchor-id="55y5">[3.4]cbGetMessageHistory(param)//获取聊天记录回调</h5>

<p data-anchor-id="l6lr">var param = {</p>

<pre data-anchor-id="ky7j"><code>messages:,//List&lt;EMMessage&gt;的json格式对象
</code></pre>

<p data-anchor-id="6n72">}</p>

<div class="md-section-divider"></div>

<h5 id="35getunreadmsgcountparam获取未读消息数量" data-anchor-id="h1qy">[3.5]getUnreadMsgCount(param)//获取未读消息数量</h5>

<p data-anchor-id="1sw4">var param = {</p>

<pre data-anchor-id="586v"><code>username:,//username|groupid
chatType:,//聊天类别 0 - 个人 1 - 群组(仅iOS需要，默认0)
</code></pre>

<p data-anchor-id="lm5d">}</p>

<div class="md-section-divider"></div>

<h5 id="36cbgetunreadmsgcountparam获取未读消息数量回调" data-anchor-id="fvoj">[3.6]cbGetUnReadMsgCount(param)//获取未读消息数量回调</h5>

<p data-anchor-id="vcb4">var param = {</p>

<pre data-anchor-id="q6kg"><code>count:,//未读消息数
</code></pre>

<p data-anchor-id="ipvv">}</p>

<div class="md-section-divider"></div>

<h5 id="37resetunreadmsgcountparam指定会话未读消息数清零" data-anchor-id="0bb8">[3.7]resetUnreadMsgCount(param)//指定会话未读消息数清零</h5>

<p data-anchor-id="cb57">var param = {</p>

<pre data-anchor-id="2mz7"><code>username:,//username|groupid
chatType:,//聊天类别 0 - 个人 1 - 群组(仅iOS需要，默认0)
</code></pre>

<p data-anchor-id="oqfd">}</p>

<div class="md-section-divider"></div>

<h5 id="38resetallunreadmsgcount所有未读消息数清零仅android可用" data-anchor-id="fe2k">[3.8]resetAllUnreadMsgCount();//所有未读消息数清零（仅Android可用）</h5>

<div class="md-section-divider"></div>

<h5 id="39getmsgcountparam获取消息总数仅android可用" data-anchor-id="o90f">[3.9]getMsgCount(param)//获取消息总数（仅Android可用）</h5>

<p data-anchor-id="t8nn">var param = {</p>

<pre data-anchor-id="zzc4"><code>username:,//username|groupid
</code></pre>

<p data-anchor-id="dgve">}</p>

<div class="md-section-divider"></div>

<h5 id="310cbgetmsgcountparam获取消息总数回调仅android可用" data-anchor-id="gd5z">[3.10]cbGetMsgCount(param)//获取消息总数回调（仅Android可用）</h5>

<p data-anchor-id="7v16">var param = {</p>

<pre data-anchor-id="1d4f"><code>msgCount:,//消息总数
</code></pre>

<p data-anchor-id="mdxr">}</p>

<div class="md-section-divider"></div>

<h5 id="311clearconversationparam清空会话聊天记录仅android可用" data-anchor-id="3ll3">[3.11]clearConversation(param)//清空会话聊天记录（仅Android可用）</h5>

<p data-anchor-id="kbzy">var param = {</p>

<pre data-anchor-id="tsop"><code>username:,//username|groupid
</code></pre>

<p data-anchor-id="1fus">}</p>

<div class="md-section-divider"></div>

<h5 id="312deleteconversationparam删除和某个user的整个的聊天记录包括本地" data-anchor-id="tj1p">[3.12]deleteConversation(param)//删除和某个user的整个的聊天记录(包括本地)</h5>

<p data-anchor-id="dux5">var param = {</p>

<pre data-anchor-id="e66f"><code>username:,//username|gr oupid
chatType:,//0-个人 1-群组（默认0，此参数仅iOS需要）
</code></pre>

<p data-anchor-id="9lwq">}</p>

<div class="md-section-divider"></div>

<h5 id="313removemessageparam删除当前会话的某条聊天记录" data-anchor-id="apfr">[3.13]removeMessage(param)//删除当前会话的某条聊天记录</h5>

<p data-anchor-id="kwrx">var param = {</p>

<pre data-anchor-id="apum"><code>username:,//username|groupid
msgId:,
chatType:,//0-个人 1-群组（默认0，此参数仅iOS需要）
</code></pre>

<p data-anchor-id="ukcj">}</p>

<div class="md-section-divider"></div>

<h5 id="314deleteallconversation删除所有会话记录包括本地" data-anchor-id="tm8z">[3.14]deleteAllConversation();//删除所有会话记录(包括本地)</h5>

<div class="md-section-divider"></div>

<h5 id="315getchatterinfo获取聊天对象信息" data-anchor-id="tgnl">[3.15]getChatterInfo();//获取聊天对象信息</h5>

<div class="md-section-divider"></div>

<h5 id="316cbgetchatterinfoparam获取聊天对象信息回调" data-anchor-id="bp9v">[3.16]cbGetChatterInfo(param);//获取聊天对象信息回调</h5>

<pre data-anchor-id="paju"><code>param为list&lt;chatterInfo&gt;,一个由chatterInfo结构组成的数组。
</code></pre>

<p data-anchor-id="v4pk">var chatterInfo = {</p>

<pre data-anchor-id="qx4v"><code>chatter;// 联系人的username或群组的groupId
groupName;// 群组名（仅群组有此值）
chatType:,//0-个人 1-群组
unreadMsgCount;//未读消息数
lastMsg;//EMMessage格式的json字符串，最后一条消息
</code></pre>

<p data-anchor-id="yvy8">}</p>

<div class="md-section-divider"></div>

<h5 id="317gettotalunreadmsgcount获取总计未读消息数" data-anchor-id="r6gg">[3.17]getTotalUnreadMsgCount();//获取总计未读消息数</h5>

<div class="md-section-divider"></div>

<h5 id="317cbgettotalunreadmsgcountparam获取总计未读消息数回调" data-anchor-id="ylz6">[3.18]cbGetTotalUnreadMsgCount(param);//获取总计未读消息数回调</h5>

<p data-anchor-id="tc4g">var param ={ <br>
    count:,//总计未读消息数 <br>
}</p>

<div class="md-section-divider"></div>

<h3 id="4friend" data-anchor-id="9avb">[4]Friend</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="41oncontactaddedparam新增联系人监听仅android" data-anchor-id="c06a">[4.1]onContactAdded(param)//新增联系人监听（仅Android）</h5>

<p data-anchor-id="1vzj">var param = {</p>

<pre data-anchor-id="h8fk"><code>userNameList:,//json格式的List&lt;String&gt;
</code></pre>

<p data-anchor-id="zkmf">};</p>

<div class="md-section-divider"></div>

<h5 id="42oncontactdeletedparam删除联系人监听仅android" data-anchor-id="nnes">[4.2]onContactDeleted(param)//删除联系人监听（仅Android）</h5>

<p data-anchor-id="apq1">var param = {</p>

<pre data-anchor-id="vlcw"><code>userNameList:,//json格式的List&lt;String&gt;
</code></pre>

<p data-anchor-id="87oi">};</p>

<div class="md-section-divider"></div>

<h5 id="43oncontactinvitedparam接到好友申请" data-anchor-id="rexj">[4.3]onContactInvited(param)//接到好友申请</h5>

<p data-anchor-id="c8r9">var param = {</p>

<pre data-anchor-id="mcr4"><code>username:,//
reason:,//
</code></pre>

<p data-anchor-id="2q9r">};</p>

<div class="md-section-divider"></div>

<h5 id="44oncontactagreedparam好友请求被同意" data-anchor-id="wi3u">[4.4]onContactAgreed(param)//好友请求被同意</h5>

<p data-anchor-id="ykul">var param = {</p>

<pre data-anchor-id="ljzs"><code>username:,//
</code></pre>

<p data-anchor-id="q1fv">};</p>

<div class="md-section-divider"></div>

<h5 id="45oncontactrefusedparam好友请求被拒绝" data-anchor-id="v3fj">[4.5]onContactRefused(param)//好友请求被拒绝</h5>

<p data-anchor-id="jswp">var param = {</p>

<pre data-anchor-id="4dln"><code>username:,//
</code></pre>

<p data-anchor-id="8423">};</p>

<div class="md-section-divider"></div>

<h5 id="46getcontactusernames获取好友列表" data-anchor-id="8mm8">[4.6]getContactUserNames();//获取好友列表</h5>

<div class="md-section-divider"></div>

<h5 id="47cbgetcontactusernamesparam获取好友列表回调" data-anchor-id="58lm">[4.7]cbGetContactUserNames(param)//获取好友列表回调</h5>

<p data-anchor-id="gyt5">var param = {</p>

<pre data-anchor-id="pmvd"><code>usernames:,//用户姓名字符串构成的数组   
</code></pre>

<p data-anchor-id="ede1">}</p>

<div class="md-section-divider"></div>

<h5 id="48addcontactparam添加好友" data-anchor-id="kqju">[4.8]addContact(param)//添加好友</h5>

<p data-anchor-id="wq35">var param = {</p>

<pre data-anchor-id="s77t"><code>toAddUsername:,//要添加的好友
reason:
</code></pre>

<p data-anchor-id="3nv9">}</p>

<div class="md-section-divider"></div>

<h5 id="49deletecontactparam删除好友" data-anchor-id="5qt1">[4.9]deleteContact(param)//删除好友</h5>

<p data-anchor-id="gq9z">var param = {</p>

<pre data-anchor-id="8690"><code>username:,//
</code></pre>

<p data-anchor-id="59rz">}</p>

<div class="md-section-divider"></div>

<h5 id="410acceptinvitationparam同意username的好友请求" data-anchor-id="aype">[4.10]acceptInvitation(param)//同意username的好友请求</h5>

<p data-anchor-id="wvqw">var param = {</p>

<pre data-anchor-id="jx02"><code>username:,//
</code></pre>

<p data-anchor-id="v71w">}</p>

<div class="md-section-divider"></div>

<h5 id="411refuseinvitationparam拒绝username的好友请求" data-anchor-id="vzi7">[4.11]refuseInvitation(param)//拒绝username的好友请求</h5>

<p data-anchor-id="9dvz">var param = {</p>

<pre data-anchor-id="tzf2"><code>username:,//
reason:,//拒绝好友请求原因（仅iOS需要）
</code></pre>

<p data-anchor-id="t9ty">}</p>

<div class="md-section-divider"></div>

<h5 id="412getblacklistusernames获取黑名单列表" data-anchor-id="oejj">[4.12]getBlackListUsernames();//获取黑名单列表</h5>

<div class="md-section-divider"></div>

<h5 id="413cbgetblacklistusernamesparam获取黑名单列表回调" data-anchor-id="ebit">[4.13]cbGetBlackListUsernames(param)//获取黑名单列表回调</h5>

<p data-anchor-id="hrhj">var param = {</p>

<pre data-anchor-id="nqhw"><code>usernames:,//List&lt;String&gt; json格式
</code></pre>

<p data-anchor-id="dlvt">}</p>

<div class="md-section-divider"></div>

<h5 id="414addusertoblacklistparam把用户加入到黑名单" data-anchor-id="ut0n">[4.14]addUserToBlackList(param)//把用户加入到黑名单</h5>

<p data-anchor-id="t3l6">var param = {</p>

<pre data-anchor-id="igjx"><code>username:,//
</code></pre>

<p data-anchor-id="obv5">}</p>

<div class="md-section-divider"></div>

<h5 id="415deleteuserfromblacklistparam把用户从黑名单中移除" data-anchor-id="yxif">[4.15]deleteUserFromBlackList(param)//把用户从黑名单中移除</h5>

<p data-anchor-id="bw82">var param = {</p>

<pre data-anchor-id="3k4o"><code>username:,//
</code></pre>

<p data-anchor-id="agof">}</p>

<div class="md-section-divider"></div>

<h3 id="5group" data-anchor-id="5ds9">[5]Group</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="51oninvitationdeclinedparam群聊邀请被拒绝" data-anchor-id="28zc">[5.1]onInvitationDeclined(param)//群聊邀请被拒绝</h5>

<p data-anchor-id="4omj">var param = {</p>

<pre data-anchor-id="25wj"><code>groupId:,
invitee:,
reason:,
</code></pre>

<p data-anchor-id="as6b">}</p>

<div class="md-section-divider"></div>

<h5 id="52onuserremovedparam当前用户被管理员移除出群聊" data-anchor-id="dzd5">[5.2]onUserRemoved(param)//当前用户被管理员移除出群聊</h5>

<p data-anchor-id="v7a0">var param = {</p>

<pre data-anchor-id="m1kx"><code>groupId:,
groupName:,
</code></pre>

<p data-anchor-id="jb9z">}</p>

<div class="md-section-divider"></div>

<h5 id="53ongroupdestroyparam群聊被创建者解散" data-anchor-id="23gf">[5.3]onGroupDestroy(param)//群聊被创建者解散</h5>

<p data-anchor-id="8s3y">var param = {</p>

<pre data-anchor-id="6fcn"><code>groupId:,
groupName:,
</code></pre>

<p data-anchor-id="ykhz">}</p>

<div class="md-section-divider"></div>

<h5 id="54onapplicationreceivedparam用户申请加入群聊收到加群申请" data-anchor-id="ass6">[5.4]onApplicationReceived(param)//用户申请加入群聊，收到加群申请</h5>

<p data-anchor-id="57sh">var param = {</p>

<pre data-anchor-id="97y3"><code>groupId:,
groupName:,
applyer:,
reason:,
</code></pre>

<p data-anchor-id="ekst">}</p>

<div class="md-section-divider"></div>

<h5 id="55onapplicationacceptparam-加群申请被同意" data-anchor-id="67fk">[5.5]onApplicationAccept(param)// // 加群申请被同意</h5>

<p data-anchor-id="pi9m">var param = {</p>

<pre data-anchor-id="dk83"><code>groupId:,
groupName:,
accepter:,
</code></pre>

<p data-anchor-id="wh6k">}</p>

<div class="md-section-divider"></div>

<h5 id="56onapplicationdeclinedparam加群申请被拒绝" data-anchor-id="p7so">[5.6]onApplicationDeclined(param)//加群申请被拒绝</h5>

<p data-anchor-id="l0o8">var param = {</p>

<pre data-anchor-id="grvj"><code>groupId:,//（仅Android）
groupName:,
decliner:,
reason:,
</code></pre>

<p data-anchor-id="g64l">}</p>

<div class="md-section-divider"></div>

<h5 id="57createprivategroupparam创建私有群" data-anchor-id="5rfs">[5.7]createPrivateGroup(param)//创建私有群</h5>

<p data-anchor-id="hf7b">var param = {</p>

<pre data-anchor-id="80yo"><code>groupName:,//要创建的群聊的名称
desc://群聊简介
members://群聊成员,为空时这个创建的群组只包含自己
allowInvite://是否允许群成员邀请人进群
maxUsers://最大群聊用户数，可选参数，默认为200，最大为2000
initialWelcomeMessage://群组创建时发送给每个初始成员的欢迎信息（仅iOS需要）
</code></pre>

<p data-anchor-id="155q">}</p>

<div class="md-section-divider"></div>

<h5 id="58createpublicgroupparam创建公开群" data-anchor-id="7gwj">[5.8]createPublicGroup(param)//创建公开群</h5>

<p data-anchor-id="qxcn">var param = {</p>

<pre data-anchor-id="g32q"><code>groupName:,//要创建的群聊的名称
desc://群聊简介
members://群聊成员,为空时这个创建的群组只包含自己
needApprovalRequired://如果创建的公开群用需要户自由加入，就传false。否则需要申请，等群主批准后才能加入，传true
maxUsers://最大群聊用户数，可选参数，默认为200，最大为2000
initialWelcomeMessage://群组创建时发送给每个初始成员的欢迎信息（仅iOS需要）
</code></pre>

<p data-anchor-id="0uwu">}</p>

<div class="md-section-divider"></div>

<h5 id="59adduserstogroupparam群聊加人" data-anchor-id="zdrt">[5.9]addUsersToGroup(param)//群聊加人</h5>

<p data-anchor-id="9f2c">var param = {</p>

<pre data-anchor-id="h9xa"><code>isGroupOwner:,//是否群主(仅Android需要)
groupId://
newmembers://群聊新成员，List&lt;String&gt; Json格式
inviteMessage:// 新增参数 邀请信息
</code></pre>

<p data-anchor-id="cz7h">}</p>

<div class="md-section-divider"></div>

<h5 id="510removeuserfromgroupparam群聊减人" data-anchor-id="np5m">[5.10]removeUserFromGroup(param)//群聊减人</h5>

<p data-anchor-id="9or4">var param = {</p>

<pre data-anchor-id="498y"><code>groupId://
username://
</code></pre>

<p data-anchor-id="psbi">} </p>

<pre data-anchor-id="6d6r"><code>只有owner才有权限进行此操作
</code></pre>

<div class="md-section-divider"></div>

<h5 id="511joingroupparam加入某个群聊只能用于加入公开群" data-anchor-id="0od6">[5.11]joinGroup(param)//加入某个群聊，只能用于加入公开群</h5>

<p data-anchor-id="9i6v">var param = {</p>

<pre data-anchor-id="8fep"><code>groupId://
reason:// //如果群开群是自由加入的，即group.isMembersOnly()为false，此参数不传
groupName://群组名称
</code></pre>

<p data-anchor-id="0ldb">}</p>

<div class="md-section-divider"></div>

<h5 id="512exitfromgroupparam退出群聊" data-anchor-id="11r4">[5.12]exitFromGroup(param)//退出群聊</h5>

<p data-anchor-id="7zu2">var param = {</p>

<pre data-anchor-id="z322"><code>groupId://
</code></pre>

<p data-anchor-id="u78m">}</p>

<div class="md-section-divider"></div>

<h5 id="513exitanddeletegroupparam解散群聊" data-anchor-id="7rej">[5.13]exitAndDeleteGroup(param)//解散群聊</h5>

<p data-anchor-id="oy5x">var param = {</p>

<pre data-anchor-id="zsin"><code>groupId://
</code></pre>

<p data-anchor-id="fj3j">}</p>

<div class="md-section-divider"></div>

<h5 id="514getgroupsfromserverparam从服务器获取自己加入的和创建的群聊列表" data-anchor-id="avmu">[5.14]getGroupsFromServer(param)//从服务器获取自己加入的和创建的群聊列表</h5>

<p data-anchor-id="z3cw">var param = {</p>

<pre data-anchor-id="feu7"><code>loadCache://是否从本地加载缓存，（默认为false，从网络获取）
</code></pre>

<p data-anchor-id="wohb">}</p>

<div class="md-section-divider"></div>

<h5 id="515cbgetgroupsfromserverparam从服务器获取自己加入的和创建的群聊列表回调" data-anchor-id="d8ok">[5.15]cbGetGroupsFromServer(param)//从服务器获取自己加入的和创建的群聊列表回调</h5>

<p data-anchor-id="3jfi">var param = {</p>

<pre data-anchor-id="q1fj"><code>result://0-成功，1-失败
grouplist://List&lt;EMGroup&gt; json格式
errorMsg:
</code></pre>

<p data-anchor-id="lx9k">}</p>

<div class="md-section-divider"></div>

<h5 id="516getallpublicgroupsfromserverparam获取所有公开群列表" data-anchor-id="aumx">[5.16]getAllPublicGroupsFromServer(param);//获取所有公开群列表</h5>

<p data-anchor-id="xd8i">var param = {</p>

<pre data-anchor-id="fiht"><code>pageSize://期望结果的数量, 如果 &lt; 0 则一次返回所有结果
cursor://获取公开群的cursor，首次调用传空即可
}
</code></pre>

<div class="md-section-divider"></div>

<h5 id="517cbgetallpublicgroupsfromserverparam获取所有公开群列表回调" data-anchor-id="isgb">[5.17]cbGetAllPublicGroupsFromServer(param)//获取所有公开群列表回调</h5>

<p data-anchor-id="vdo6">var param = {</p>

<pre data-anchor-id="tsy0"><code>result://0-成功，1-失败
grouplist:List&lt; EMGroup&gt; json格式 见附录
errorMsg:
cursor:,//
</code></pre>

<p data-anchor-id="fjuv">}</p>

<div class="md-section-divider"></div>

<h5 id="518getgroupparam获取单个群聊信息" data-anchor-id="ag13">[5.18]getGroup(param)//获取单个群聊信息</h5>

<p data-anchor-id="lh0h">var param = {</p>

<pre data-anchor-id="gt07"><code>groupId:,//
loadCache://是否从本地加载缓存，（默认为false，从网络获取）
</code></pre>

<p data-anchor-id="i94u">}</p>

<div class="md-section-divider"></div>

<h5 id="519cbgetgroupparam获取单个群聊信息回调" data-anchor-id="lj2f">[5.19]cbGetGroup(param)//获取单个群聊信息回调</h5>

<p data-anchor-id="3flf">var param = {</p>

<pre data-anchor-id="5ibu"><code>group://EMGroup 对象json格式  
</code></pre>

<p data-anchor-id="nw7q">}</p>

<div class="md-section-divider"></div>

<h5 id="520blockgroupmessageparam屏蔽群消息" data-anchor-id="71ad">[5.20]blockGroupMessage(param)//屏蔽群消息</h5>

<p data-anchor-id="p64x">var param = {</p>

<pre data-anchor-id="pz3y"><code>groupId:// 
</code></pre>

<p data-anchor-id="azak">}</p>

<div class="md-section-divider"></div>

<h5 id="521unblockgroupmessageparam解除屏蔽群" data-anchor-id="rqrz">[5.21]unblockGroupMessage(param)//解除屏蔽群</h5>

<p data-anchor-id="y0yv">var param = {</p>

<pre data-anchor-id="lup2"><code>groupId:// 
</code></pre>

<p data-anchor-id="0aow">}</p>

<div class="md-section-divider"></div>

<h5 id="522changegroupnameparam修改群组名称" data-anchor-id="09ug">[5.22]changeGroupName(param)//修改群组名称</h5>

<p data-anchor-id="se5b">var param = {</p>

<pre data-anchor-id="sadc"><code>groupId:// 
changedGroupName:,//改变后的群组名称
</code></pre>

<p data-anchor-id="gcnz">}</p>

<div class="md-section-divider"></div>

<h5 id="523setreceivenotnoifygroupparam群聊不提醒只显示数目仅android可用" data-anchor-id="s75f">[5.23]setReceiveNotNoifyGroup(param)//群聊不提醒只显示数目（仅Android可用）</h5>

<p data-anchor-id="ju0u">var param = {</p>

<pre data-anchor-id="86dc"><code>groupIds:// List&lt;String&gt; 
</code></pre>

<p data-anchor-id="4vri">}</p>

<div class="md-section-divider"></div>

<h5 id="524blockuserparam将群成员拉入群组的黑名单仅android可用" data-anchor-id="4exr">[5.24]blockUser(param)//将群成员拉入群组的黑名单（仅Android可用）</h5>

<p data-anchor-id="mpf2">var param = {</p>

<pre data-anchor-id="7ilk"><code>groupId:,// 
username://待屏蔽的用户名
</code></pre>

<p data-anchor-id="pcq3">}</p>

<div class="md-section-divider"></div>

<h5 id="525unblockuserparam将拉入黑名单的群成员移除仅android可用" data-anchor-id="6a5i">[5.25]unblockUser(param)//将拉入黑名单的群成员移除（仅Android可用）</h5>

<p data-anchor-id="7anu">var param = {</p>

<pre data-anchor-id="1k3i"><code>groupId:,// 
username://待解除屏蔽的 用户名
</code></pre>

<p data-anchor-id="l9br">}</p>

<div class="md-section-divider"></div>

<h5 id="526getblockedusersparam获取群组的黑名单用户列表仅android可用" data-anchor-id="9cco">[5.26]getBlockedUsers(param)//获取群组的黑名单用户列表（仅Android可用）</h5>

<p data-anchor-id="7g7p">var param = {</p>

<pre data-anchor-id="hwyt"><code>groupId:,// 
</code></pre>

<p data-anchor-id="2tdr">}</p>

<div class="md-section-divider"></div>

<h5 id="527cbgetblockedusersparam获取群组的黑名单用户列表回调仅android" data-anchor-id="d9se">[5.27]cbGetBlockedUsers(param)//获取群组的黑名单用户列表回调（仅Android）</h5>

<pre data-anchor-id="2pmo"><code>var param = {
usernames:,// List&lt;String&gt; json格式 
</code></pre>

<p data-anchor-id="ihln">}</p>

<div class="md-section-divider"></div>

<h5 id="528ongroupupdateinfoparam群组信息更新的监听仅ios" data-anchor-id="dsaq">[5.28]onGroupUpdateInfo(param)//群组信息更新的监听（仅iOS）</h5>

<p data-anchor-id="uevc">var param={</p>

<pre data-anchor-id="uyhs"><code>    group:,//EMGroup对象的json格式字符串
</code></pre>

<p data-anchor-id="kxua">}</p>

<pre data-anchor-id="bmu5"><code>每当添加/移除/更改角色/更改主题/更改群组信息之后,都会触发此回调
</code></pre>

<div class="md-section-divider"></div>

<h3 id="6call" data-anchor-id="66p2">[6]Call</h3>

<hr>

<div class="md-section-divider"></div>

<h5 id="61oncallreceiveparam-实时语音监听" data-anchor-id="yfde">[6.1]onCallReceive(param)// 实时语音监听</h5>

<p data-anchor-id="krxn">var param = {</p>

<pre data-anchor-id="ypl0"><code>from;//拨打方username
callType;//0-语音电话 1-视频电话
callId;//本次通话的EMSessionId
</code></pre>

<p data-anchor-id="tr3i">}</p>

<div class="md-section-divider"></div>

<h5 id="62oncallstatechangedparam通话状态监听" data-anchor-id="2b2o">[6.2]onCallStateChanged(param)//通话状态监听</h5>

<p data-anchor-id="y0wb">var param = {</p>

<pre data-anchor-id="fxtw"><code>state:,//1-正在连接对方，2-双方已经建立连接，3-同意语音申请，建立语音通话中，4-连接中断 5-电话暂停中 6-电话等待对方同意接听 7-通话中 
</code></pre>

<p data-anchor-id="n949">}</p>

<pre data-anchor-id="vpsk"><code>eg. 一个成功的语音通话流程为 ：A发送通话请求给B ==&gt; AB建立语音通话连接 ==&gt; B同意语音通话 ==&gt; 开始语音通话
</code></pre>

<div class="md-section-divider"></div>

<h5 id="63makevoicecallparam拨打语音通话" data-anchor-id="9jzd">[6.3]makeVoiceCall(param)//拨打语音通话</h5>

<p data-anchor-id="rfn8">var param = {</p>

<pre data-anchor-id="wzf7"><code>username:,//
</code></pre>

<p data-anchor-id="gd5r">}</p>

<div class="md-section-divider"></div>

<h5 id="64answercall接听通话" data-anchor-id="d68h">[6.4]answerCall();//接听通话</h5>

<div class="md-section-divider"></div>

<h5 id="65rejectcall拒绝接听" data-anchor-id="72xk">[6.5]rejectCall();//拒绝接听</h5>

<div class="md-section-divider"></div>

<h5 id="66endcall挂断通话" data-anchor-id="jmqj">[6.6]endCall();//挂断通话</h5>

<div class="md-section-divider"></div>

<h3 id="7apns以下方法全部仅限ios" data-anchor-id="9uny">[7]Apns（以下方法全部仅限iOS）</h3>

<div class="md-section-divider"></div>

<h5 id="71registerremotenotification注册apns推送" data-anchor-id="7xo6">[7.1]registerRemoteNotification();//注册Apns推送</h5>

<div class="md-section-divider"></div>

<h5 id="72-cbregisterremotenotificationparam回调" data-anchor-id="l08i">[7.2] cbRegisterRemoteNotification(param);//回调</h5>

<p data-anchor-id="gii8">var param{</p>

<pre data-anchor-id="x3zt"><code>result;//1-成功 2-失败
errorInfo;//注册失败时的错误信息
</code></pre>

<p data-anchor-id="vkho">}</p>

<div class="md-section-divider"></div>

<h5 id="73onapnslaunchparam" data-anchor-id="5l8k">[7.3]onApnsLaunch(param);</h5>

<pre data-anchor-id="50u0"><code>若APP是通过点击apns推送调起的，当插件初始化时会触发此回调。
param为此条推送的内容，json格式。
</code></pre>

<div class="md-section-divider"></div>

<h5 id="74updatepushoptionsparam设置apns全局属性" data-anchor-id="1c8p">[7.4]updatePushOptions(param);//设置apns全局属性</h5>

<p data-anchor-id="w23n">var param{</p>

<pre data-anchor-id="wvrr"><code>nickname;//昵称
displayStyle;//推送显示类型 0-提示"您有一条新消息" 1- 显示详细消息内容 
noDisturbingStyle;//是否开启免打扰模式 0-全天免打扰 1-自定义时段免打扰 2- 关闭免打扰
noDisturbingStartH;//免打扰模式开始时间  小时（int）
noDisturbingEndH;//免打扰模式结束时间  小时（int）
</code></pre>

<p data-anchor-id="tczd">}</p>

<div class="md-section-divider"></div>

<h5 id="75cbupdatepushoptionsparam设置apns全局属性回调" data-anchor-id="7kme">[7.5]cbUpdatePushOptions(param);//设置apns全局属性回调</h5>

<p data-anchor-id="fcqv">var param{</p>

<pre data-anchor-id="0gzx"><code>nickname;//昵称
displayStyle;//推送显示类型 0-提示"您有一条新消息" 1- 显示详细消息内容 
noDisturbingStyle;//是否开启免打扰模式 0-全天免打扰 1-自定义时段免打扰 2- 关闭免打扰
noDisturbingStartH;//免打扰模式开始时间  小时（int）
noDisturbingEndH;//免打扰模式结束时间  小时（int）
</code></pre>

<p data-anchor-id="i655">}</p>

<pre data-anchor-id="ipvx"><code>说明：updatePushOptions全为可选参数，当传入空值时，即可通过回调获得当前apns全局属性
</code></pre>

<div class="md-section-divider"></div>

<h5 id="76ignoregrouppushnotificationparam设置指定群组是否接收" data-anchor-id="8ipl">[7.6]ignoreGroupPushNotification(param)://设置指定群组是否接收</h5>

<p data-anchor-id="6hdu">var param{</p>

<pre data-anchor-id="rz99"><code>groupId;//指定的群组Id
isIgnore;//1-屏蔽  2-取消屏蔽
</code></pre>

<p data-anchor-id="bq9q">}</p>

<div class="md-section-divider"></div>

<h5 id="77cbignoregrouppushnotificationparam回调" data-anchor-id="crxm">[7.7]cbIgnoreGroupPushNotification(param)://回调</h5>

<p data-anchor-id="k7ys">var param{</p>

<pre data-anchor-id="vd85"><code>groupIds;//已屏蔽接收推送消息的群列表
</code></pre>

<p data-anchor-id="6e8j">}</p>

<div class="md-section-divider"></div>

<h2 id="附录" data-anchor-id="9j1k">附录</h2>

<div class="md-section-divider"></div>

<h4 id="emmessage-json字符串返回值结构" data-anchor-id="9uij">EMMessage json字符串返回值结构</h4>

<table data-anchor-id="5s5j" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>from</td>
 <td>发送者</td>
</tr>
<tr>
 <td>to</td>
 <td>接受者</td>
</tr>
<tr>
 <td>messageId</td>
 <td>消息id</td>
</tr>
<tr>
 <td>messageTime</td>
 <td>消息发送或接收的时间</td>
</tr>
<tr>
 <td>isAcked</td>
 <td>是否接收到了接收方的阅读回执, 或是否已发送了阅读回执给对方</td>
</tr>
<tr>
 <td>isDelivered</td>
 <td>对于发送方来说, 该值表示:接收方是否已收到了消息, 对于接收方来说, 表示:接收方是否已发送了"已接收回执" 给对方</td>
</tr>
<tr>
 <td>isRead</td>
 <td>是否已读</td>
</tr>
<tr>
 <td>chatType:</td>
 <td>聊天类别 0-个人 1-群组</td>
</tr>
<tr>
 <td>messageType</td>
 <td>消息类型  text/video/audio/image/location/file/cmd</td>
</tr>
<tr>
 <td>ext</td>
 <td>扩展属性 String格式</td>
</tr>
<tr>
 <td>messageBody</td>
 <td>消息主体json</td>
</tr>
</tbody></table>


<p data-anchor-id="7rhr">messageBody的结构为</p>

<div class="md-section-divider"></div>

<h5 id="普通文本消息" data-anchor-id="annu">普通文本消息</h5>

<table data-anchor-id="gn4h" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>text</td>
 <td>文本内容</td>
</tr>
</tbody></table>


<div class="md-section-divider"></div>

<h5 id="透传消息" data-anchor-id="s342">透传消息</h5>

<table data-anchor-id="kwvp" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>action</td>
 <td>具体命令</td>
</tr>
</tbody></table>


<div class="md-section-divider"></div>

<h5 id="位置消息" data-anchor-id="z0kx">位置消息</h5>

<table data-anchor-id="z1yn" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>longitute</td>
 <td>经度</td>
</tr>
<tr>
 <td>latitude</td>
 <td>纬度</td>
</tr>
<tr>
 <td>address</td>
 <td>地理位置信息</td>
</tr>
</tbody></table>


<div class="md-section-divider"></div>

<h5 id="视频语音图片文件消息" data-anchor-id="lj1y">视频/语音/图片/文件消息</h5>

<table data-anchor-id="btfm" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>displayName</td>
 <td>显示名</td>
</tr>
<tr>
 <td>remotePath</td>
 <td>服务器远程文件路径</td>
</tr>
<tr>
 <td>secretKey</td>
 <td>远端文件的密钥</td>
</tr>
<tr>
 <td>length</td>
 <td>长度 （单位:秒 仅语音/视频消息）</td>
</tr>
<tr>
 <td>thumbnailRemotePath</td>
 <td>预览图文件的服务器远程路径(仅视频/图片消息)</td>
</tr>
<tr>
 <td>thumbnailSecretKey</td>
 <td>预览图文件的密钥(仅视频/图片消息)</td>
</tr>
</tbody></table>


<p data-anchor-id="b6se"><code>注</code>：由于<code>Android SDK</code>不能获取<code>已发送消息</code>的<code>remotePath</code>和<code>thumbnailRemotePath</code>，改用<code>本地文件路径</code>（file://开头）代替</p>

<pre data-anchor-id="tec4"><code>返回的json数据中会包含除上述属性之外的一些其他信息，均可以忽略
</code></pre>

<div class="md-section-divider"></div>

<h4 id="emconversation-json字符串返回值结构" data-anchor-id="f4c7">EMConversation json字符串返回值结构</h4>

<table data-anchor-id="ynp6" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>chatter</td>
 <td>conversation识别名</td>
</tr>
<tr>
 <td>chatType</td>
 <td>聊天类别 0-个人 1-群组</td>
</tr>
<tr>
 <td>messages</td>
 <td>"conversation所包含的message列表，表内元素为EMMessage的json字符串"</td>
</tr>
</tbody></table>


<pre data-anchor-id="5b7r"><code>返回的json数据中会包含除上述属性之外的一些其他信息，均可以忽略
</code></pre>

<div class="md-section-divider"></div>

<h4 id="emgroup-json字符串返回值结构" data-anchor-id="w8y2">EMGroup json字符串返回值结构</h4>

<table data-anchor-id="uh7r" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>key</th>
 <th>说明</th>
</tr>
</thead>
<tbody><tr>
 <td>groupSubject</td>
 <td>群组名</td>
</tr>
<tr>
 <td>members</td>
 <td>包含的成员</td>
</tr>
<tr>
 <td>owner</td>
 <td>群主</td>
</tr>
<tr>
 <td>isPushNotificationEnable</td>
 <td>是否允许推送提醒</td>
</tr>
<tr>
 <td>isBlock</td>
 <td>是否被用户屏蔽</td>
</tr>
<tr>
 <td>groupMaxUserCount</td>
 <td>群组最大人数</td>
</tr>
<tr>
 <td>groupId</td>
 <td>群组Id</td>
</tr>
<tr>
 <td>isPublic</td>
 <td>群组类型</td>
</tr>
<tr>
 <td>allowInvites</td>
 <td>是否允许群成员邀请人进群</td>
</tr>
<tr>
 <td>membersOnly</td>
 <td>需要申请和验证才能加入</td>
</tr>
</tbody></table>


<div class="md-section-divider"></div>

<h4 id="isgroup参数废弃-改用chattype的相关说明" data-anchor-id="kumc">"isGroup"参数废弃 改用“chatType”的相关说明</h4>

<p data-anchor-id="t9dm">由于环信插件即将添加<code>聊天室功能</code>，<strong>isGroup参数即将不能满足需求</strong>，因此做如下修改:</p>

<ul data-anchor-id="ld7r">
<li>所有的调用API中，入参里的isGroup改为chatType</li>
<li>所有的回调API中，isGroup属性改为chatType</li>
</ul>

<p data-anchor-id="dich">考虑到有已经使用环信插件进行开发的用户，因此有如下<strong>兼容性支持</strong>:</p>

<ul data-anchor-id="q6rw">
<li>调用API中所有的isGroup入参仍然可用，但若传值与chatType冲突，以chatType为准</li>
<li>回调API中如包含isGroup项的，现在会同时包含isGroup项和chatType项</li>
</ul>
</body>
</html>
