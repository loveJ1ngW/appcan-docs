# uexChart
   该插件封装几何图表功能，包括饼状图，折线图和柱状图功能。

## 方法：
### openPieChart 打开饼状图
### closePieChart 关闭饼状图
### openLineChart 打开曲线图
### closeLineChart 关闭曲线图
### openBarChart 打开直方图
### closeBarChart 关闭直方图

## 监听方法：
### onValueSelected 图表中元素被点击的监听方法

### openPieChart
  打开饼状图
```
uexChart.openPieChart(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    left:,//(可选) 左间距，默认0
    top:,//(可选) 上间距，默认0
    width:,//(可选) 宽度，默认屏幕宽度
    height:,//(可选) 高度，默认屏幕高度
    bgColor:,//(可选) 背景颜色，默认透明
    showUnit:,//(可选) 是否显示单位，默认false
    unit:,//(可选) 单位
    valueTextColor:,//(可选) 饼状图上值的文本颜色，默认#ffffff
    valueTextSize:,//(可选) 饼状图上值的字体大小，默认13
    desc:,//(可选) 描述
    descTextColor:,//(可选) 描述及图例文本颜色，默认#000000
    descTextSize:,//(可选) 描述及图例字体大小，默认12
    showValue:,//(可选) 是否显示value，默认true
    showLegend:,//(可选) 是否显示图例，默认false
    legendPosition:,//(可选) 图例显示的位置，取值范围：bottom-饼状图下方；right-饼状图右侧，默认bottom
    duration:,//(可选) 显示饼状图动画时间，单位ms，默认1000
    isScrollWithWeb:,//(可选) 是否跟随网页滑动，默认false
    showTitle:,//(可选) 是否显示title，默认true
    showPercent:,//(可选) 是否用百分比代替value,默认true
    showCenter:,//(可选) 是否显示中心圆，默认true
    centerColor:,//(可选) 中心圆颜色，默认透明
    centerTitle:,//(可选) 中心标题
    centerSummary:,//(可选) 中心子标题
    centerRadius:,//(可选) 中心圆半径，默认40
    centerTransRadius:,//(可选) 中心圆半透明部分半径，默认42
    data:[//(必选) 数组
        {
            title:,//(必选) 色块名称
            color:,//(必选) 色块颜色
            value://(必选) 色块值
        }
    ]
}
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：

示例1
```
    var param1 = {
        id:1,
        top:500,
        isScrollWithWeb:true,
        data:[
            {
                title:"title1",
                color:"#c12552",
                value:0.9
            },
            {
                title:"title2",
                color:"#ff6600",
                value:0.5
            },
            {
                title:"title3",
                color:"#f5c700",
                value:0.6
            },
            {
                title:"title4",
                color:"#6a961f",
                value:0.4
            },
            {
                title:"title5",
                color:"#b36435",
                value:0.8
            }
        ]
    };
    var data1 = JSON.stringify(param1);
    uexChart.openPieChart(data1);
```
运行效果：
![](http://i.imgur.com/nof0K4x.png)

示例2
```
    var param2 = {
        id:2,
        left:0,
        top:500,
        width:800,
        height:800,
        bgColor:"#cccccc",
        showUnit:true,
        unit:"cc",
        showCenter:true,
        centerColor:"#00000000",
        centerTitle:"我是标题!",
        centerSummary:"我是子标题",
        centerRadius:55,
        centerTransRadius:57,
        valueTextColor:"#ffffff",
        valueTextSize:15,
        desc:"测试饼状图功能",
        descTextColor:"#000000",
        descTextSize:9,
        showTitle:true,
        showValue:true,
        showPercent:false,
        showLegend:true,
        legendPosition:"bottom",
        duration:800,
        data:[
            {
                title:"title1",
                color:"#c12552",
                value:0.9
            },
            {
                title:"title2",
                color:"#ff6600",
                value:0.5
            },
            {
                title:"title3",
                color:"#f5c700",
                value:0.6
            },
            {
                title:"title4",
                color:"#6a961f",
                value:0.4
            },
            {
                title:"title5",
                color:"#b36435",
                value:0.8
            }
        ]
    };
    var data2 = JSON.stringify(param2);
    uexChart.openPieChart(data2);
```
运行效果：
![](http://i.imgur.com/YBYj6Wc.png)

### closePieChart
  关闭饼状图
```
uexChart.closePieChart(json)
```
### 参数：
```
var json = []//(可选) 饼状图唯一标识符数组，不传时关闭所有饼状图
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
```
示例1
    var params = [1];
    var data = JSON.stringify(params);
    uexChart.closePieChart(data);//关闭唯一标识符为1的饼状图

示例2
    uexChart.closePieChart();//关闭所有饼状图
```

### openLineChart
  打开曲线图
