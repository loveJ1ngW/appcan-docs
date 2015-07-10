# uexGaodeMap
  封装高德地图相关功能，包括放大缩小、移动和旋转等基本操作；标注；圆形、矩形和多边形覆盖物；定位、搜索、地理编码等功能。

## [changelog](#changelog) 更新日志
## [appendix](#appendix) 附录

## 方法：
### [open](#open) 打开地图
### [close](#close) 关闭地图
### [setMapType](#setmaptype) 设置地图类型
### [setTrafficEnabled](#settrafficenabled) 开启或关闭实时路况
### [setCenter](#setcenter) 设置地图中心点
### [setZoomLevel](#setzoomlevel) 设置地图缩放级别
### [zoomIn](#zoomin) 放大一个地图级别
### [zoomOut](#zoomout) 缩小一个地图级别
### [rotate](#rotate) 旋转地图
### [overlook](#overlook) 倾斜地图
### [setZoomEnable](#setzoomenable) 开启或关闭手势缩放
### [setRotateEnable](#setrotateenable) 开启或关闭手势旋转及手势倾斜
### [setCompassEnable](#setcompassenable) 开启或关闭指南针
### [setScrollEnable](#setscrollenable) 开启或关闭手势移动
### [addMarkersOverlay](#addmarkersoverlay) 添加标注
### [setMarkerOverlay](#setmarkeroverlay) 修改标注
### [addPolylineOverlay](#addpolylineoverlay) 添加折线覆盖物
### [removeOverlays](#removeoverlays) 移除覆盖物
### [addArcOverlay](#addarcoverlay) 添加弧形覆盖物
### [addCircleOverlay](#addcircleoverlay) 添加圆形覆盖物
### [addPolygonOverlay](#addpolygonoverlay) 添加多边形覆盖物
### [addGroundOverlay](#addgroundoverlay) 添加图片覆盖物
### [removeMarkersOverlays](#removemarkersoverlays) 移除标注
### [poiSearch](#poisearch) 兴趣点搜索
### [geocode](#geocode) 地理编码
### [reverseGeocode](#reversegeocode) 反地理编码
### [getCurrentLocation](#getcurrentlocation) 获取当前位置
### [startLocation](#startlocation) 开始连续定位
### [stopLocation](#stoplocation) 停止连续定位
### [setMyLocationEnable](#setmylocationenable) 显示或隐藏我的位置
### [setUserTrackingMode](#setusertrackingmode) 设置连续定位模式
### [setScaleVisible](#setscalevisible) 设置地图是否显示比例尺
### [setMyLocationButtonVisible](#setmylocationbuttonvisible) 设置是否显示回到我的位置按钮
### [setZoomVisible](#setzoomvisible) 设置是否显示放大缩小按钮
### [clear](#clear) 清除地图上所有的标注和覆盖物

## 回调方法：
### [cbGetCurrentLocation](#cbgetcurrentlocation) 获取当前位置的回调方法
### [cbGeocode](#cbgeocode) 地理编码的回调方法
### [cbReverseGeocode](#cbreversegeocode) 反地理编码的回调方法
### [cbPoiSearch](#cbpoisearch) 兴趣点搜索的回调方法

## 监听方法：
### [onMapLoadedListener](#onmaploadedlistener) 地图加载完成的监听方法
### [onMarkerClickListener](#onmarkerclicklistener) 点击标注的监听方法
### [onMarkerBubbleClickListener](#onmarkerbubbleclicklistener) 点击气泡的监听方法
### [onReceiveLocation](#onreceivelocation) 位置变化的监听方法
### [onMapClickListener](#onmapclickListener) 点击地图的监听方法
### [onMapLongClickListener](#onmaplongclicklistener) 长按地图的监听方法


