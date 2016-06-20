## MIDCameraWarnEnable = MIDCameraBegin +1

* 设备报警开关配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|int| 是否开启 |


---

## MIDCameraWarnTime = MIDCameraBegin +2

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
 
---

## MIDCameraWarnSensitivity = MIDCameraBegin +3

*  报警灵敏度配置

---

## MIDCameraWarnSound = MIDCameraBegin +4

*  报警提示音配置

---

## MIDCameraWarnMsg = MIDCameraBegin +5 

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

## MIDCameraTimeLapse = MIDCameraBegin +6

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

## MIDCameraWonder = MIDCameraBegin +7

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

## MIDCameraStandby = MIDCameraBegin +8

*  摄像头待机 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| / |

---