# 广告主应用激活回传接口
## 一、使用场景
当您和ZPLAY Ads约定按照应用的下载激活进行结算的时候，您必须同意将激活数据回传给我们，这样我们才可以基于算法和数据进行投放的自动优化。

当您没有使用第三方监测公司的服务或者添加第三方监测公司的 SDK，而使用了自己的监测工具时，您必须按照本文档的说明向我们回传应用下载激活的数据。在广告正式上线之前，必须通过我们的激活回调测试，只有通过后才可以开始广告投放。

## 二、接口说明
### 1、数据回传的请求地址
https://callback.zplayads.com/effect/advertiser?click_id={click_id}&campaign_name={campaign_name}&promote_app_id={promote_app_id}&traffic_app_id={traffic_app_id}&ad_unit_id={ad_unit_id}&idfa={idfa}&imei={imei}&advertising_id={advertising_id}&android_id={android_id}&price={price}&currency={currency}&cost_model={cost_model}&secret={secret}&conversion_type={conversion_type}

### 2、请求方式：GET

### 3、数据回传参数说明
> 以下参数由ZPLAY Ads生成，通用的符号为{}，在广告展示及产生点击时，我们通过将替换完的值传递给您，您在回传激活数据时需将参数一并回传。
>
> 当激活发生在Android系统时，imei、advertising_id及android_id三个参数必须回传一个。

|参数|是否必须回传|说明|
|------|---|----|
|click_id|必须|点击 ID，由 ZPLAY Ads 生成，在展示及点击请求时替换后发送给广告主|
|campaign_name|必须|广告ID，由 ZPLAY Ads 生成，广告主在 ZPLAY Ads 平台创建广告投放后生成的ID|
|promote_app_id|必须|广告主应用在 ZPLAY Ads 平台注册后生成的ID，由 ZPLAY Ads 生成|
|traffic_app_id|必须|流量来源的应用ID，由 ZPLAY Ads 生成|
|ad_unit_id|必须|流量来源的广告位ID，由 ZPLAY Ads 生成|
|idfa|在iOS系统时必须|iOS操作系统上的唯一ID|
|imei|在Android系统时非必须|Android操作系统上的唯一ID|
|advertising_id|在Android系统时非必须|Android操作系统上的唯一ID|
|android_id|在Android系统时非必须|Android操作系统上的唯一ID|
|price|必须|广告的CPI单价|
|currency|必须|广告单价货币|
|cost_model|必须|广告计费方式|
|secret|必须|秘钥，由 ZPALY Ads 生成|
|conversion_type|必须|转化类型|


### 4、返回参数
如果响应正常，返回ok字符串

## 三、代码示例
#### Android：
https://callback.zplayads.com/effect/advertiser?click_id=0bts0K1DtjEM0tHfZA07I1WP3pTzxY&campaign_name=EA2645B8-E42A-4817-1780-B2A2A4D47E58&promote_app_id=1000250&traffic_app_id=33299445&ad_unit_id=3456778&imei=864375024316326&advertising_id=eacutmd&price=30&currency=CNY&cost_model=cpi&secret=8jdyeh3b583dhjs&conversion_type=install

#### iOS：
https://callback.zplayads.com/effect/advertiser?click_id=0btsuijxEM0tHfZA07I1WP3paytz&campaign_name=4B767D4A-A6A6-4AB5-3B76-FCA5DD9DD276&promote_app_id=1000250&traffic_app_id=33299445&ad_unit_id=3456778&idfa=40740166-76F7-4069-A207-B0DF290754A9&price=30&currency=CNY&cost_model=cpi&secret=8jdyeh3b583dhjs&conversion_type=install
