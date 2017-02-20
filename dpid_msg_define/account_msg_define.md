## 帐号相关功能定义 DPIDAccountBegin = 600
## DPIDAccountBind = 601

*  强制绑定，解绑消息的记录

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|-- |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|isBind|bool| true：绑定，false：解绑|
|account |string| 强绑帐号 |
|sn |string| 设备序列号 |
---


## DPIDAccountWonder = 602

*  每日精彩消息 (3.0 新增) 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|time|int|视频或图片生成的时间点，单位秒|
|msgType|int| 0-附带图片，1-附带视频|
|regionType |int| 海外或国内存储地。|
|fileName |string|附件文件名全称。如：图片timestamp.jpg 视频timestamp.mp4 |

## DPIDAccountShare = 603

*  分享或取消分享设备给好友的消息记录

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|isShare|bool| true：分享，false：取消分享|
|account |string| 对方帐号 |


## DPIDAccountIsShared = 604

*  被好友分享或取消分享设备的消息记录

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|isShare|bool| true：分享，false：取消分享|
|account |string| 对方帐号 |

---

## DPIDAccountLog = 605

*  提交WIFI信息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| 格式已OK的字符串 |

以设置WiFi为例，
客户端实际上发的value为： 设置WiFi：SSID[XiaoLan],密码[123456]，加密方式[WAP2], 频段[2.4G]

