## 帐号相关功能定义 DPIDAccountBegin = 600
## DPIDAccountBind = 601

*  强制绑定，解绑消息的记录

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|-- |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|isBind|bool| true：绑定，false：解绑|
|account |string| 强绑帐号 |
|sn |string| 设备序列号 |
|pid |int| 设备型号 |
---


## DPIDAccountWonder = 602

*  每日精彩消息 (3.0 新增) 
*  报警图片、直播截图、门铃呼叫记录截图
*  使用[MIDRobotSetDataByTime=20216](mid_msg_define/mid_define.md#midrobotsetdatabytime20216)。
*  使用[MIDRobotGetDataByTime=20218](mid_msg_define/mid_define.md#midrobotgetdatabytime20218)。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒。赋值为 DPIDCameraWarnAndWonder 中的 ctimeMsec |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|time|int|视频或图片生成的时间点，单位秒|
|msgType|int| 0-附带图片，1-附带视频|
|regionType |int| 海外或国内存储地。|
|fileName |string|附件文件名全称。如：图片timestamp.jpg 视频timestamp.mp4 |
|alias|string|设备别名|
|favoriteTimeMsec|int64|视频或图片收藏的时间点，单位毫秒。DPIDCameraWarnAndWonder 中的timeMsec  |



## DPIDAccountShare = 603

*  分享或取消分享设备给好友的消息记录

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
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
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
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
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| 格式已OK的字符串 |

以设置WiFi为例，
客户端实际上发的value为： CID[200000000001], 设置WiFi：SSID[XiaoLan],密码[123456]，加密方式[WAP2], 频段[2.4G]
服务器记录该消息到用户日志。


---

## DPIDAccountWonderV2 = 606

*  每日精彩消息 (3.2 新增) 
*  分享 720 双鱼眼图片或视频
*  视频缩略图由客户端生成并put到bucket，命名规则对应fileName，示例：视频文件为timestamp.mp4，则缩略图为timestamp.jpg

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|cid|string| -- |
|time|int|视频或图片生成的时间点，单位秒|
|msgType|int| 0-附带图片，1-附带视频|
|regionType |int| 海外或国内存储地。|
|fileName |string|附件文件名全称。如：图片timestamp.jpg 视频timestamp.mp4 |
|desc|string|用户分享描述|
|url|string|视频或图片分享的H5链接|

