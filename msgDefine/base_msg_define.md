## DPIDBaseBegin = 200
## DPIDBaseNet=DPIDBaseBegin +1

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

设备上线时示例： {id, time, msgpack(1,"cylan_605")}

设备离线时实例： {id, time, msgpack(1,"")}， 服务器检测到离线后主动推送该消息给客户端。  


---

## DPIDBaseMac = DPIDBaseBegin +2

* 设备上报MAC地址

|  data定义 |  类型|   描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|mac|string| 无|

示例：{id，time, msgpack("AW:SW:WS:DE:DE:DE")}


---

## DPIDBaseSD = DPIDBaseBegin +3

*  设备上报SD卡开关信息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sdcard|bool|是否有卡|

示例：{id，time, msgpack(true)}

---

## DPIDBaseSDStatus = DPIDBaseBegin +4

*  设备上报SD卡容量信息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|storage|int|卡容量 单位byte|
|storage_used|int|已用空间 单位byte|
|sdcard_errno |int|错误号|


---

## DPIDBasePower = DPIDBaseBegin +5

*  是否连接电源线

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|power|bool| 是否 |

---

## DPIDBaseBattery = DPIDBaseBegin +6

*  设备上报剩余电量

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|battery|int|电量 百分比|

---

## DPIDBaseVersion = DPIDBaseBegin +7

* 设备上报软件版本号 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|version|string|  字符串|

---
 
## DPIDBaseSysVersion = DPIDBaseBegin +8

*  设备上报系统版本号

|  data定义 |    类型| 描述 |
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sysVersion|string|  字符串|

---
 
## DPIDBaseLED = DPIDBaseBegin +9

* 设备指示灯配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|led|bool| 指示灯 |

---

## DPIDBaseUptime = DPIDBaseBegin +10

*  上报开机时间消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|uptime|int| 开机时间 |

---

## DPIDBaseClientLog = DPIDBaseBegin +11

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

## DPIDBaseCidLog = DPIDBaseBegin +12

*  上报日志消息 （3.0新增）

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|log|string| 格式已OK的字符串 |
  
---

## DPIDBaseP2PVersion = DPIDBaseBegin +13

* 上报P2P版本号 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|version|int|  p2p版本 |

--- 

 
## DPIDBaseTimezone = DPIDBaseBegin +14

* 设备时区配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|timezone|string| 如： Asia/Shanghai。|
|offset |int|单位：秒。 如东八区： 8*60*60|


----
 
## DPIDBaseIsPushFlow = DPIDBaseBegin +15

* 设备推流配置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|isPushFlow|bool|  |

----
 
## DPIDBaseIsNTSC = DPIDBaseBegin +16

* 设备电流频率配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|isNTSC|bool|  |

----
 
## DPIDBaseIsMobile = DPIDBaseBegin +17

* 设备优先使用移动网络配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|isMobile|bool|  |

----

## DPIDBaseFormatSD = DPIDBaseBegin +18

*  格式化SD卡

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|int|占位字段，暂未使用|

---



