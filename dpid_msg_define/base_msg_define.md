## DPIDBaseBegin = 200
## DPIDBaseNet = 201

* 设备上报网络类型 / 客户端查询 


|  data定义 |  类型|   描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 |
|---|---|---|
|net|int| 特征值|
|ssid|string| 网络名称|


| net| 特征值|  描述 |
|---|---|---|
|NET_CONNECT | -1 | 绑定后的连接中 |
|NET_OFFLINE |  0 | 不在线 |
|NET_WIFI    |  1 | WIFI网络 |
|NET_2G      |  2 | 2G网络 |
|NET_3G      |  3 | 3G网络 |
|NET_4G      |  4 | 4G网络  |   
|NET_5G      |  5 | 5G网络  |   
|NET_WIRED   |  10 | 有线网络  |   

设备上线时示例： {id, time, msgpack(1,"cylan_605")}

设备离线时实例： {id, time, msgpack(0,"")}， 服务器检测到离线后主动推送该消息给客户端。  


---

## DPIDBaseMac=202

* 设备上报MAC地址 / 客户端查询 

|  data定义 |  类型|   描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|mac|string| 无|

示例：{id，time, msgpack("AW:SW:WS:DE:DE:DE")}


---

## DPIDBaseFormatSDAck = 203 

*  格式化SD卡的响应
*  客户端调用 [MIDRobotSetData](mid_msg_define/mid_define.md#midrobotsetdata20202) 接口发送格式化命令 [DPIDBaseFormatSD = 218](base_msg_define.md#dpidbaseformatsd-218)，设备端响应结果给服务器，服务器主动推送 [MIDRobotPushData](mid_msg_define/mid_define.md#midrobotputdata20211) 接口 [DPIDBaseFormatSDAck = 203](base_msg_define.md#dpidbaseformatsdack-203) 给客户端。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|storage|int64|卡容量 单位byte|
|storage_used|int64|已用空间 单位byte|
|sdcard_errno |int|错误号。0 正常； 非0错误，需要格式化|
|sdcard|bool|是否有卡|

[sdcard_errno 定义](error_define.md#sd卡错误码)

---

## DPIDBaseSDStatus = 204

*  设备SD卡容量信息 / 客户端查询 
*  实时向设备发起查询请求：仅适合用户主动触发场景，节省功耗（需要避免高频次调用：如主页列表，消息中心等） 
*  APP端 调用 MIDRobotGetData 类接口获取，服务器使用 MIDRobotPushData 推送给APP端。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|storage|int64|卡容量 单位byte|
|storage_used|int64|已用空间 单位byte|
|sdcard_errno |int|错误号。0 正常； 非0错误，需要格式化|
|sdcard|bool|是否有卡|

[sdcard_errno 定义](error_define.md#sd卡错误码)

---

## DPIDBasePower = 205

*  是否连接电源线 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|power|bool| 是否 |

---

## DPIDBaseBattery = 206

*  设备上报剩余电量 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|battery|int|电量 百分比|

---

## DPIDBaseVersion = 207

* 设备上报软件版本号 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|version|string|  字符串|

---
 
## DPIDBaseSysVersion = 208

*  设备上报系统版本号 / 客户端查询 

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|sysVersion|string|  字符串|

---
 
## DPIDBaseLED = 209

* 设备指示灯配置 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|led|bool| 指示灯 |

---

## DPIDBaseUptime = 210

*  上报开机时间戳消息 / 客户端查询  



|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|powerOn|int| 开机时间戳，单位秒。示例（2017-02-22 18: 57 :37）：1487761057|


---

## DPIDBaseCidLog = 212

*  上报日志消息 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|log|string| 格式已OK的字符串 |
  
---

## DPIDBaseP2PVersion = 213

* 上报P2P版本号 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|time| int64| 数据更新时间点 |
|version|int|  p2p版本 |

--- 

 
## DPIDBaseTimezone = 214

* 设备时区配置 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|timezone|string| 如： Asia/Shanghai。注：请使用标准的时区字符串，参考：[wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)|
|offset |int|如东八区： 8\*60\*60=28800，单位秒|


----
 
## DPIDBaseIsPushFlow = 215

* 设备推流配置 / 客户端查询  

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|isPushFlow|bool|  |

----
 
## DPIDBaseIsNTSC = 216

* 设备电流频率配置 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|isNTSC|bool|  |

----
 
## DPIDBaseIsMobile = 217

* 设备优先使用移动网络配置 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|isMobile|bool| True 在WiFi可用的时候，优先使用移动网络， False 在WiFi可用的时候，优先使用WiFi, WiFi不可用的时候，再使用移动网络。|

----

## DPIDBaseFormatSD = 218

*  格式化SD卡命令
*  使用方式参考 [DPIDBaseFormatSDAck = 203](base_msg_define.md#dpidbaseformatsdack-203)

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| 占位，默认0 |

---


## DPIDBaseBind = 219

*  绑定，解绑信息 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string |msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|isBind|bool| true: 绑定；false：解绑|
|account |string |如果isBind = true，则是绑定帐号；如果isBind = false， 则是解绑帐号|
|oldAccount |string |如果isBind = true，并且该设备被其他帐号（oldAccount）绑定，则该字段有值，否则该字段为空。|

---


## DPIDBaseSdkVersion = 220

*  设备上报SDK版本号 / 客户端查询 

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|version|string|  字符串|

---


## DPIDBaseCtrlLog = 221

*  开启客户端和设备端日志功能 
*  到截止时间后自动停止。
*  终端逻辑：终端将当前时间戳now和timeEnd比较，如果now <= timeEnd, 向日志服务写入日志；如果now > timeEnd, 停止写入日志。
*  服务器逻辑：如果客户端和设备端在线，主动推送；如果不在线，上线时自动获取。

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|ip|string| 日志服务器地址 |
|port|int| 日志服务器端口|
|timeEnd|int| 结束时间点，单位秒。|

---

## DPIDBaseSDInfoOnOff = 222

* 1 设备端 SD 卡插拔消息， 服务器使用 MIDRobotPushData 推送给APP端。
* 2 APP端的消息中心， APP端 调用 MIDRobotGetData 类接口获取。


|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|sdcard|bool|是否有卡|
|sdcard_errno |int|错误号。0 正常； 非0错误，需要格式化|


----
 
## DPIDBaseIsExistMobile = 223

* 设备端是否存在可用的移动网络。
* 设备端插入和拔出sim卡均会上报该消息。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|sim|int|0 未知, 1 没卡,  2 user's PIN, 3 user's PUK, 4 network PIN, 5 正常|

---

## DPIDBaseCtrlLogUploadFile = 224

*  通知设备端上传日志压缩包。
*  终端逻辑：终端收到该命令后，上传文件到指定云存储地址，命名约束[filename].zip。

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|filename| string | YYYYMMDD_HHmm 示例：20161222_1122 |

---

## DPIDBaseIsExistNetWired = 225

* 设备端是否存在可用的有线网络。
* 设备端插入和拔出网线均会上报该消息。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| 0 拔出网线， 1 插入网线  |

--- 

## DPIDBaseIsNetWired = 226

* 客户端配置/设备端查询 设备是否使用有线网络 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|isWiredNet|bool| True 使用有线网络， False 不使用有线网络。|

--- 

## DPIDBasePrivateIP = 227

* 客户端查询/设备端上发 内网IP地址

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|IP|string| 内网IP地址。示例：192.168.0.1 |

## DPIDBaseUpgradeStatus = 228

* 设备端上报升级状态

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| 0 未升级，1 升级中  |

## DPIDBaseVoltage = 229

*  设备上报电压 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|voltage|int|电压 0 低电压（表示电量不足）， 1 正常|

## DPIDBaseRegion = 230

*  服务端记录 / 客户端查询 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|region|int|设备所在区域（设备登陆过才有记录）。CN:1，US:2，EU:3，SG:4。|

## DPIDBaseLocalConf = 231

*  获取 / 设置设备配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|msgpack(json)|

---