```
uexChart.openLineChart(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    left:,//(可选) 左间距，默认0
    top:,//(可选) 上间距，默认0
    width:,//(可选) 宽度，默认屏幕宽度
    height:,//(可选) 高度，默认屏幕高度
    bgColor:,//(可选) 背景颜色，默认透明
    showUnit:,//(可选) 是否显示单位，默认false
    unit:,//(可选) 单位
    valueTextColor:,//(可选) 曲线图上值的文本颜色，默认#ffffff
    valueTextSize:,//(可选) 曲线图上值的字体大小，默认13
    desc:,//(可选) 描述
    descTextColor:,//(可选) 描述及图例文本颜色，默认#000000
    descTextSize:,//(可选) 描述及图例字体大小，默认12
    showValue:,//(可选) 是否显示value，默认true
    showLegend:,//(可选) 是否显示图例，默认false
    legendPosition:,//(可选) 图例显示的位置，取值范围：bottom-曲线图下方；right-曲线图右侧，默认bottom
    duration:,//(可选) 显示曲线图动画时间，单位ms，默认1000
    isScrollWithWeb:,//(可选) 是否跟随网页滑动，默认false
    lines:[//(必选) 曲线数组
        {
            lineName:,//(必选) 曲线名称
            lineColor:,//(必选) 曲线颜色
            lineWidth:,//(必选) 曲线线宽
            circleColor:,//(必选) 结点圆圈颜色
            circleSize:,//(必选) 结点圆圈大小
            isSolid:,//(可选) 是否是实线，默认true
            data:[//(必选) 数据数组
                {
                    xValue:,//(必选) 横坐标值
                    yValue://(必选) 纵坐标值
                }
            ]
        }
    ]
}
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
示例1
```
    var param = {
        id:1,
        left:500,
        top:500,
        width:600,
        height:600,
        bgColor:"#00000000",
        showUnit:true,
        unit:"cc",
        valueTextColor:"#000000",
        valueTextSize:15,
        desc:"测试折线图功能",
        descTextColor:"#000000",
        descTextSize:12,
        showLegend:true,
        legendPosition:"bottom",
        duration:800,
        lines:[
            {
                lineName:"line1",
                lineColor:"#ff6600",
                lineWidth:2,
                circleColor:"#ff6600",
                circleSize:3,
                isSolid:true,
                data:[
                    {xValue:2001,yValue:5},
                    {xValue:2002,yValue:1},
                    {xValue:2003,yValue:6},
                    {xValue:2004,yValue:4},
                    {xValue:2005,yValue:2},
                    {xValue:2006,yValue:3},
                    {xValue:2007,yValue:8},
                    {xValue:2008,yValue:10},
                    {xValue:2009,yValue:2},
                    {xValue:2010,yValue:6}
                ]
            }
        ]
    };
    var data1 = JSON.stringify(param);
    uexChart.openLineChart(data1);
```
运行效果：
![](http://i.imgur.com/hABh4o5.png)

示例2
```
    var param = {
        id:2,
        left:0,
        top:700,
        width:600,
        height:600,
        bgColor:"#cccccc",
        showUnit:true,
        showValue:false,
        unit:"cc",
        valueTextColor:"#ffffff",
        valueTextSize:15,
        desc:"测试折线图功能",
        descTextColor:"#000000",
        descTextSize:12,
        showLegend:true,
        legendPosition:"right",
        duration:800,
        isScrollWithWeb:true,
        lines:[
                {
                    lineName:"line1",
                    lineColor:"#ff6600",
                    lineWidth:2,
                    circleColor:"#ff6600",
                    circleSize:3,
                    isSolid:true,
                    data:[
                        {xValue:2001,yValue:5},
                        {xValue:2002,yValue:1},
                        {xValue:2003,yValue:6},
                        {xValue:2004,yValue:4},
                        {xValue:2005,yValue:2},
                        {xValue:2006,yValue:3},
                        {xValue:2007,yValue:8},
                        {xValue:2008,yValue:10},
                        {xValue:2009,yValue:2},
                        {xValue:2010,yValue:6}
                    ]
                },
                {
                    lineName:"line2",
                    lineColor:"#6a961f",
                    lineWidth:4,
                    circleColor:"#6a961f",
                    circleSize:4,
                    isSolid:false,
                    data:[
                        {xValue:2001,yValue:10},
                        {xValue:2002,yValue:3},
                        {xValue:2003,yValue:3},
                        {xValue:2004,yValue:2},
                        {xValue:2005,yValue:8},
                        {xValue:2006,yValue:2},
                        {xValue:2007,yValue:5},
                        {xValue:2008,yValue:2},
                        {xValue:2009,yValue:5},
                        {xValue:2010,yValue:4}
                    ]
                }
        ]
    };
    var data1 = JSON.stringify(param);
    uexChart.openLineChart(data1);
