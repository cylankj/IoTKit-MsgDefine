## DPIDVideoMic = DPIDVideoBegin +1

*  控制设备麦克风

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|int64| int| 时间点 |
|mike|bool| 开启/关闭麦克风 |
  
* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDAudioControl-9
  
---

## DPIDVideoSpeaker = DPIDVideoBegin +2

*  控制设备喇叭

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|speaker|bool| 开启/关闭喇叭 |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDAudioControl-9

 ---

## DPIDVideoAutoRecord = DPIDVideoBegin +3
 
* 自动录像配置

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|auto_record|int|  0 侦测到异常时， 1为24小时启用录像，2 从不录像 |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientCidSetReq-8 

---

## DPIDVideoDirection = DPIDVideoBegin +4

*  控制设备画面翻转

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|direction|int| 0 默认正向，1倒置（旋转180度） |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientCidSetReq-8
 
  
---