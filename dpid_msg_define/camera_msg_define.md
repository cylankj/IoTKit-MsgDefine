## DPIDCameraBegin = 500
## DPIDCameraWarnEnable = 501

* 设备报警开关配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool| 是否开启 |


---

## DPIDCameraWarnTime = 502

*  设备报警时间段配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串 |
 
 
|  value定义 |  类型|   描述 | 
|---|---|---|
|begin_time|int| 开始时间点，距离零点的数值。按位标识，低八位（0-7bit）标识分钟，次低八位（8-15bit）标识小时。示例：00:00, 该值为0|
|end_time|int| 结束时间点，距离零点的数值。按位标识，低八位（0-7bit）标识分钟，次低八位（8-15bit）标识小时。示例：23:59, 二进制为 0b00010111 00111011，该值为5947|
|week|int| 每周的星期*， 从高（7bit）位到低位（0bit）代表周一到周日。0b01000000代表周一,0b00000001代表周日。示例：一,二,三,四,五, 该值为124|
 

---

## DPIDCameraWarnSensitivity = 503

*  报警灵敏度配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|sensitivity|int| 灵敏度 0为低SENSITIVITY_LOW, 1为中SENSITIVITY_MIDDLE, 2为高SENSITIVITY_HIGH 默认为中 |

---

## DPIDCameraWarnSound = 504

*  报警提示音配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
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
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int| 时间点，单位秒 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|file|int|协商命名规则为：time_id.jpg， id取值范围[1,2,3]。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充128消息下发的数据|
|tly|string| 全景设备陀螺仪。'0'俯视, '1' 平视。| 
|objects|int数组| 检测到的物体类型。人1，猫2，狗3，车辆4。例子，检测到人和猫：[1,2]。 | 
|humanNum|int| 检测到的人形的个数。 | 

存储路径：                [bucket]/[cid]/[timestamp]_[id].jpg ， 文件名使用图片产生时间，单位秒。

objects 定义参考：[物体检测枚举类型定义](dpid_msg_define/camera_msg_define.md#物体检测枚举类型定义)

---

## DPIDCameraTimeLapse = 506

*  延迟摄影设置 (3.0 新增) 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
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
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
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
*  2.* 设备仍在使用1114，服务器处理 3.* APP 与 2.* 设备兼容。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|tly|string|全景设备陀螺仪。‘0’俯视, ‘1’ 平视。|

---

## DPIDCameraCoord = 510

*  视频 - 坐标
*  2.* 设备仍在使用1114，服务器处理 3.* APP 与 2.* 设备兼容。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack |

|  value定义 |  类型|   描述 | 
|---|---|---|
|x |int|横坐标|
|y |int|纵坐标|
|r |int|半径|
|w |int|分辨率 宽|
|h |int|分辨率 高|
---

## DPIDCameraWarnAndWonder = 511

*  报警消息 DPIDCameraWarnMsg 与 每日精彩 DPIDAccountWonder 的收藏关系。
*  使用[MIDRobotSetDataByTime=20216](mid_msg_define/mid_define.md#midrobotsetdatabytime20216)。
*  使用[MIDRobotGetDataByTime=20218](mid_msg_define/mid_define.md#midrobotgetdatabytime20218)。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| 时间点， 单位毫秒。 赋值为 DPIDCameraWarnMsg 中的 timeMsec + index (file 字段代表的1，2，4)|
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|ctimeMsec|int64|每日精彩收藏时间， 单位毫秒。 DPIDAccountWonder 中的 timeMsec |


---

## DPIDCameraWarnMsgV3 = 512 

*  （3.0版设备）设备报警消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int| 时间点，单位秒 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|file|int|协商命名规则为：time_id.jpg， id取值范围[1,2,3]。目前有三张图片，用位来表示。第一张0b001。第二张0b010。第三张0b100。三张都有就是0b111|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充 DPIDCloudStorage = 3 消息下发的数据|
|tly|string| 全景设备陀螺仪。'0'俯视, '1' 平视。| 

存储路径：                [bucket]/cid/[vid]/[cid]/[timestamp]_[id].jpg ， 文件名使用图片产生时间，单位秒。

---

## DPIDCameraResolution = 513

* 分辨率

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|Resolution|int| 分辨率 0自动 1标清 2高清 |

## DPIDCameraWarnInterval = 514

* 报警间隔 
* 默认值： 客户端和设备端自设置，服务端不干涉。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|sec|int| 秒 |

## DPIDCameraObjectDetect = 515

* 物体检测
* 默认值： 客户端和设备端自设置，服务端不干涉。

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|objects| int数组 | 开启物体检测的类型。如果数组为空，则不开启。人1，猫2，狗3，车辆4。例子：需要检测人和猫：[1,2]。 |

#### 物体检测枚举类型定义
[
TypePerson = 1
TypeCat = 2
TypeDog = 3
TypeCar = 4
]

---  

