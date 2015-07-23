###uexMultiDownloader插件文档

###简介
本插件封装了多任务多线程下载，断点续传功能。只用简单的传入下载url和要保存路径等信息就可以进行下载。


###API概述

####方法
#####[open](#open)
#####[enqueue](#enqueue)
添加下载任务 回调函数[cbEnqueue](#cbEnqueue)
#####[close](#close)

####回调方法
#####[onComplete](#onComplete)
下载完成回调
#####[onTaskDetail](#onTaskDetail)
任务详情回调函数
#####[cbEnqueue](#cbEnqueue)
enqueue回调函数

>###open

打开下载视图
####参数:
```
var params = {
    x:,//x坐标
    y:,//y坐标
    w:,//下载器宽度
    h://下载器高度
};
```


####平台支持：
```
  Android 2.2+
  iOS 6.0+
```
#### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```

####示例
```
var params = {
    x:"0",
    y:"500",
    w:"1000",
    h:"1000"
};
var data = JSON.stringify(params);
uexMultiDownloader.open(data);
```

>###enqueue

添加下载任务
####参数:
```
var params = {
    url:,//下载链接
    savePath:,//保存路径
};
```
####平台支持：
```
  Android 2.2+
  iOS 6.0+
```
#### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```

####示例
```
var params = {
    url:“http://down.360safe.com/360mobilemgr/360box_web.apk”,
    savePath:"/sdcard/360/360box_web.apk"
};
var data = JSON.stringify(params);
uexMultiDownloader.enqueue(data);
```

>###close

关闭下载器
####参数:
```
var params = {
};
```
####平台支持：
```
  Android 2.2+
  iOS 6.0+
```
#### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```

####示例
```
var params = {
};
var data = JSON.stringify(params);
uexMultiDownloader.close(data);
```


>###cbEnqueue

添加下载任务时回调
####参数:
```
var params = {
	result:,//0-成功，1-失败
};
```
####平台支持：
```
  Android 2.2+
  iOS 6.0+
```
#### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```

####示例
```
function cbEnqueue(info){
     alert(info);
}
```

>###onTaskDetail

用户长按任务，出现任务详情的回调，需要自己实现详情的界面
####参数:
```
var params = {
    url://下载地址,
    savePath://保存路径
};
```
####平台支持：
```
  Android 2.2+
  iOS 6.0+
```
#### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```

####示例
```
function onTaskDetail(info){
     alert(info);
}
```

