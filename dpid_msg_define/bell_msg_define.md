## DPIDBellBegin = 400
## DPIDBellCallMsg = 401

*  （兼容2.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|
  
  
|  value定义 |  类型|   描述 | 
|---|---|---|
|isOK|int| 是否已接听 |
|time|int|单位秒。门铃的呼叫时间，ios和android客户端可以根据此时间判断是否收到了重复的呼叫，根据此时间可以找到对应的截图url # 2.4.5 新增|
|timeDuration |int| 结束时间点，单位秒 |
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 128 消息下发的数据。 |

存储路径：                [bucket]/[cid]/[timestamp].jpg ， 文件名使用图片产生时间，单位秒。

---

## DPIDBellLeaveMsg = 402

*  门铃留言设置 (3.0 新增)

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|int| 枚举 |


---

## DPIDBellCallMsgV3 = 403

*  （3.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|
  
  
|  value定义 |  类型|   描述 | 
|---|---|---|
|isOK|int| 是否已接听 |
|time|int|单位秒。门铃的呼叫时间，ios和android客户端可以根据此时间判断是否收到了重复的呼叫，根据此时间可以找到对应的截图url # 2.4.5 新增|
|timeDuration |int| 结束时间点，单位秒 |
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 DPIDCloudStorage = 3 消息下发的数据。|

存储路径：               [bucket]/cid/[vid]/[cid]/[timestamp].jpg  