## 全局配置类定义 DPIDCFGBegin = 0
## DPIDRelayServer = DPIDCFGBegin + 1

*   RelayServer配置

|  data定义 |    类型 | 描述 | 
| --- | --- | --- |
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 

--------------------------------------------------------------------------------------------------------------------------

## DPIDHeartbeat = DPIDCFGBegin + 2

*  心跳配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|heartbeat|int|  单位秒 |
  
-------

## DPIDCloudStorage = DPIDCFGBegin + 3

*  云存储配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|value|string| msgpack字符串：map结构  |

|  mapKey定义 |  类型|   描述 | 
|---|---|---|
|regionType|int|枚举 enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeS3USEast1}|

 
|  mapValue定义 |  类型|   描述 | 
|---|---|---|
|cloudStorageType|int|枚举 enum{cloudStorageOSS, cloudStorageS3}|
|bucketName|string| 存储桶|
|regionName|string|区域|
|url|string|域名|


------

## DPIDClientUpgradeConfig = DPIDCFGBegin + 5

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

------

