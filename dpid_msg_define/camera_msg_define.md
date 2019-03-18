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
|face_id|string数组|检测到的物体的标识，例子，检测到A和B：[face_id_A,face_id_B] --20170929 加入faceid
|is_video|int|0-图片报警，1-视频报警 --20181204

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
|x |int|横坐标 x<1920|
|y |int|纵坐标 y<1080|
|r |int|半径   r<1080|
|w |int|分辨率 宽 w<=1920|
|h |int|分辨率 高 h<=1080|

 
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
## DPIDCameraLiveRtmpCtrl = 516

* 720双目摄像机直播推流开关控制指令
* 客户端设置/服务端推送/设备端执行

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 |
|---|---|---|
| url |string| rtmp推流地址。示例：rtmp://a.rtmp.youtube.com/live2|
| enable |int| 特征值： 0 关闭直播； 1 开启直播|
|liveType|int|直播类型：1 facebook; 2 youtube; 3 weibo; 4 rtmp  


---
## DPIDCameraLiveRtmpStatus = 517

* 720双目摄像机直播推流状态上报
* 设备端上报/服务端推送/客户端查询

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 |
|---|---|---|
|liveType|int|直播类型：1 facebook; 2 youtube; 3 weibo; 4 rtmp
| url |string| rtmp推流地址。示例：rtmp://a.rtmp.youtube.com/live2|
| flag |int| 状态特征值： 1 准备直播； 2 直播中； 3 直播结束；|
|timestamp|int|开始直播的时间戳，其它情况置位0
| error |int| 错误特征值： 0 正确； 1 错误；|
---  

## DPIDSetFaceIdStatus = 518

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|face_ids|[]string|面孔标识id|
|status|int| 0 变为陌生人，1 变为熟人, 2 删除，3 清空缓存| 

---
## DPIDCameraWarnArea = 519

* 摄像机侦测区域

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串 |

|  value定义 |  类型|   描述 | 
|---|---|---|
|enable|bool|是否开启|
|rects|array| 侦测区域，如:[[x1,y1,x2,y2],[x1,y1,x2,y2],...] | 

|  rect定义 |  类型|   描述 | 
|---|---|---|
|left|float|左上x|
|top|float|左上y|
|right|float|右下x|
|bottom|float| 右下y |

---

## DPIDCameraInfrared = 520

* 摄像机红外增强识别开关

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool|  是否开启 |

---

## DPIDCameraTakePicture = 521

* 摄像机拍照

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool|  是否拍照 |

---

## DPIDCameraTakePictureAck = 522

* 摄像机拍照响应

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| msgpack字符串 |


|  value定义 |  类型|   描述 | 
|---|---|---|
|ret|int|返回码，0成功，非0失败|
|ossType|int|oss节点|
|time|int64| 拍照时间，单位：秒，照片oss上的存储路径:[cid]/tmp/[time].jpg，如：200000004808/tmp/1511315306.jpg| 
|url|string|oss路径，服务器提供给2.0app使用，设备不用填写|
|width |int|图片分辨率宽度（分辨率为1920*1080，则其值为1920）|
|height|int|图片分辨率高度（分辨率为1920*1080，则其值为1080）|

---

## DPIDCameraWeChatPushCid = 523

* 微信推送开关

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool|  是否开启 |

---

## DPIDCameraInfraRedCid = 524

* 红外夜视状态

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|status|int| 0 自动，1 关闭, 2 开启| 

---

## DPIDCameraUploadImage = 525

* 上传报警大图

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool| true:上传报警大图， false:不上传报警大图| 

---

## DPIDCameraAIWarnMsg = 526 

*  AI设备报警消息

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
|persons|object数组|检测到的人物信息 |

|  person定义 |  类型|   描述 | 
|---|---|---|
|name|string| 名称 |
|sex|string|性别，男：male，女：female|
|age|string|年龄|

---

## DPIDCameraAddPersonMsg = 527 

*  AI添加熟人消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|name|string|  姓名 |

---

## DPIDCameraWarnVideoMsg = 528 

*  （兼容2.0版设备）设备报警消息视频流

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|time| int| 时间点，单位秒 |
|is_record|int|摄像头是否在录像中。客户端【消息中心】->【历史视频】按钮根据该字段显示。注：由于正在录制的视频需要半小时后才能查看，所以客户端对最新报警与当前时间比对，小于半小时不显示按钮|
|regionType|int|enum{regionTypeOSSCN = 1, regionTypeOSSUS, regionTypeOSSEU, regionTypeOSSSG}。填充128消息下发的数据|

存储路径：                [bucket]/[cid]/[timestamp].xxx ， 文件名使用视频产生时间，单位秒。

---

## DPIDCameraAIFaceSizeMsg = 529

*  人脸识别尺寸设置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|x| int| x轴像素大小 |
|y| int| Y轴像素大小 |

---

## DPIDCameraWarnVideoAndImgType = 530 

*  （兼容2.0版设备）设备报警消息视频流和图片选择类型

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|type|int|  1:图片报警消息  2:视频报警消息|

---

## DPIDCameraFaceEnable = 531

* AI检测开关配置（即AI设备开启人脸抓拍功能）

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|enable|bool| 是否开启 |

---

## DPIDCameraFaceNumber = 532

* AI摄像头单机库容

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|used|int| 以使用 |
|total|int| 总量 |

---
## DPIDCameraGpsEnable = 533

* 上报gps信息开关配置（设备端根据这个值来决定是否启用上报GPS数据）

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| 启用GPS上报:0--不启用，1--启用 |

---
## DPIDCameraName = 534

* 设备名称（客户要给设备写一个唯一标识，故需要将webapp设置的设备名称推送给设备）

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| 设备名称|

---

## DPIDPersonFeatrue = 535

* 注册人脸特征值

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|  value定义 |  类型|   描述 | 
|---|---|---|
|person_id|string| -- |
|person_name|string| 人物名称 |
|age|string| 年龄 |
|sex|string| 性别 |
|tags|[]string| 人物标签，字符串数组 |
|faces|[]face| 人脸属性 |

|  face定义 |  类型|   描述 | 
|---|---|---|
|face_id|string| -- |
|featrues|[]float32| 特征值 |

---

## DPIDCameraWebGateway = 536

* 设备web网关开关(萝卜头后台管理中配置)

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| web网关:0--不启用，1--启用 |

---

## DPIDCameraShakingMachine = 537

* 摇头机方向控制，透传消息

|data定义|类型|描述|
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|value定义|类型|描述 |
|---|---|---|
|direction|int|方向|
|angle|int|角度|

---

## DPIDCameraScript = 538

* 下发脚本给设备(萝卜头后台管理中配置)

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| 脚本文本 |

---

## DPIDCameraShakingEnd = 539

* 摇头机方向控制，透传消息(摇头机"是否到头")

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|int| msgpack字符串 |

---

## DPIDCameraTemp = 540

* 设备端临时记录数据，查验设备问题用

|  data定义 |    类型| 描述 |
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| 设备端自定义类型 |

---
## DPIDCameraFocus = 541

* 设备调焦（在webapp上面操作）

|data定义|类型|描述|
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|value定义|类型|描述 |
|---|---|---|
|zoom|int|变倍|
|focus|int|聚焦|
|aperture |int|光圈|

---
## DPIDPreset = 542

* 设备预置位

|data定义|类型|描述|
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string|  msgpack字符串|


|value定义|类型|描述 |
|---|---|---|
|type|int|1-生成新的预置位，2-使用已存在预置位,3-删除预置位|
|index|int|预置位序号|

---