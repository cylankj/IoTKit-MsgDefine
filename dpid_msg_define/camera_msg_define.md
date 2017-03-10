## DPIDCameraBegin = 500
## DPIDCameraWarnEnable = 501

* 设备报警开关配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| 是否开启 |


---

## DPIDCameraWarnTime = 502

*  设备报警时间段配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串 |
 
 
|  value定义 |  类型|   描述 | 
|---|---|---|
|begin_time|int| 开始时间点 ，单位秒|
|end_time|int| 结束时间点 ，单位秒|
|week|int| 每周的星期*， 从低位到高位代表周一到周日。如0b00000001代表周一，0b01000000代表周日 |
 

---

## DPIDCameraWarnSensitivity = 503

*  报警灵敏度配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|sensitivity|int| 灵敏度 0为低SENSITIVITY_LOW, 1为中SENSITIVITY_MIDDLE, 2为高SENSITIVITY_HIGH 默认为中 |

---

## DPIDCameraWarnSound = 504

*  报警提示音配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|sound|int| 报警设备提示音 ：0 是静音， 1是汪汪声，2是警报声|
|sound_long|int| 循环播放时长 |


---

## DPIDCameraWarnMsg = 505 

*  （兼容2.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int| 时间点，单位秒 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|file|int|协商命名规则为：time_id.jpg， id取值范围[1,2,3]。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充128消息下发的数据|

存储路径：                [bucket]/[cid]/[timestamp]_[id].jpg ， 文件名使用图片产生时间，单位秒。

---

## DPIDCameraTimeLapse = 506

*  延迟摄影设置 (3.0 新增) 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|beginTime |int|开始时间，单位秒|
|timeCycle |int| 摄影间隔，单位秒（20 ， 60）|
|timeDuration |int| 摄影时长，单位秒（如86400为24小时）|
|status|int|任务状态：0 表示摄影任务被人为终止; 1 表示任务进行中； 2 表示任务成功完成。 |


---

## DPIDCameraStandby = 508

*  直播开关 - 摄像头待机 (3.0 新增) 
*  APP根据待机参数自行组合控制设备工作模式；即APP需要主动调用MIDRobotSetData接口发送DPIDBaseLED， DPIDCameraWarnEnable ， DPIDBaseLED， DPIDVideoAutoRecord 消息给设备端。
*  该消息不需要发送给设备端。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack |

|  value定义 |  类型|   描述 | 
|---|---|---|
|standby|bool| true：待机，false：正常工作|
|warnEnable|bool| 是否开启报警，见 DPIDCameraWarnEnable = 501 |
|led|bool| 设备指示灯，见 DPIDBaseLED = 209 |
|auto_record|int| 自动录像配置， 见 DPIDVideoAutoRecord = 303 |

---

## DPIDCameraHangMode = 509

*  视频模式 - 壁挂或吊顶 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|mode|int|  如何置放：壁挂或吊顶 |


模式定义：
MODE_TOP  = 0  吊顶
MODE_WALL = 1  壁挂

---

## DPIDCameraCoord = 510

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

## DPIDCameraWarnAndWonder = 511

*  报警消息与每日精彩的收藏关系。
*  使用[MIDRobotSetDataByTime=20216](mid_msg_define/mid_define.md#midrobotsetdatabytime20216)增加关联关系，time 使用 DPIDCameraWarnMsg = 505 消息中的time赋值。
*  使用[MIDRobotGetDataByTime=20218](mid_msg_define/mid_define.md#midrobotgetdatabytime20218)获取关联关系，time 使用 DPIDCameraWarnMsg = 505 消息中的time查询。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|file|int|目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都收藏就是0b111|


---

## DPIDCameraWarnMsgV3 = 512 

*  （3.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int| 时间点，单位秒 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|file|int|协商命名规则为：time_id.jpg， id取值范围[1,2,3]。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 DPIDCloudStorage = 3 消息下发的数据|

存储路径：                [bucket]/cid/[vid]/[cid]/[timestamp]_[id].jpg ， 文件名使用图片产生时间，单位秒。

---

