## DPIDBellBegin = 400
## DPIDBellCallMsg = 401

*  （兼容2.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|
  
  
|  value定义 |  类型|   描述 | 
|---|---|---|
|isOK|int| 是否已接听 |
|time|int|单位秒。门铃的呼叫时间，ios和android客户端可以根据此时间判断是否收到了重复的呼叫，根据此时间可以找到对应的截图url # 2.4.5 新增|
|timeDuration |int| 结束时间点，单位秒 |
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 128 消息下发的数据。 |
|is_record|int|3.2.2 版本新增字段；是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。|


存储路径：                [bucket]/[cid]/[timestamp].jpg ， 文件名使用图片产生时间，单位秒。

注： 如果is_record 和 file 不存在，则是2.0的门铃； 客户端需要做好新旧版兼容。

---

## DPIDBellLeaveMsg = 402

*  门铃留言设置 (3.0 新增)

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| 枚举 |


---

## DPIDBellCallMsgV3 = 403

*  （3.0版设备）门铃已呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|
  
  
|  value定义 |  类型|   描述 | 
|---|---|---|
|isOK|int| 是否已接听 |
|time|int|单位秒。门铃的呼叫时间，ios和android客户端可以根据此时间判断是否收到了重复的呼叫，根据此时间可以找到对应的截图url # 2.4.5 新增|
|timeDuration |int| 结束时间点，单位秒 |
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 DPIDCloudStorage = 3 消息下发的数据。|
|is_record|int|3.2.2 版本新增字段；是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。|




存储路径：               [bucket]/cid/[vid]/[cid]/[timestamp].jpg  

注： 如果is_record 和 file 不存在，则是2.0的门铃； 客户端需要做好新旧版兼容。

## DPIDBellDeepSleep = 404

* 深度睡眠设置。
* 默认值： 空。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value| string | msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|enbale|bool| 是否开启 |
|beginTime|int64| 开始时间，单位秒 |
|endTime|int64| 结束时间，单位秒 |
