## 简化客户端获取计数方式：通过MIDRobotGetData, MIDRobotGetMultiData, MIDRobotGetDataEx获取未读计数，逐渐放弃MIDRobotCountUnReadData接口。

## DPIDCountUnReadBegin = 1000

## DPIDCountUnReadCameraWarnMsg = 1001 

*  未读消息计数：（兼容2.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|count|int|  msgpack字符串|

[DPIDCameraWarnMsg = 505](camera_msg_define.md#dpidcamerawarnmsg-505)

## DPIDCountUnReadCameraWarnMsgV3 = 1002

*  未读消息计数：（3.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|count|int|  msgpack字符串|

[DPIDCameraWarnMsgV3 = 512](camera_msg_define.md#dpidcamerawarnmsgv3-512)

## DPIDCountUnReadBaseSDInfo = 1003

* 未读消息计数： 客户端查询是否插入SD卡及错误的信息，本消息是服务器对 DPIDBaseSDStatus（根据sdcard和sdcard_errno）去重后存储, 用于APP端的消息中心。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|count|int|  msgpack字符串|

[DPIDBaseSDInfo = 222](base_msg_define.md#dpidbasesdinfo-222)

## DPIDCountUnReadBellCallMsg = 1004

* 未读消息计数：（兼容2.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|count|int|  msgpack字符串|

 
[DPIDBellLeaveMsg = 402](bell_msg_define.md#dpidbellleavemsg-402)

## DPIDCountUnReadBellCallMsgV3 = 1005

* 未读消息计数：（3.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|count|int|  msgpack字符串|

[DPIDBellCallMsgV3 = 403](bell_msg_define.md#dpidbellcallmsg-403)



