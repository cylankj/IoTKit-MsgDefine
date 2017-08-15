## DPIDVideoBegin = 300
## DPIDVideoMic = 301

*  控制设备麦克风

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|int64| int| 时间点 |
|mike|bool| 开启/关闭麦克风 |

  
---

## DPIDVideoSpeaker = 302

*  控制设备喇叭

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|speaker|bool| 开启/关闭喇叭 |

 ---

## DPIDVideoAutoRecord = 303
 
* 自动录像配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|auto_record|int|  0 侦测到异常时， 1为24小时启用录像，2 从不录像 |
 

---

## DPIDVideoDirection = 304

*  控制设备画面翻转

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|direction|int| 0 默认正向，1倒置（旋转180度） |

 
  
---
## DPIDViewVideoRecord = 305

*  控制查看时录像功能开关状态

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|recordEnable|bool| 0 关闭，1开启|

 
  
---