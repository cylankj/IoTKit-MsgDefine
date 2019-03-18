## DPIDCidPushBegin=10000
## DPIDPushCidBind = 10001
## DPIDPushCidUnBind = 10002
## DPIDPushCidShare = 10003
## DPIDPushCidUnShare = 10004

* 推送绑定、解绑、分享、取消分享通知

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|cid|string| 被操作设备,msgpack字符串 |
---