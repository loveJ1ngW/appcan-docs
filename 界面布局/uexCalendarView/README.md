#uexCalendarView
提供日历功能

##方法
* [open](#open) 打开日历
* [close](#close) 关闭日历
* [setSelectedDate](#setselecteddate) 设置日历被选中的日期

##回调方法
* [onItemClick](#onitemclick) 点击日期的回调






###open
打开日历

	uexCalendarView.open(json)
	
###参数
```
var json = {
	x:,//view距离当前网页顶部的距离(px)
	y:,//view距离当前网页左边框的距离(px)
	w:,//view宽度(px)
	h:,//view高度(px)
	}
```

###平台支持

	Android 2.2+
	iOS 6.1+

###版本支持

	Android 3.0.0+
	iOS 3.0.0+

###示例
```
var data ={
    x:0,
	y:0,
    w:300,
	h:300
	};
var jsonStr = JSON.stringify(data)
uexCalendarView.open(jsonStr);

```
###close
 关闭日历
	
	uexCalendarView.close()
###参数

```
无
```
###平台支持
	Android 2.2+
	iOS 6.1+
###版本支持
	Android 3.0.0+
	iOS 3.0.0+
###示例
```
uexCalendarView.close()

```
###setSelectedDate
设置被选中的日期

	uexCalendarView.setSelectedDate(json)
	
###参数
```
var json = {
	date:{  //所设置的日期
		year:,//年
		month:,//月
		day:,//日
	} 
}
```

###平台支持

	Android 2.2+
	iOS 6.1+

###版本支持

	Android 3.0.0+
	iOS 3.0.0+

###示例
```
var data ={
	date:{  
		year:2014,
		moth:11,
		day:11
	}
};
var jsonStr = JSON.stringify(data)
uexCalendarView.setSelectedDate(jsonStr);

```
###onItemClick
 点击日期时的监听方法
	
	uexCalendarView.onItemClick(json)
###参数

```
var json = {
	date:{  //返回的日期
		year:,//年
		month:,//月
		day:,//日
	} 
}
	
```
###平台支持
	Android 2.2+
	iOS 6.1+
###版本支持
	Android 3.0.0+
	iOS 3.0.0+
###示例
```
uexCalendarView.onItemClick = function(data){
	alert(data);
}

```
