## 七、门磁功能定义 DPIDDoorSensorBegin = 600
| id     |描述       |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------|----------|----------|----------|----------|------------ |---------|---------|------|------|
| [DPIDDSNoticeMsgEnable = DPIDDoorSensorBegin +1](doorsensor_msg_define.md#dpiddsnoticemsgenable-dpiddoorsensorbegin-1)    | [未启用]门磁消息通知开关设置  | 是        | bool     | 是        | 控制         | 是     |无       | 是 | 否 |


## DPIDDSNoticeMsgEnable = DPIDDoorSensorBegin +1

*  门磁消息通知开关设置 

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|enable|bool| / |

* http://yf.cylan.com.cn:82/redmine/projects/cloudplatform/wiki/%E6%B6%88%E6%81%AF%E5%AE%9A%E4%B9%89-%E6%94%AF%E6%8C%81%E8%90%9D%E5%8D%9C%E5%A4%B4#MIDClientMagSetWarnReq-20

---