## DPIDCameraBegin = 500
## DPIDCameraWarnEnable = DPIDCameraBegin +1

* 设备报警开关配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| 是否开启 |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDCidPushCidset-3007

---

## DPIDCameraWarnTime = DPIDCameraBegin +2

*  设备报警时间段配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串 |
 
 
|  value定义 |  类型|   描述 | 
|---|---|---|
|begin_time|int| 开始时间点 |
|end_time|int| 结束时间点 |
|week|int| 每周的星期* |
 
* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDCidPushCidset-3007

---

## DPIDCameraWarnSensitivity = DPIDCameraBegin +3

*  报警灵敏度配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sensitivity|int| 灵敏度 0为低SENSITIVITY_LOW, 1为中SENSITIVITY_DPIDDLE, 2为高SENSITIVITY_HIGH 默认为中 |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDCidPushCidset-3007

---

## DPIDCameraWarnSound = DPIDCameraBegin +4

*  报警提示音配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|sound|int| 报警设备提示音 |
|sound_long|int| 循环播放时长 |


* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDCidPushCidset-3007

---

## DPIDCameraWarnMsg = DPIDCameraBegin +5 

*  设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int64| 时间点 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|file|int|协商命名规则为：time_id.jpg。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|type|int|海外或国内存储地区。128消息下发填充|


* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDUploadWarn-3105

---

## DPIDCameraTimeLapse = DPIDCameraBegin +6

*  延迟摄影设置 (3.0 新增) 

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

## DPIDCameraWonder = DPIDCameraBegin +7

*  每日精彩消息 (3.0 新增) 

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

## DPIDCameraLive = DPIDCameraBegin +8

*  直播开关 - 摄像头待机 (3.0 新增) 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| / |

---

## DPIDCameraHangMode = DPIDCameraBegin +9

*  视频模式 - 壁挂或吊顶 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|mode|int|  如何置放：壁挂或吊顶 |


模式定义：
HANG_WALL = 1  壁挂
HANG_CEIL = 2  吊顶

---

## DPIDCameraCoord = DPIDCameraBegin +10

*  视频 - 坐标

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack |

|  value定义 |  类型|   描述 | 
|---|---|---|
|x |int|横坐标|
|y |int|纵坐标|
|r |int|半径|


---