## DPIDAccountBind = DPIDAccountBegin + 1

*  强制绑定，解绑消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|isBind|bool| true：绑定，false：解绑|
|account |string| 强绑帐号 |

---


## DPIDAccountWonder = DPIDAccountBegin + 2

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
|regionType |int| 阿里或亚马逊的云存储地区。|
|fileName |string|附件文件名全称。如：图片timestamp.jpg 视频timestamp.mp4 |

## DPIDAccountShare = DPIDAccountBegin + 3

*  分享或取消分享设备给好友

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


## DPIDAccountIsShared = DPIDAccountBegin + 4

*  被好友分享或取消分享设备

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