# uexLoadingView
   

### 方法：

* [open](#open)
* [close](#close)

---

### open 
打开loading

```
uexLoadingView.open(jsonstr)
```
#### 参数
```
    "x": 
    "y":  
    "w": 宽(宽度需要跟圆点数量相适应，太短会显示不完整)
    "h": 高
    "style": {
        "styleId": //loading的样式，取值为0或1
        "pointNum": //圆点的数量
        "pointColor": [
            "#ffffff" //圆点的颜色
        ]
    }

```
#### 示例：
```
var jsonstr = '{
    "x": 200, 
    "y": 500, 
    "w": 150, 
    "h": 40, 
    "style": {
        "styleId": 1, 
        "pointNum": 4, 
        "pointColor": [
            "#ffffff"
        ]
    }
}';
uexLoadingView.open(jsonstr);
```

### close
关闭loading

#### 示例：

```
uexLoadingView.close();
```
