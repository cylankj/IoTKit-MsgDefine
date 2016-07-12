## DPIDRelayServer = DPIDCFGBegin+1

*   RelayServer配置

|  data定义 |    类型 | 描述 | 
| --- | --- | --- |
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
 
* 原19号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#RELAY_SERVER-19

--------------------------------------------------------------------------------------------------------------------------

## DPIDHeartbeat = DPIDCFGBegin+2

*  心跳配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|heartbeat|int|  秒 |
 
* 客户端直接文件直接上传到OSS, 所以MsgServer弃用。
* 原18号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#SERVER_CONFIG-18
 
-------

## DPIDCidOSSConfig = DPIDCFGBegin+3

*  CidOSSConfig配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
* 原128号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#CID_PUSH_OSS_CONFIG-128
* 注：因为通道已加密，所以去掉消息内加密。

<pre>
type定义：
const (
	OssCNConfig = 1 + iota  //阿里中国
	OssUSConfig = 2         //阿里美国
    AwsUSConfig = 3         //亚马逊美国
)
</pre>

如果是Aws存储，该配置只下发type = AwsUSConfig， hostname = us-west-2（即为regionName）和bucket = us_jfgyun 字段，Access ID和Key为空，需要通过接口获取安全凭证：http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#CLIENT_GET_AWS_CREDENTIALS_REQ-16306
      
 
----------------------------------------------------------------------------------------------------------------------------

## DPIDClientOSSConfig = DPIDCFGBegin+4

*  ClientOSSConfig配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
* 原129号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#CLIENT_PUSH_OSS_CONFIG-129
* 注：因为通道已加密，所以去掉消息内加密。


------

## DPIDClientUpgradeConfig = DPIDCFGBegin+5

*  ClientUpgradeConfig配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
|  value定义 |  类型|   描述 | 
|---|---|---|
|url|string| 升级地址|
|isUpgrade|int|是否强制升级|

* 原响应消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientLoginRsp30-1

------

