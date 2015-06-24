# uexAreaPickerView
   该插件封装区域选择的功能，支持三级区域选择

### 方法：
* [open](#open)
* [close](#close)

### 监听方法：
* [onConfirmClick](#onConfirmClick)

---


### open 
打开区域选择

```
uexAreaPickerView.open();
```
#### 参数：
无
#### 平台支持：
```
Android 2.2+
iOS 7.1+
```

### close
关闭区域选择

#### 版本支持：
```
Android 3.0.0+
iOS 7.1+
```
#### 示例：

示例1
```
uexAreaPickerView.close();
```

### onConfirmClick
选中的区域回调
#### 版本支持：
```
Android 3.0.0+
iOS 7.1+
```
#### 示例：

```
uexAreaPickerView.onConfirmClick = function(json){
	 alert("onConfirmClick "+json);
}
```
#### 参数：
```
city:"河北石家庄市长安区"
```

