## DPIDBellCallMsg = DPIDBellBegin +1

*  门铃呼叫状态 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|
  
  
|  value定义 |  类型|   描述 | 
|---|---|---|
|isOK|int| 是否接通|
|timeDuration |int| 结束时间点 |
|type|int| 区分云存储海内外地址 |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDBellCallStatus-17

---

## DPIDBellLeaveMsg = DPIDBellBegin +2

*  门铃留言设置 (3.0 新增)

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|int| 枚举 |


---