# 广告主应用激活回传接口
## 一、使用场景
当广告主和掌游天下约定按照应用的下载激活进行结算的时候，我们要求广告主必须将转化效果回传给我们，这样我们才可以基于算法和数据进行投放的自动优化。

目前我们已经与市场上主流的第三方监测公司进行对接，当广告主使用这些第三方监测公司的服务或者在应用内添加了第三方监测公司的 SDK 时，只需要通过第三方监测公司的系统生成投放在掌游天下的点击监测地址，并将地址提供给我们即可。掌游天下已经对接的第三方监测公司有： AdMaster、Talking Data、AppsFlyer、Adjust、热云。

如果广告主没有使用第三方监测公司的服务或者添加第三方监测公司的 SDK，则必须按照本文档的说明向掌游天下发送应用下载激活后的数据。在广告正式上线之前，必须向掌游天下的技术人员申请测试，测试通过后才可以开始广告投放。

## 二、接口说明
### 1、数据回传的请求地址
http://callback.zplayads.com/effect/advertiser?click_id={click_id}&campaign_name={campaign_name}&app_id={app_id}&idfa={idfa}&imei={imei}&advertising_id={adverstising_id}&conversion_type={conversion_type}

### 2、请求方式：GET

### 3、数据回传参数说明
|参数|说明|
|------|---|
|click_id|点击 ID，由 zplay 生成，在点击请求时发送给广告主，广告主回传；必填|
|campaign_name|广告ID，由zplay生成，广告主在zplay平台创建广告投放后生成的ID；必填|
|app_id|广告主应用在zplay平台注册后生成的ID；非必填|
|idfa|iOS操作系统上的唯一ID；在iOS系统时必填|
|imei|Android操作系统上的唯一ID；在Android系统时必填|
|advertising_id|Android操作系统上的唯一ID；非必填|
|conversion_type|转化类型，可用的值及对应ID如下：下载：1；激活：2；付费：3；自定义：（广告主对自定义的ID要提前与zplay确认，并告知zplay）；必填|


### 4、返回参数
如果响应正常，返回ok字符串

## 代码示例
#### Android：
http://callback.zplayads.com/effect/advertiser?click_id=0bts0K1DtjEM0tHfZA07I1WP3pTzxY&campaign_name=EA2645B8-E42A-4817-1780-B2A2A4D47E58&app_id=1000250&imei=864375024316326&advertising_id=eacutmd&conversion_type=1

#### iOS：
http://callback.zplayads.com/effect/advertiser?click_id=0btsuijxEM0tHfZA07I1WP3paytz&campaign_name=4B767D4A-A6A6-4AB5-3B76-FCA5DD9DD276&app_id=1000251&idfa=40740166-76F7-4069-A207-B0DF290754A9&advertising_id=adid12345&conversion_type=1
