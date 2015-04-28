#uexTestinCrash 插件接口文档
##简介
***
本插件包封装了Testin崩溃分析的相关模块，能根据实际用户发生的崩溃信息，帮助确定崩溃发生的规模以及严重程度，根据应用版本和崩溃类型进行分析。
开发者能够通过这些信息迅速找到影响用户最严重的崩溃进行修复与优化

##Changelog
***
2015-04-22 初稿 

2014-04-27 增加了一个提供测试的方法



##API
***
###1.init(param)//初始化
	
	var param{
		appKey;//应用的AppKey
		channel;//应用的渠道号
	}

	注：如果在项目中还引用了友盟、Takingdata 等同类产品，需要将它们的错误分析收集的功能取消。
	
###2.setUserInfo(param)//设置用户名
	var param{
		username;//用户名
	}
	
	注：如不设置，平台将默认显示为“匿名用户”。
	
###3.leaveBreadcrumb(param)//上传面包屑
	var param{
		breadcrumb;//面包屑字符串
	}
	
###4.test()//崩溃测试
	注:该方法调用后可能会引起程序崩溃，仅供开发人员测试用.
	   正常使用插件，请勿调用此方法!
		
	