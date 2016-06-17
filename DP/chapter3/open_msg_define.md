# 一、原有结构化消息定义

需要服务器解析处理的消息保持原结构化格式不变。
原消息定义：消息头 + 可变消息体
 
|  定义 |  类型|   描述 | 
| ---   | ---  | ---    |
|id     | int  | TCP消息唯一标识 |
|caller | string | 源端标识 |
|callee | string | 目的端标识 |
|data1  | ...    | 自定义  |
|...    | ...    | ...     |
|dataN  | ...    | 自定义  |
 

 ---
 
# 二、新增通用消息定义：

## 2.1 消息定义 - 查询请求 RobotGetData = 20200

|  定义 |  类型|   描述 | 
| --- | --- | --- |
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|limit|int| 查询条数 |
|asc|bool| 升降序 |
|reqList|array| 被查询功能的消息列表 |


| 定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 查询时间点 |

说明：
* time统一以服务器时间戳为准。
* 如果asc为真，服务器返回time时间点后的数据，之前的数据不返回。
* 如果asc为否，服务器返回time时间点前的数据，之后的数据不返回。
* 如果time置为0, 默认使用服务器当前时间。
* 如果查询单条记录，limit置为1。
* 如果查询列表，limit >1 && limit <=100。
* 服务器或相应端将响应的seq号与请求的seq保持相同，以保证消息的一一对应。


---

## 2.2 消息定义 - 查询响应 RobotGetDataRsp = 20201 

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | data消息数组 |

| data定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|value| int, string, bool, ...| 基础类型： |


说明：

* 每个data都是一个开放功能的完整定义。

## 2.2 消息定义 -  设备上报消息 + 配置请求 RobotSetData = 20202 

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|reqList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|value| int, string, bool, ...| 基础类型： |



---

## 2.3 消息定义 - 配置响应 RobotSetDataRsp = 20203

由开放功能定义表格返回值列决定是否要响应该消息。

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|ret| int | 返回值 |

* time 由服务器提供，客户端更新该消息的缓存时间戳。


---

## 2.4 消息定义 - 删除请求 RobotDelData = 20204


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识|
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|reqList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 删除时间点 |

* time 如果time为真，删除匹配条件的单条记录。如果time为0, 删除该id的全部消息。

---

## 2.5 消息定义 - 删除响应 RobotDelDataRsp = 20205


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 删除时间点 |
|ret| int | 返回值 |

* time 原样返回客户端的请求数据，只增加ret作为响应码。


## 2.6 消息定义 - 未读消息计数 RobotCountData = 20206


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|act|int| 操作：查询未读消息计数， 将未读消息计数清零(不需要响应RobotCountDataRsp) enum {RobotCountDataQuery, RobotCountDataClear}|
|reqList | array | 消息数组 |

| 定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |

---

## 2.7 消息定义 - 未读消息计数响应 RobotCountDataRsp = 20207


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|act|int| 操作：查询未读消息计数 enum {RobotCountDataQuery}|
|dataList | array | data消息数组 |

| data定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|count| int | 计数 |



# 三、 公有功能消息定义：

## 3.1 全局配置类消息定义

*   RelayServer配置

|  data定义 |    类型 | 描述 | 
| --- | --- | --- |
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
 
原19号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#RELAY_SERVER-19
 
--------------------------------------------------------------------------------------------------------------------------

*  MsgServer配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64 | 数据更新时间点 |
|value|string|  msgpack字符串 |
 
原18号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#SERVER_CONFIG-18
 
-------


*  CidOSSConfig配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
原128号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#CID_PUSH_OSS_CONFIG-128
 
----------------------------------------------------------------------------------------------------------------------------


*  ClientOSSConfig配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|value|string|  msgpack字符串 |
 
原129号消息 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89#CLIENT_PUSH_OSS_CONFIG-129
 
--------------------------------------------------------------------------------------------------------------------------------------


## 3.2 功能消息定义


* 设备上报网络类型 

|  data定义 |  类型|   描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|net|int| WiFi，3G，4G等|
|ssid|string| 网络名称|

示例： {id, time, "{"net":1,"ssid":"cylan_605"}"}

---

* 设备上报MAC地址

|  data定义 |  类型|   描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|mac|string| 无|

示例：{id，time,"AW:SW:WS:DE:DE:DE"}

---

*  设备上报SD卡信息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|sdcard|int|是否有卡|
|storage|int|卡容量 单位byte|
|storage_used|int|已用空间 单位byte|
|sdcard_errno |int|错误号|


示例：{id，time,"{"sdcard":1,"storage":700000,"storage_used":1000,"sdcard_errno":0}"}

---

*  设备上报剩余电量

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|battery|int|电量 百分比|


---

* 设备上报版本号 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|version|string|  字符串|
 

---
 
*  设备上报系统版本号

|  data定义 |    类型| 描述 |
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sysVersion|string|  字符串|
 
 
---

*  设备报警配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串 |
 
 
|  value定义 |  类型|   描述 | 
|---|---|---|
|enable|int| 是否开启 |
|begin_time|int| 开始时间点 |
|end_time|int| 结束时间点 |
|week|int| 每周的星期* |
 
---

*  设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|file|int|协商命名规则为：time_id.jpg。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|type|int|海外或国内存储地区。128消息下发填充|


---

*  控制设备麦克风

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|int64| int| 时间点 |
|mike|bool| 开启/关闭麦克风 |
  
 ---

*  控制设备喇叭

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|speaker|bool| 开启/关闭喇叭 |

  
 ---

*  控制设备画面翻转

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|direction|int| 0 默认正向 |
 
  
---

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


---

*  上报日志消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|log|string| 格式已OK的字符串 |
  
   
---

*  上报开机时间消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|uptime|int| 开机时间 |


---

*  提交WIFI信息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|postType|int| 0-绑定，1-设置WiFi|
|SSID |string| / |
|password|string| 密码 |
|encryType |string| 加密方式 |
|channel|string| 频段 |


---


*  门铃留言设置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|int| 枚举 |


---


*  延迟摄影设置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|interval|int| 间隔时间|
|duration |int|拍摄时长|
|beginTime |int64|开始时间|


---


*  摄像头待机 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| / |


---


*  延迟摄影设置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|picFile|int| 协商命名规则为：time.jpg。|
|ossType |int|海外或国内存储地区。128消息下发填充|
|isOk |bool|接听状态|
|audio |bool|是否有留言|


---


*  门磁消息通知开关设置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| / |


---


*  每日精彩消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|msgType|int| 0-附带图片，1-附带视频|
|ossType |int|海外或国内存储地区。128消息下发填充|
|fileName |string|附件文件名|

---
 

* APP端多条查询消息 - 状态类
  
组合查询 - 如同时查询SD卡和网络类型的消息请求：设备列表cidlist使用这种方式。
{20200, "", "200000001", 1, true, [{5, time},{3, time}]}
    
响应：
{20201, "", "", [[{5, time, "{"sdcard_errno":0}"}], [{3, time, "{"ssid":"cylan_605"}"}]]}
   
---
   
* APP端多条查询消息 - 图表类

如查询报警消息的请求：
{20200, "", "200000001", 2, true, [{9, time}]}
   
如查询报警消息的响应：
{20201, "", "", [[{9，time, "{"file":7,"type":1}"},{9, time,{"file":7,"type":1}}]]}
   
---
  
# 三、 服务器消息缓存原则：缓存最新一条消息。





