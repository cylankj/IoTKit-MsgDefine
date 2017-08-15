## 简化客户端获取计数方式：通过MIDRobotGetData, MIDRobotGetMultiData, MIDRobotGetDataEx获取未读计数，逐渐放弃MIDRobotCountUnReadData接口。

----
## 1.设备类未读消息计数
## DPIDCountUnReadCIDBegin = 1000

## DPIDCountUnReadCameraWarnMsg = 1001 

*  未读消息计数：（兼容2.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|

[DPIDCameraWarnMsg = 505](camera_msg_define.md#dpidcamerawarnmsg-505)

## DPIDCountUnReadCameraWarnMsgV3 = 1002

*  未读消息计数：（3.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|

[DPIDCameraWarnMsgV3 = 512](camera_msg_define.md#dpidcamerawarnmsgv3-512)

## DPIDCountUnReadBaseSDInfo = 1003

* 未读消息计数： 客户端查询是否插入SD卡及错误的信息，本消息是服务器对 DPIDBaseSDStatus（根据sdcard和sdcard_errno）去重后存储, 用于APP端的消息中心。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|

[DPIDBaseSDInfo = 222](base_msg_define.md#dpidbasesdinfo-222)

## DPIDCountUnReadBellCallMsg = 1004

* 未读消息计数：（兼容2.0版设备）门铃已呼叫状态 
* 特别说明：只记录未接听的消息计数（isOK == 0）

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|

 
[DPIDBellCallMsg = 401](bell_msg_define.md#dpidbellcallmsg-401)

## DPIDCountUnReadBellCallMsgV3 = 1005

* 未读消息计数：（3.0版设备）门铃已呼叫状态 
* 特别说明：只记录未接听的消息计数（isOK == 0）

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|

[DPIDBellCallMsgV3 = 403](bell_msg_define.md#dpidbellcallmsgv3-403)



-----

# 帐号类未读消息计数

## DPIDCountUnReadAccountBegin = 1000

## DPIDCountUnReadAccountBind = 1101

* 未读消息计数

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|
[DPIDAccountBind = 601](account_msg_define.md#dpidaccountbind-601)

## DPIDCountUnReadAccountWonder = 1102

* 未读消息计数

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|
[DPIDAccountWonder = 602](account_msg_define.md#dpidaccountwonder-602)

## DPIDCountUnReadAccountShare = 1103

* 未读消息计数

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|
[DPIDAccountShare = 603](account_msg_define.md#dpidaccountshare-603)

## DPIDCountUnReadAccountIsShared = 1104

* 未读消息计数

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|
[DPIDAccountIsShared = 604](account_msg_define.md#dpidaccountisshared-604)

## DPIDCountUnReadSystemMsg = 1105

* 未读消息计数 - 未支持

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|count|int|  msgpack字符串|
[DPIDSystemMsg = 701](system_msg_define.md#dpidsystemmsg-701)

