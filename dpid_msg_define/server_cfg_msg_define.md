## 全局配置类定义 DPIDCFGBegin = 0
## DPIDRelayServer = 1

*   RelayServer配置

|  data定义 |    类型 | 描述 | 
| --- | --- | --- |
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 

--------------------------------------------------------------------------------------------------------------------------

## DPIDHeartbeat = 2

*  心跳配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|heartbeat|int|  单位秒 |
  
-------

## DPIDCloudStorage = 3

*  云存储配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|value|string| msgpack字符串：map结构  |

|  mapKey定义 |  类型|   描述 | 
|---|---|---|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}|

 
|  mapValue定义 |  类型|   描述 | 
|---|---|---|
|cloudStorageType|int|枚举 enum{cloudStorageOSS, cloudStorageS3}|
|bucketName|string| 存储桶|
|regionName|string|区域|
|url|string|域名|


生命周期用于oss定期清理文件。
客户端获取临时安全凭证：读写权限控制到account和cid级别。
设备端获取临时安全凭证：读写权限控制到cid级别。

2.4.6 运营版的客户端云存储路径约束：

| 功能名称 |云存储路径 |说明 | 生命周期 |
|--- |--- |--- |--- |
|用户头像 |[bucket]/image/[account].jpg|--- |永久保留 |


2.4.6 运营版的设备端云存储路径约束：

| 功能名称 |云存储路径 |说明 | 生命周期 |
|--- |--- |--- |--- |
|报警图片 | [bucket]/[cid]/[timestamp]_[id].jpg | 文件名使用图片产生时间，单位秒; id特征值为1，2，3。 |15 天|
|门铃截图 | [bucket]/[cid]/[timestamp].jpg | 文件名使用图片产生时间，单位秒。 |15 天|
|3g狗的apns配置 | [bucket]/package/apns.xml| \ | 永久保留 |
|wifi狗报警声音 | [bucket]/package/alert.pcm[u] /package/wang.pcm[u]| \ |永久保留 |

3.0 (对接VID,VKEY) 客户端云存储路径约束：
  
| 功能名称 |云存储路径 |说明 | 生命周期 |
|--- |--- |--- |--- |
|用户头像 |[bucket]/image/[account].jpg |客户端根据消息号16301中vid值判断头像是否更新。默认头像客户端内置。 |永久保留 |
|用户反馈的日志 |[bucket]/log/[vid]/[account]/[timestamp].zip |文件名使用上传时间戳，单位秒。|两个月|
|用户每日精彩 |[bucket]/long/[vid]/[account]/wonder/[cid]/[timestamp].jpg |如果是报警图片或延时摄影图片（视频），需要客户端将音视频文件copy到该目录下|永久保留 |
|用户每日精彩之延时摄影合成的影片 |[bucket]/long/[vid]/[account]/wonder/[cid]/[timestamp].mp4 |文件名使用延时摄影开始的时间，单位秒。 演示视频位置：[bucket]/long/demo.mp4|永久保留 |
|用户每日精彩之延时摄影视频的首帧图片 |[bucket]/long/[vid]/[account]/wonder/[cid]/[timestamp].jpg|文件名使用延时摄影开始的时间，单位秒。 |永久保留 |



3.0 (对接VID,VKEY) 设备端云存储路径约束：
  
| 功能名称 |云存储路径 |说明 |生命周期 |
|--- |--- |--- |--- |
| 报警和门铃截图 | [bucket]/cid/[vid]/[cid]/[timestamp]_[id].jpg |文件名使用图片产生时间，单位秒; id特征值为1，2，3。| 15 天|
| 延时摄影图片| [bucket]/long/[vid]/[cid]/tmp/%04d.jpg | 文件名使用自然数左边补零格式化为四位字符串。 临时目录，服务器主动删除。| 临时 |
| 设备端上传日志|[bucket]/log/[vid]/[cid]/[timestamp].zip|文件名使用上传时间戳，单位秒|两个月|



------

## DPIDClientUpgradeConfig = 5

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

