## MIDBaseNet=MIDBaseBegin +1

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

* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#DefJFGMsgIDBegin-3000

---

## MIDBaseMac = MIDBaseBegin +2

* 设备上报MAC地址

|  data定义 |  类型|   描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|mac|string| 无|

示例：{id，time,"AW:SW:WS:DE:DE:DE"}

* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#DefJFGMsgIDBegin-3000

---

## MIDBaseSD = MIDBaseBegin +3

*  设备上报SD卡开关信息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|sdcard|int|是否有卡|

http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDStatusSdcardTOServer-0

---

## MIDBaseSDStatus = MIDBaseBegin +4

*  设备上报SD卡容量信息

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


示例：{id，time,"{"storage":700000,"storage_used":1000,"sdcard_errno":0}"}

http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDStatusSdcardTOServer-0

---

## MIDBasePower = MIDBaseBegin +5

*  是否连接电源线

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|power|int| 是否 |

http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDStatusSdcardTOServer-0

---

## MIDBaseBattery = MIDBaseBegin +6

*  设备上报剩余电量

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|battery|int|电量 百分比|

http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDStatusSdcardTOServer-0

---

## MIDBaseVersion = MIDBaseBegin +7

* 设备上报软件版本号 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|version|string|  字符串|
 
* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#DefJFGMsgIDBegin-3000

---
 
## MIDBaseSysVersion = MIDBaseBegin +8

*  设备上报系统版本号

|  data定义 |    类型| 描述 |
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sysVersion|string|  字符串|

* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#DefJFGMsgIDBegin-3000

---
 
## MIDBaseLED = MIDBaseBegin +9

* 设备指示灯配置
|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|led|int| 指示灯 |

* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientCidSetReq-8

---

## MIDBaseUptime = MIDBaseBegin +10

*  上报开机时间消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|uptime|int| 开机时间 |

* 原消息定义 http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#DefJFGMsgIDBegin-3000

---

## MIDBaseClientLog = MIDBaseBegin +11

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

http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientPost-0

---

## MIDBaseCidLog = MIDBaseBegin +12

*  上报日志消息 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|log|string| 格式已OK的字符串 |
  
   