```
运行效果：
![](http://i.imgur.com/dq0gml0.png)

### closeLineChart
  关闭曲线图
```
uexChart.closeLineChart(json)
```
### 参数：
```
var json = []//(可选) 曲线图唯一标识符数组，不传时关闭所有曲线图
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
```
示例1
    var params = [1];
    var data = JSON.stringify(params);
    uexChart.closeLineChart(data);//关闭唯一标识符为1的曲线图

示例2
    uexChart.closeLineChart();//关闭所有曲线图
```

### openBarChart
  打开直方图
```
uexChart.openBarChart(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    left:,//(可选) 左间距，默认0
    top:,//(可选) 上间距，默认0
    width:,//(可选) 宽度，默认屏幕宽度
    height:,//(可选) 高度，默认屏幕高度
    bgColor:,//(可选) 背景颜色，默认透明
    showUnit:,//(可选) 是否显示单位，默认false
    unit:,//(可选) 单位
    valueTextColor:,//(可选) 直方图上值的文本颜色，默认#ffffff
    valueTextSize:,//(可选) 直方图上值的字体大小，默认13
    desc:,//(可选) 描述
    descTextColor:,//(可选) 描述及图例文本颜色，默认#000000
    descTextSize:,//(可选) 描述及图例字体大小，默认12
    showValue:,//(可选) 是否显示value，默认true
    showLegend:,//(可选) 是否显示图例，默认false
    legendPosition:,//(可选) 图例显示的位置，取值范围：bottom-直方图下方；right-直方图右侧，默认bottom
    duration:,//(可选) 显示直方图动画时间，单位ms，默认1000
    isScrollWithWeb:,//(可选) 是否跟随网页滑动，默认false
    bars:[//直方数组
        {
            barName:,//(必选) 直方名称
            barColor:,//(必选) 直方颜色
            data:[//(必选) 数据数组
                {
                    xValue:,//(必选) 横坐标值
                    yValue://(必选) 纵坐标值
                }
            ]
        }
    ]
}
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
示例1
```
    var param = {
        id:1,
        left:0,
        top:500,
        width:600,
        height:600,
        bgColor:"#00000000",
        showUnit:true,
        unit:"cc",
        valueTextColor:"#000000",
        valueTextSize:15,
        duration:1800,
        bars:[
            {
                barName:"bar1",
                barColor:"#c12552",
                data:[
                    {xValue:2001,yValue:5},
                    {xValue:2002,yValue:1},
                    {xValue:2003,yValue:6},
                    {xValue:2004,yValue:4},
                    {xValue:2005,yValue:2},
                    {xValue:2006,yValue:3}
                ]
            }
        ]
    };
    var data1 = JSON.stringify(param);
    uexChart.openBarChart(data1);
```
运行效果：
![](http://i.imgur.com/DwdLmjK.png)

示例2
```
    var param = {
        id:2,
        left:500,
        top:700,
        width:600,
        height:600,
        bgColor:"#cccccc",
        showUnit:true,
        unit:"cc",
        valueTextColor:"#ffffff",
        valueTextSize:15,
        showValue:false,
        desc:"测试柱状图功能",
        descTextColor:"#000000",
        descTextSize:12,
        showLegend:true,
        legendPosition:"right",
        duration:1800,
        isScrollWithWeb:true,
        bars:[
            {
                barName:"bar1",
                barColor:"#c12552",
                data:[
                    {xValue:2001,yValue:5},
                    {xValue:2002,yValue:1},
                    {xValue:2003,yValue:6},
                    {xValue:2004,yValue:4},
                    {xValue:2005,yValue:2},
                    {xValue:2006,yValue:3}
                ]
            },
            {
                barName:"bar2",
                barColor:"#ff6600",
                data:[
                    {xValue:2001,yValue:10},
                    {xValue:2002,yValue:3},
                    {xValue:2003,yValue:3},
                    {xValue:2004,yValue:2},
                    {xValue:2005,yValue:8},
                    {xValue:2006,yValue:2}
                ]
            }
        ]
    };
    var data1 = JSON.stringify(param);
    uexChart.openBarChart(data1);
```
运行效果：
![](http://i.imgur.com/rDEC5mO.png)

### closeBarChart
  关闭直方图
```
uexChart.closeBarChart(json)
```
### 参数：
```
var json = []//(可选) 直方图唯一标识符数组，不传时关闭所有直方图
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
```
示例1
    var params = [1];
    var data = JSON.stringify(params);
    uexChart.closeBarChart(data);//关闭唯一标识符为1的直方图

示例2
    uexChart.closeBarChart();//关闭所有直方图
```

### onValueSelected
图表中元素被点击的监听方法
```
uexChart.onValueSelected(json);
```
### 参数：
```
var json = {
    value://被点击的元素对应的值
}
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.0+
iOS 3.0.0+
```
### 示例：
```
    uexChart.onValueSelected = function(data){
        alert(data);
    }
```