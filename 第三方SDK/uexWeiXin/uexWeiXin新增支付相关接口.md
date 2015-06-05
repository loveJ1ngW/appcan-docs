# uexWeiXin
   新增接口

## 方法：
### getPrepayId 生成预支付订单
### startPay 支付

## 回调方法：
### cbGetPrepayId 生成预支付订单的回调接口
### cbStartPay 支付结果的回调方法

### getPrepayId
  生成预支付订单
```
uexWeiXin.getPrepayId(json)
```
### 参数：
参数说明及生成办法详见微信开放平台文档 [统一下单接口参数说明](http://pay.weixin.qq.com/wiki/doc/api/app.php?chapter=9_1) 中的“请求参数”
```
var json = {
    appid:,//(必选) 微信分配的AppID
    mch_id:,//(必选) 微信支付分配的商户号
    device_info:,//(可选)
    nonce_str:,//(必选) 随机字符串，不长于32位。
    body:,//(必选) 终端设备号(门店号或收银设备ID)
    detail:,//(可选) 商品名称明细列表
    attach:,//(可选) 附加数据，在查询API和支付通知中原样返回，该字段主要用于商户携带订单的自定义数据
    out_trade_no://(必选) 商户系统内部的订单号,32个字符内、可包含字母
    fee_type:,//(可选) 符合ISO 4217标准的三位字母代码，默认人民币：CNY
    total_fee:,//(必选) 订单总金额，只能为整数
    spbill_create_ip:,//(必选) 用户端ip
    time_start:,//(可选) 订单生成时间
    time_expire:,//(可选) 订单失效时间
    goods_tag:,//(可选) 商品标记，代金券或立减优惠功能的参数
    notify_url:,//(必选) 接收微信支付异步通知回调地址
    trade_type:,//(必选) 交易类型，此处为固定值"APP"
    product_id:,//(可选) 商品ID
    openid:,//(可选) 用户标识
    sign://(必选) 签名
}
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.1.29+
iOS 3.0.14+
```
### 示例：

```
    var param1 = {
        appid:"wx5h8hdi9o2hs6gd0c5g",
        mch_id:"1234567890",
        device_info:"013467007045764",
        nonce_str:"weradfdgdvccfexs1",
        body:"appcan pay",
        detail:"detail",
        attach:"attach",
        out_trade_no:"1217752501201406033233356018",
        fee_type:"CNY",
        total_fee:"1",
        spbill_create_ip:"127.0.0.1",
        time_start:"20150503152510",
        time_expire:"20150703152510",
        goods_tag:"WXG",
        notify_url:"http://www.baidu.com/",
        trade_type:"APP",
        product_id:"12235413214070356458058",
        openid:"oUpF8uMuAJO_M2pxb1Q9zNjWeS6o",
        sign:"8FC5935C38628F44B924C838D760E33E"
    };
    var data1 = JSON.stringify(param1);
    uexWeiXin.getPrepayId(data1);
```

### startPay
  支付
```
uexWeiXin.startPay(json)
```
### 参数：
参数说明及生成办法详见微信开放平台文档 [调起支付接口参数说明](http://pay.weixin.qq.com/wiki/doc/api/app.php?chapter=9_12&index=2) 中的“请求参数”
```
var json = {
    appid:,//(必选) 微信分配的AppID
    partnerid:,//(必选) 微信支付分配的商户号
    prepayid:,//(必选) 微信返回的支付交易会话ID,从getPrepayId接口的回调方法中获取
    package:,//(必选) 暂填写固定值Sign=WXPay
    noncestr:,//(必选) 随机字符串
    timestamp:,//(必选) 时间戳
    sign://(必选) 签名
}
```
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.1.29+
iOS 3.0.14+
```
### 示例：

```
    var param1 = {
        appid:"wx5h8hdi9o2hs6gd0c5g",
        partnerid:"1234567890",
        prepayid:"wx201506031538433160984eee0861221810",
        package:"Sign=WXPay",
        noncestr:"weradfdgdvccfexs",
        timestamp:"1412000000",
        sign:"8FC5935C38628F44B924C838D760E33E"
    };
    var data1 = JSON.stringify(param1);
    uexWeiXin.startPay(data1);
```

### cbGetPrepayId
生成预支付订单的回调接口
```
uexWeiXin.cbGetPrepayId(json);
```
### 参数：
  json格式数据，参数详见微信开放平台文档 [统一下单接口参数说明](http://pay.weixin.qq.com/wiki/doc/api/app.php?chapter=9_1) 中的“返回结果”
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.1.29+
iOS 3.0.14+
```
### 示例：
```
    uexWeiXin.cbGetPrepayId = function(data){
        alert(data);
    }
```

### cbStartPay
支付结果的回调方法
```
uexWeiXin.cbStartPay(json);
```
### 参数：
```
var json = {
    errCode:,//状态码。0：成功；-1：错误；-2：用户取消
    errStr://状态说明
}
```
参数说明及生成办法详见微信开放平台文档 [调起支付接口参数说明](http://pay.weixin.qq.com/wiki/doc/api/app.php?chapter=9_12&index=2) 中的“返回结果”
### 平台支持：
```
Android 2.2+
iOS 6.0+
```
### 版本支持：
```
Android 3.1.29+
iOS 3.0.14+
```
### 示例：
```
    uexWeiXin.cbStartPay = function(data){
        alert(data);
    }
```