> [离线地图](#离线地图)

### [download](#download) 开始下载
### [cbDownload](#cbdownload) 开始下载的回调方法
### [pause](#pause) 暂停下载
### [restart](#restart) 继续下载
### [getAvailableCityList](#getavailablecitylist) 获取可下载离线地图的城市列表
### [cbGetAvailableCityList](#cbgetavailablecitylist) 获取可下载离线地图的城市列表的回调方法
### [getAvailableProvinceList](#getavailableprovincelist) 获取可下载离线地图的省和城市列表
### [cbGetAvailableProvinceList](#cbgetavailableprovincelist) 获取可下载离线地图的省和城市列表的回调方法
### [getDownloadList](#getdownloadlist) 获取已下载列表
### [cbGetDownloadList](#cbgetdownloadlist) 获取已下载列表的回调方法
### [getDownloadingList](#getdownloadinglist) 获取正在下载列表
### [cbGetDownloadingList](#cbgetdownloadinglist) 获取正在下载列表的回调方法
### [isUpdate](#isupdate) 已下载的离线地图数据是否需要更新
### [cbIsUpdate](#cbisupdate) 已下载的离线地图数据是否需要更新的回调方法
### [delete](#delete) 删除已下载或者正在下载数据
### [cbDelete](#cbdelete) 删除已下载或者正在下载数据的回调方法

### [onDownload](#ondownload) 下载监听方法


### open
  打开地图
```
uexGaodeMap.open(json)
```
### 参数：
```
var json = {
    left:,//(可选) 左间距，默认0
    top:,//(可选) 上间距，默认0
    width:,//(可选) 地图宽度
    height:,//(可选) 地图高度
    longitude:,//(可选) 中心点经度
    latitude://(可选) 中心点纬度
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
    var params = {
        left:0,
        top:0,
        width:800,
        height:800,
        longitude:114.402815,
        latitude:30.475798
    };
    var data = JSON.stringify(params);
    uexGaodeMap.open(data);
```

### close
  关闭地图
```
uexGaodeMap.close()
```
### 参数：
```
无
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
    uexGaodeMap.close();
```

### setMapType
  设置地图类型
```
uexGaodeMap.setMapType(json)
```
### 参数：
```
var json = {
    type://（必选）地图类型，1-标准地图，2-卫星地图，3-夜景地图
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setMapType(data);
```

### setTrafficEnabled
  开启或关闭实时路况
```
uexGaodeMap.setTrafficEnabled(json)
```
### 参数：
```
var json = {
    type://（必选） 0-关闭，1-开启
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setTrafficEnabled(data);
```

### setCenter
  设置地图中心点
```
uexGaodeMap.setCenter(json)
```
### 参数：
```
var json = {
    longitude:,//（必选）中心点经度
    latitude://（必选）中心点纬度
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
    var params = {
        longitude:114.402815,
        latitude:30.475798
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setCenter(data);
```

### setZoomLevel
  设置地图缩放级别
```
uexGaodeMap.setZoomLevel(json)
```
### 参数：
```
var json = {
    level://(必选)级别，范围(3,20)
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
    var params = {
        level:15
        };
    var data = JSON.stringify(params);
    uexGaodeMap.setZoomLevel(data);
```

### zoomIn
  放大一个地图级别
```
uexGaodeMap.zoomIn()
```
### 参数：
```
无
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
    uexGaodeMap.zoomIn()；
```

### zoomOut
  缩小一个地图级别
```
uexGaodeMap.zoomOut()
```
### 参数：
```
无
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
    uexGaodeMap.zoomOut();
```

### rotate
  旋转地图
```
uexGaodeMap.rotate(json)
```
### 参数：
```
var json = {
    angle://（必选）旋转角度，正北方向到地图方向逆时针旋转的角度，范围(0,360)。
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
    var params = {
        angle:90
    };
    var data = JSON.stringify(params);
    uexGaodeMap.rotate(data);
```

### overlook
  倾斜地图
```
uexGaodeMap.overlook(json)
```
### 参数：
```
var json = {
    angle://(必选)地图倾斜度，范围(0,45)。
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
    var params = {
        angle:23
    };
    var data = JSON.stringify(params);
    uexGaodeMap.overlook(data);
```

### setZoomEnable
  开启或关闭手势缩放
```
uexGaodeMap.setZoomEnable(json)
```
### 参数：
```
var json = {
    type://（必选） 0-关闭，1-开启
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setZoomEnable(data);
```

### setRotateEnable
  开启或关闭手势旋转及手势倾斜
```
uexGaodeMap.setRotateEnable(json)
```
### 参数：
```
var json = {
    type://（必选） 0-关闭，1-开启
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setRotateEnable(data);
```

### setCompassEnable
  开启或关闭指南针
```
uexGaodeMap.setCompassEnable(json)
```
### 参数：
```
var json = {
    type://（必选） 0-关闭，1-开启
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setCompassEnable(data);
```

### setScrollEnable
  开启或关闭手势移动
```
uexGaodeMap.setScrollEnable(json)
```
### 参数：
```
var json = {
    type://（必选） 0-关闭，1-开启
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
    var params = {
        type:1
    };
    var data = JSON.stringify(params);
    uexGaodeMap.setScrollEnable(data);
```

### addMarkersOverlay
  添加标注
```
uexGaodeMap.addMarkersOverlay(json)
```
### 参数：
```
var json = [
    {
        id:,//(必选) 唯一标识符
        longitude:,//(必选) 标注经度
        latitude:,//(必选) 标注纬度
        icon:,//(可选) 标注图标
        bubble:{//(可选) 标注气泡
                title:,//(必选) 气泡标题
                subTitle://(可选) 气泡子标题
        }
    }
]
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
    var param = [
        {
            id:10001,
            longitude:114.402965,
            latitude:30.475845,
            icon:"http://www.iconpng.com/png/mapmarkers/marker_inside_azure.png",
            bubble:{
                title:"title1",
                subTitle:"subTitle1"
            }
        },
        {
            id:10002,
            longitude:114.409308,
            latitude:30.476229,
            bubble:{
                title:"title2",
                subTitle:"subTitle2"
            }
        }
    ];
    var data = JSON.stringify(param);
    uexGaodeMap.addMarkersOverlay(data);
```

### setMarkerOverlay
  修改标注
```
uexGaodeMap.setMarkerOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    longitude:,//(可选) 标注经度
    latitude:,//(可选) 标注纬度
    icon:,//(可选) 标注图标
    bubble:{//(可选) 标注气泡
        title:,//(必选) 气泡标题
        subTitle://(可选) 气泡子标题
    }
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
    var makerInfo = {
        id:10002,
        bubble:{
            title:"change-title",
            subTitle:"change-subTitle"
        }
    };
    var data = JSON.stringify(makerInfo);
    uexGaodeMap.setMarkerOverlay(data);
```

### addPolylineOverlay
  添加折线覆盖物
```
uexGaodeMap.addPolylineOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    fillColor:,//(可选) 折线颜色
    lineWidth:,//(可选) 折线宽
    property:[//(必选) 数据
        {
            longitude:,//(必选) 连接点经度
            latitude://(必选) 连接点纬度
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
```
    var jsonstr = {
        id:"151",
        fillColor:"#f00",
        lineWidth:"10.0",
        property:[
            {
                longitude:"114.402965",
                latitude:"30.475845"
            },
            {
                longitude:"114.502965",
                latitude:"30.475845"
            },
            {
                longitude:"114.402965",
                latitude:"30.375845"
            }
        ]
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.addPolylineOverlay(data);
```

### removeOverlays
  移除覆盖物
```
uexGaodeMap.removeOverlays(json)
```
### 参数：
```
var json = []////(可选)覆盖物唯一标识符数组，不传时移除所有覆盖物。
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.2+
iOS 3.0.1+
```
### 示例：
```
    var idarr = ["151"];
    var data = JSON.stringify(idarr);
    uexGaodeMap.removeOverlays(data);
```

### addArcOverlay
  添加弧形覆盖物
```
uexGaodeMap.addArcOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    strokeColor:,//(可选) 颜色
    lineWidth:,//(可选) 线宽
    start:{//(必选) 起点数据
        longitude:,//(必选) 经度
        latitude://(必选) 纬度
    },
    center:{//(必选) 中间点数据
        longitude:,//(必选) 经度
        latitude://(必选) 纬度
    },
    end:{//(必选) 终点数据
        longitude:,//(必选) 经度
        latitude://(必选) 纬度
    }
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.0+
```
### 示例：
```
    var jsonstr = {
        id:"152",
        strokeColor:"#f00",
        lineWidth:"12.0",
        start:{
            longitude:"114.402965",
            latitude:"30.475845"
        },
        center:{
            longitude:"114.502965",
            latitude:"30.475845"
        },
        end:{
            longitude:"114.402965",
            latitude:"30.375845"
        }
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.addArcOverlay(data);
```

### addCircleOverlay
  添加圆形覆盖物
```
uexGaodeMap.addCircleOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    longitude:,//(必选) 圆心经度
    latitude:,//(必选) 圆心纬度
    radius:,//(必选) 半径
    fillColor:,//(可选) 填充颜色
    strokeColor:,//(可选) 边框颜色
    lineWidth://(可选) 边框线宽
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
    var jsonstr = {
        id:"153",
        longitude:"114.402965",
        latitude:"30.375845",
        radius:"1000",
        fillColor:"#4169E1",
        strokeColor:"#990033",
        lineWidth:"4"
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.addCircleOverlay(data);
```

### addPolygonOverlay
  添加多边形覆盖物
```
uexGaodeMap.addPolygonOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    fillColor:,//(可选) 填充颜色
    strokeColor:,//(可选) 边框颜色
    lineWidth:,//(可选) 边框线宽
    property:[//(必选) 数据
        {
            longitude:,//(必选) 顶点经度
            latitude://(必选) 顶点纬度
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
```
    var jsonstr = {
        id:"154",
        fillColor:"#990033",
        strokeColor:"#990033",
        lineWidth:"2.0",
        property:[
            {
                longitude:"114.402965",
                latitude:"30.375845"
            },
            {
                longitude:"115.402965",
                latitude:"30.375845"
            },
            {
                longitude:"114.402965",
                latitude:"31.375845"
            },
            {
                longitude:"114.402965",
                latitude:"30.375845"
            }
        ]
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.addPolygonOverlay(data);
```

### addGroundOverlay
  添加图片覆盖物
```
uexGaodeMap.addGroundOverlay(json)
```
### 参数：
```
var json = {
    id:,//(必选) 唯一标识符
    imageUrl:,//(必选) 图片地址
    transparency:,//(可选) 图片透明度（仅Android支持该参数）
    property:[//(必选) 数据，数组长度为2，第一个元素表示西南角的经纬度，第二个表示东北角的经纬度；
        {
            longitude:,//(必选) 顶点经度
            latitude://(必选) 顶点纬度
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
```
    示例1：
    var jsonstr = {
        id:"155",
        imageUrl:"http://img0.bdstatic.com/img/image/9baf75d938553886ce515def29441ed31409109131.jpg",
        transparency:"0.5",
        property:[
            {
                longitude:"114.402165",
                latitude:"30.374845"
            },
            {
                longitude:"114.502165",
                latitude:"30.474845"
            }
        ]
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.addGroundOverlay(data);
```

### removeMarkersOverlays
  移除标注
```
uexGaodeMap.removeMarkersOverlays(json)
```
### 参数：
```
var json = []//(可选)标注唯一标识符数组，不传时移除所有标注。
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.2+
iOS 3.0.1+
```
### 示例：
```
    var params = ['10001'];
    var data = JSON.stringify(params);
    uexGaodeMap.removeMarkersOverlays(data);
```

### poiSearch
  兴趣点搜索
```
uexGaodeMap.poiSearch(json)
```
### 参数：
```
var json = {
    searchKey:,//(可选) 搜索关键字
    poiTypeSet:,//(可选) Poi兴趣点，searchKey和poiTypeSet必须至少包含其中的一个
    city:,//(可选) 城市，不传时表示全国范围内（iOS无效，默认全国范围内搜索）
    pageNum:,//(可选) 搜索结果页索引，默认为0
    searchBound://(可选) 区域搜索，city和searchBound必须至少包含其中的一个。以下的三个类别有且只有一种。
    {
        type:"circle",//(必选) 圆形区域搜索
        dataInfo:{
            center:{//(必选) 圆心
                longitude:,//(必选) 经度
                latitude://(必选) 纬度
            },
            radius:,//(必选) 半径
            isDistanceSort://(可选) 是否按距离由小到大排序，默认true
        }
    }
    {
        type:"rectangle",//(必选) 矩形区域搜索
        dataInfo:{
            lowerLeft:{//(必选) 左下角
                longitude:,//(必选) 经度
                latitude://(必选) 纬度
            },
            upperRight:{//(必选) 右上角
                longitude:,//(必选) 经度
                latitude://(必选) 纬度
            }
        }
	}
    {
        type:"polygon",//(必选) 多边形区域搜索
        dataInfo:[//(必选) 顶点集合
            {
                longitude:,//(必选) 顶点经度
                latitude://(必选) 顶点纬度
            }
        ]
	}
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
    示例1：
    var jsonstr = {
        city:"武汉",
        searchKey:"加油站"
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.poiSearch(data);

    示例2：
    var jsonstr = {
        city:"武汉",
        poiTypeSet:"加油站",
        searchBound:{
            type:"circle",
            dataInfo:{
                center:{
                    longitude:114.402815,
                    latitude:30.475798
                },
                radius:3000,
                isDistanceSort:true
            }
        }
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.poiSearch(data);

    示例3：
    var jsonstr = {
        poiTypeSet:"加油站",
        searchBound:{
            type:"rectangle",
            dataInfo:{
                lowerLeft:{
                    longitude:114.402815,
                    latitude:30.475798
                },
                upperRight:{
                    longitude:114.513855,
                    latitude:30.586848
                }
            }
        }
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.poiSearch(data);

    示例4：
    var jsonstr = {
        poiTypeSet:"加油站",
        searchBound:{
            type:"polygon",
            dataInfo:[
                {
                    longitude:"114.402965",
                    latitude:"30.375845"
                },
                {
                    longitude:"115.402965",
                    latitude:"30.375845"
                },
                {
                    longitude:"114.402965",
                    latitude:"31.375845"
                },
                {
                    longitude:"114.402965",
                    latitude:"30.375845"
                }
            ]
        }
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.poiSearch(data);
```

### geocode
  地理编码，通过地址获得经纬度信息
```
uexGaodeMap.geocode(json)
```
### 参数：
```
var json = {
    city:,//(必选) 城市，不传时表示全国范围内
    address://(必选) 具体地址
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
    var jsonstr = {
        city:"武汉",
        address:"光谷软件园C6栋"
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.geocode(data);
```

### reverseGeocode
  反地理编码，将经纬度转换为地址信息
```
uexGaodeMap.reverseGeocode(json)
```
### 参数：
```
var json = {
    longitude:,//经度
    latitude://纬度
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
    var jsonstr = {
        longitude:114.402815,
        latitude:30.475798
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.reverseGeocode(data);
```

### getCurrentLocation
  打开地图
```
uexGaodeMap.getCurrentLocation()
```
### 参数：
```
无
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
    uexGaodeMap.getCurrentLocation();
```

### startLocation
  开始连续定位
```
uexGaodeMap.startLocation(json)
```
### 参数：
```
var json = {（仅Android支持参数）
    minTime:,//(可选) 位置变化通知时间，单位：毫秒， 默认2000
    minDistance://(可选) 位置变化通知距离，单位：米，默认10
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
    var jsonstr = {
        minTime:3000,
        minDistance:10
    };
    var data = JSON.stringify(jsonstr);
    uexGaodeMap.startLocation(data);
```

### stopLocation
  停止连续定位
```
uexGaodeMap.stopLocation()
```
### 参数：
```
无
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
    uexGaodeMap.stopLocation();
```

### setMyLocationEnable
  显示或隐藏我的位置
```
uexGaodeMap.setMyLocationEnable(json)
```
### 参数：
```
var json = {
    type://（必选） 0-隐藏，1-显示
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
    var params = {
        type:1
    }
    var data = JSON.stringify(params);
    uexGaodeMap.setMyLocationEnable(data);
```

### setUserTrackingMode
  设置连续定位模式
```
uexGaodeMap.setUserTrackingMode(json)
```
### 参数：
```
var json = {
    type://(必选) 模式，1-只在第一次定位移动到地图中心点；
                       2-定位、移动到地图中心点并跟随；
                       3-定位、移动到地图中心点，跟踪并根据方向旋转地图。
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
    var params = {
        type:1
    }
    var data = JSON.stringify(params);
    uexGaodeMap.setUserTrackingMode(data);
```

### setScaleVisible
  设置地图是否显示比例尺
```
uexGaodeMap.setScaleVisible(json)
```
### 参数：
```
var json = {
    visible://(必选) 是否显示，true-显示；false-隐藏。
}
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.2+
iOS 3.0.1+
```
### 示例：
```
    var params = {
        visible:true
    }
    var data = JSON.stringify(params);
    uexGaodeMap.setScaleVisible(data);
```

### setMyLocationButtonVisible
  设置是否显示回到我的位置按钮，注意回到我的位置按钮点击生效的前提条件是开启定位。
```
uexGaodeMap.setMyLocationButtonVisible(json)
```
### 参数：
```
var json = {
    visible://(必选) 是否显示，true-显示；false-隐藏。
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.2+
```
### 示例：
```
    var params = {
        visible:true
    }
    var data = JSON.stringify(params);
    uexGaodeMap.setMyLocationButtonVisible(data);
```

### setZoomVisible
  设置是否显示放大缩小按钮
```
uexGaodeMap.setZoomVisible(json)
```
### 参数：
```
var json = {
    visible://(必选) 是否显示，true-显示；false-隐藏。
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.2+
```
### 示例：
```
    var params = {
        visible:true
    }
    var data = JSON.stringify(params);
    uexGaodeMap.setZoomVisible(data);
```

### clear
  清除地图上所有的标注和覆盖物
```
uexGaodeMap.clear()
```
### 参数：
```
无
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.2+
iOS 3.0.1+
```
### 示例：
```
    uexGaodeMap.clear();
```

### cbGetCurrentLocation
获取当前位置的回调方法
```
uexGaodeMap.cbGetCurrentLocation(json);
```
### 参数：
```
var json = {
    longitude:,//当前位置经度
    latitude:,//当前位置纬度
    timestamp://时间戳
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
    uexGaodeMap.cbGetCurrentLocation = function(json) {
        alert("cbGetCurrentLocation: "+json);
    }
```

### cbGeocode
地理编码的回调方法
```
uexGaodeMap.cbGeocode(json);
```
### 参数：
```
var json = {
    longitude:,//当前位置经度
    latitude://当前位置纬度
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
    uexGaodeMap.cbGeocode = function(json) {
        alert("cbGeocode: "+json);
    }
```

### cbReverseGeocode
反地理编码的回调方法
```
uexGaodeMap.cbReverseGeocode(json);
```
### 参数：
```
var json = {
    address://具体地址
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
    uexGaodeMap.cbReverseGeocode = function(json) {
        alert("cbReverseGeocode: "+json);
    }
```

### cbPoiSearch
兴趣点搜索的回调方法
```
uexGaodeMap.cbPoiSearch(json);
```
### 参数：
```
var json = {
    errorCode: 0， //错误码，0-成功，非0-失败
    data: [//搜索结果集合
        {
            address:,//地址详情
            cityCode:,//城市编码
            cityName:,//城市名称
            website:,//网址
            email:,//邮箱
            id:,//poiId
            point: {//位置坐标
                latitude:,//经度
                longitude://纬度
            },
            postcode:,//邮编
            provinceCode:,//省/自治区/直辖市/特别行政区编码
            provinceName:,//省/自治区/直辖市/特别行政区名称
            tel:,//电话号码
            title:,//名称
            typeDes:,//类型描述
            distance://距离中心点的距离
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
```
    uexGaodeMap.cbPoiSearch = function(json) {
        alert("cbPoiSearch: "+json);
    }
```

### onMapLoadedListener
地图加载完成的监听方法
```
uexGaodeMap.onMapLoadedListener();
```
### 参数：
```
无
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
    uexGaodeMap.onMapLoadedListener = function() {
        alert("onMapLoadedListener");
    }
```

### onMarkerClickListener
点击标注的监听方法
```
uexGaodeMap.onMarkerClickListener(json);
```
### 参数：
```
var json = {
    id://被点击的标注的id
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
    uexGaodeMap.onMarkerClickListener = function(json) {
        alert("onMarkerClickListener: "+json);
    }
```

### onMarkerBubbleClickListener
点击气泡的监听方法
```
uexGaodeMap.onMarkerBubbleClickListener(json);
```
### 参数：
```
var json = {
    id://被点击的气泡所属标注的id
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.0+
```
### 示例：
```
    uexGaodeMap.onMarkerBubbleClickListener = function(json) {
        alert("onMarkerBubbleClickListener: "+json);
    }
```

### onReceiveLocation
位置变化的监听方法
```
uexGaodeMap.onReceiveLocation(json);
```
### 参数：
```
var json = {
    longitude:,//当前位置经度
    latitude:,//当前位置纬度
    timestamp://时间戳
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
    uexGaodeMap.onReceiveLocation = function(json) {
        alert("onReceiveLocation: "+json);
    }
```

### onMapClickListener
点击地图的监听方法
```
uexGaodeMap.onMapClickListener(json);
```
### 参数：
```
var json = {
    longitude:,//被点击的位置经度
    latitude://被点击的位置纬度
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.0+
```
### 示例：
```
    uexGaodeMap.onMapClickListener = function(json) {
        alert("onMapClickListener: "+json);
    }
```

### onMapLongClickListener
长按地图的监听方法
```
uexGaodeMap.onMapLongClickListener(json);
```
### 参数：
```
var json = {
    longitude:,//长按的位置经度
    latitude://长按的位置纬度
}
```
### 平台支持：
```
  Android 2.2+
```
### 版本支持：
```
Android 3.0.0+
```
### 示例：
```
    uexGaodeMap.onMapLongClickListener = function(json) {
        alert("onMapLongClickListener: "+json);
    }
```

### 离线地图

### download
  开始下载，当前如果有正在下载的任务，添加到正在下载列表中。
```
uexGaodeMap.download(json)
```
### 参数：
```
var json = [//数组
    {//city或province必须传一个，都传时只有city有效
        city:,//(可选) 城市名称
        province://(可选) 省或直辖市名称
    }
]
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    var params = [
        {
            city:'武汉'
        },
        {
            province:'广东省'
        }
    ];
    var data = JSON.stringify(params);
    uexGaodeMap.download(data);
```

### cbDownload
  开始下载的回调方法
```
uexGaodeMap.cbDownload(json)
```
### 参数：
```
var json = {
    name:,//(必选) 省或城市名称
    errorCode:,//(必选) 状态码，0-加入列表成功，非0-失败。
    errorStr://(可选) 错误描述，errorCode非0时，该值有效。
}
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbDownload = function(json) {
        alert("cbDownload: "+json);
    }
```

### onDownload
  下载监听方法
```
uexGaodeMap.onDownload(json)
```
### 参数：
```
var json = {
    name:,//(必选) 省或城市名称
    completeCode:,//(必选) 进度百分比。
    status://(可选) 下载状态，具体请参考附录onDownload Status。
}
```
注：status下载状态参见附录[Download Status](#download-status)

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.onDownload = function(json) {
        var data = JSON.parse(info);
        if(data.status == 0){
            uexWindow.toast(1,5,data.name + " 正在下载...",0);
        }
        if(data.status == 1){
            uexWindow.toast(1,5,data.name + " 正在解压...",0);
        }
        if(data.status == 4){
            uexWindow.closeToast();
            alert(data.name + " 离线地图下载成功！");
        }
        if(data.status == 3){
            uexWindow.toast(0,5,data.name + " 暂停下载...",2000);
        }
        if(data.status == -1){
            uexWindow.closeToast();
            alert(data.name + " 下载失败！");
        }
    }
```

### pause
  暂停下载
```
uexGaodeMap.pause(json)
```
### 参数：
```
var json = []//(必传) 省或城市名称数组
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    var params = ["武汉","广东省"];
    var data = JSON.stringify(params);
    uexGaodeMap.pause(data);
```

### restart
  继续下载
```
uexGaodeMap.restart(json)
```
### 参数：
```
var json = []//(必传) 省或城市名称数组
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    var params = ["武汉","广东省"];
    var data = JSON.stringify(params);
    uexGaodeMap.restart(data);
```

### getAvailableCityList
  获取可下载离线地图的城市列表
```
uexGaodeMap.getAvailableCityList()
```
### 参数：
```
无
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.getAvailableCityList();
```

### cbGetAvailableCityList
  获取可下载离线地图的城市列表的回调方法
```
uexGaodeMap.cbGetAvailableCityList(json)
```
### 参数：
```
var json = [
    {
        city:,//(必选) 城市名称
        url:,//(必选) 下载地址
        version:,//(必选) 版本号
        size:,//(必选) 包大小，单位字节
        completeCode:,//(必选) 进度百分比
        status://(可选) 下载状态
    }
]
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbGetAvailableCityList = function(json) {
        alert("cbGetAvailableCityList: "+json);
    }
```

### getAvailableProvinceList
  获取可下载离线地图的省和城市列表
```
uexGaodeMap.getAvailableProvinceList()
```
### 参数：
```
无
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.getAvailableProvinceList();
```

### cbGetAvailableProvinceList
  获取可下载离线地图的省和城市列表的回调方法
```
uexGaodeMap.cbGetAvailableProvinceList(json)
```
### 参数：
```
var json = [
    {
        cityList:[//(必选) 省包含的城市列表
            {
                city:,//(必选) 城市名称
                url:,//(必选) 下载地址
                version:,//(必选) 版本号
                size:,//(必选) 包大小，单位字节
                completeCode:,//(必选) 进度百分比
                status://(可选) 下载状态
            }
        ],
        province:,//(必选) 省或直辖市名称
        url:,//(必选) 下载地址
        version:,//(必选) 版本号
        size:,//(必选) 包大小，单位字节
        completeCode:,//(必选) 进度百分比
        status://(可选) 下载状态
    }
]
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbGetAvailableProvinceList = function(json) {
        alert("cbGetAvailableProvinceList: "+json);
    }
```

### getDownloadList
  获取已下载列表
```
uexGaodeMap.getDownloadList(json)
```
### 参数：
```
无
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.getDownloadList();
```

### cbGetDownloadList
  获取已下载列表的回调方法
```
uexGaodeMap.cbGetDownloadList(json)
```
### 参数：
```
var json = [
    {
        name:,//(必选) 省或城市名称
        type:,//(必选) 类型，1-城市，2-省
        url:,//(必选) 下载地址
        version:,//(必选) 版本号
        size:,//(必选) 包大小，单位字节
        completeCode:,//(必选) 进度百分比
        status://(可选) 下载状态
    }
]
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbGetDownloadList = function(json) {
        alert("cbGetDownloadList: "+json);
    }
```

### getDownloadingList
  获取正在下载列表
```
uexGaodeMap.getDownloadingList(json)
```
### 参数：
```
无
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.getDownloadingList();
```

### cbGetDownloadingList
  获取正在下载列表的回调方法
```
uexGaodeMap.cbGetDownloadingList(json)
```
### 参数：
```
var json = [
    {
        name:,//(必选) 省或城市名称
        type:,//(必选) 类型，1-城市，2-省
        url:,//(必选) 下载地址
        version:,//(必选) 版本号
        size:,//(必选) 包大小，单位字节
        completeCode:,//(必选) 进度百分比
        status://(可选) 下载状态
    }
]
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbGetDownloadingList = function(json) {
        alert("cbGetDownloadingList: "+json);
    }
```

### isUpdate
  已下载的离线地图数据是否需要更新
```
uexGaodeMap.isUpdate(json)
```
### 参数：
```
var json = {//city或province必须传一个，都传时只有city有效
    city:,//(可选) 城市名称
    province://(可选) 省或直辖市名称
}
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    var params = [
        {
            city:'武汉'
        }
    ];
    var data = JSON.stringify(params);
    uexGaodeMap.isUpdate(data);
```

### cbIsUpdate
  已下载的离线地图数据是否需要更新的回调方法
```
uexGaodeMap.cbIsUpdate(json)
```
### 参数：
```
var json = {
    name:,//(必选) 省或城市名称
    result://(可选) 是否有更新，0-有更新，1-没有更新
}
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbIsUpdate = function(json) {
        alert("cbIsUpdate: "+json);
    }
```

### delete
  删除已下载或者正在下载数据
```
uexGaodeMap.delete(json)
```
### 参数：
```
var json = []//(必传) 省或城市名称数组
```
### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    var params = ["武汉"];
    var data = JSON.stringify(params);
    uexGaodeMap.delete(data);
```

### cbDelete
  删除已下载或者正在下载数据的回调方法
```
uexGaodeMap.cbDelete(json)
```
### 参数：
```
var json = {
    name:,//(必选) 省或城市名称
    errorCode:,//(必选) 状态码，0-删除成功，非0-失败。
    errorStr://(可选) 错误描述，errorCode非0时，该值有效。
}
```

### 平台支持：
```
  Android 2.2+
  iOS 6.0+
```
### 版本支持：
```
Android 3.0.3+
iOS 3.0.2+
```
### 示例：
```
    uexGaodeMap.cbDelete = function(json) {
        alert("cbDelete: "+json);
    }
```


### changelog
2015-06-30
- 新增**API**： `removeMarkersOverlays`、`removeOverlays`、`setScaleVisible`、`setMyLocationButtonVisible`、`setZoomVisible`;
- 废弃**API**： `removeMarkersOverlay`、`removeOverlay`;
- 以上**API** iOS 3.0.1版本，Android 3.0.2版本开始支持。

2015-07-02
- 新增**API**：`clear` 清除地图上所有标注和覆盖物。
- iOS3.0.1版本，Android3.0.2版本开始支持。

2015-07-10
- 新增**API**：[离线地图](#离线地图)相关接口
- iOS3.0.2版本，Android3.0.3版本开始支持。

### appendix
#### Download Status
| 状态码 | 描述 | 英文描述 |
| ----- | ---- | ------- |
|-1 | 下载失败 | ERROR |
| 0 | 正在下载 | LOADING |
| 1 | 正在解压 | UNZIP |
| 2 | 等待下载 | WAITING |
| 3 | 暂停下载 | PAUSE |
| 4 | 下载成功 | SUCCESS |
| 5 | 停止下载 | STOP |
| 6 | 检查更新状态 | CHECKUPDATES |

