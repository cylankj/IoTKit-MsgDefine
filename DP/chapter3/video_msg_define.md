

## MIDVideoMic = MIDVideoBegin +1

*  控制设备麦克风

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|int64| int| 时间点 |
|mike|bool| 开启/关闭麦克风 |
  
 ---

## MIDVideoSpeaker = MIDVideoBegin +2

*  控制设备喇叭

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|speaker|bool| 开启/关闭喇叭 |

  
 ---

## MIDVideoAutoRecord = MIDVideoBegin +3
 
* 自动录像配置


 ---

## MIDVideoDirection = MIDVideoBegin +4

*  控制设备画面翻转

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|direction|int| 0 默认正向 |
 
  
---