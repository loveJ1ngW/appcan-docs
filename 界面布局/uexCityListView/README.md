# uexCityListView
   该插件封装城市选择的功能

### 方法：
* [open](#open)
* [setLocalCity](#setLocalCity)
* [setHotCity](#setHotCity)
* [setAllCity](#setAllCity)
* [setViewStyle](#setViewStyle)
* [close](#close)

### 监听方法：
* [onItemClick](#onItemClick)

---

### open 
打开城市选择

```
uexCityListView.open(x,y,w,h);
```
#### 示例：
```
uexCityListView.open("0","600","720","1230");
```

### setLocalCity
设置当前定位城市


#### 参数：
```
localCity:当前定位到的城市
```

#### 示例：

```
 var localCity = '{"localCity":"北京"}';
 uexCityListView.setLocalCity(localCity);
```

### setHotCity
设置热门城市

#### 参数：
```
hotCity:热门城市列表，List<String>
```

#### 示例：

```
var hotCity = '{"hotCity":["北京","重庆","成都","广州","厦门","杭州","上海","武汉","深圳"]}';
uexCityListView.setHotCity(hotCity);
```

### setAllCity
设置所有的城市

#### 参数：
参数为存放所有城市数据的文件路径。
文件内容格式为Json字符串，示例：
city.json内容

```
{
    allCity: {
        '安吉': 'anji',
        '安康': 'ankang'
    }
}
```

#### 示例：

```
uexCityListView.setAllCity("res://city.json");
```

### setViewStyle
设置城市选择视图的样式

#### 参数：

```
    "searchBar": {//搜索栏配置参数
        "placehoderText": //输入框的默认显示文本 
        "bgColor": //背景色
        "textColor": //文字颜色 
        "inputBgColor": //输入框的背景色
    }, 
    "headerView": {//定位、最近访问、热门城市区域配置参数
        "bgColor": //背景色
        "separatorLineColor": //分割线颜色
        "sectionHeaderTitleColor": //标题颜色
        "itemTextColor": //每个城市的文字颜色
    }, 
    "listView": {//所有城市列表区域配置参数
        "bgColor": //背景色
        "separatorLineColor": //分割线颜色
        "sectionHeaderTitleColor"://分段标题的颜色 
        "sectionHeaderBgColor": //分段标题的背景色, 
        "itemTextColor": //每个城市的文字颜色
    }, 
    "indexBar": {
        "indexBarTextColor": //右边快速定位文字的颜色
    }

```

#### 示例：

```
var params = '
{
    "searchBar": {
        "placehoderText": "请输入城市", 
        "bgColor": "#ffdddddd", 
        "textColor": "#ff0000ff", 
        "inputBgColor": "#ffffffff"
    }, 
    "headerView": {
        "bgColor": "#ffeeeeee", 
        "separatorLineColor": "#ff0000ff", 
        "sectionHeaderTitleColor": "#ff0000ff", 
        "itemTextColor": "#ff0000ff"
    }, 
    "listView": {
        "bgColor": "#ffffffff", 
        "separatorLineColor": "#ff0000ff", 
        "sectionHeaderTitleColor": "#ff0000ff", 
        "sectionHeaderBgColor": "#aadddddd", 
        "itemTextColor": "#ff0000ff"
    }, 
    "indexBar": {
        "indexBarTextColor": "#ff0000ff"
    }
}
';
uexCityListView.setViewStyle(params);
```

### close
关闭城市选择视图

#### 示例：

```
uexCityListView.close();
```

### onItemClick
点击城市之后的回调

#### 参数：
```
city://用户点击的城市
```

#### 示例：

```
uexCityListView.onItemClick = function(result){
   alert(result);
}
```
