# 预定义消息概述

## 一、全局配置类定义 MIDCFGBegin = 0

|id     |描述                  |数据类型    |  
|-------|-------------------|----------|
| [MIDRelayServerDP = MIDCFGBegin+1](server_cfg_msg_define.md#midrelayserverdp-midcfgbegin1)     | RelayServer配置      | string     |
| [MIDMsgServerDP = MIDCFGBegin+2](server_cfg_msg_define.md#midmsgserverdp-midcfgbegin2)     | MsgServer配置        | string     | 
| [MIDCidOSSConfigDP = MIDCFGBegin+3](server_cfg_msg_define.md#midcidossconfigdp-midcfgbegin3)     | CidOSSConfig配置     | string     | 
| [MIDClientOSSConfigDP = MIDCFGBegin+4](server_cfg_msg_define.md#midclientossconfigdp-midcfgbegin4)     | ClientOSSConfig配置  | string     | 



## 二、局域网消息定义 MIDUDPBegin = 100


## 三、基础功能定义 MIDBaseBegin = 200


| id                                                                                          |描述                               |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值       | 是否展示图表 | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                      |----------                         |---------- |----------  |---------- |------------  |---------          |---------     |------        |------|
| [MIDBaseNet = MIDBaseBegin +1](base_msg_define.md#midbasenetmidbasebegin-1)                 | 网络类型                          | 否        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseMac = MIDBaseBegin +2](base_msg_define.md#midbasemac-midbasebegin-2)                | MAC地址                           | 是        | string     | 是        | 显示         | 无                |无            | 否           | 否 |
| [MIDBaseSD = MIDBaseBegin +3](base_msg_define.md#midbasesd-midbasebegin-3)                  | 是否接入SD卡                      | 否        | bool       | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseSDStatus = MIDBaseBegin +4](base_msg_define.md#midbasesdstatus-midbasebegin-4)      | SD卡容量信息                      | 否        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBasePower = MIDBaseBegin +5](base_msg_define.md#midbasepower-midbasebegin-5)            | 是否连接电源线                    | 否        | bool       | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseBattery = MIDBaseBegin +6](base_msg_define.md#midbasebattery-midbasebegin-6)        | 剩余电量                          | 否        | int        | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseVersion = MIDBaseBegin +7](base_msg_define.md#midbaseversion-midbasebegin-7)        | 软件版本号                        | 否        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseSysVersion = MIDBaseBegin +8](base_msg_define.md#midbasesysversion-midbasebegin-8)  |系统版本号                         | 否        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [MIDBaseLED = MIDBaseBegin +9](base_msg_define.md#midbaseled-midbasebegin-9)                | 设备指示灯配置                    | 否        | int        | 是        | 控制         | 无                |无            | 是           | 否 |
| [MIDBaseUptime = MIDBaseBegin +10](base_msg_define.md#midbaseuptime-midbasebegin-10)        | 开机时间                          | 否        | int        | 是        | 显示         | 无                |无            | 否           | 否 |
| [MIDBaseClientLog = MIDBaseBegin +11](base_msg_define.md#midbaseclientlog-midbasebegin-11)  | 客户端上报日志消息（提交WIFI信息）| 否        | string     | 否        | 无           | 无                |无            | 否           | 否 |
| [MIDBaseCidLog = MIDBaseBegin +12](base_msg_define.md#midbasecidlog-midbasebegin-12)        | 设备上报日志消息                  | 否        | string     | 否        | 无           | 无                |无            | 否           | 否 |
| [MIDBaseP2PVersion = MIDBaseBegin +13](base_msg_define.md#midbasep2pversion-midbasebegin-13)| 设备P2P版本号                     | 否        | int        | 否        | 无           | 无                |无            | 否           | 是 |
| [MIDBaseTimezoneOffset = MIDBaseBegin +14](base_msg_define.md#midbaseled-midbasebegin-14)   | 设备时区配置                      | 否        | int        | 是        | 控制         | 是                |无            | 是           | 否 |
| [MIDBaseIsPushFlow = MIDBaseBegin +15](base_msg_define.md#midbaseled-midbasebegin-15)       | 设备推流配置                      | 否        | int        | 是        | 控制         | 是                |无            | 是           | 否 |
| [MIDBaseIsNTSC = MIDBaseBegin +16](base_msg_define.md#midbaseled-midbasebegin-16)           | 设备电流频率配置                  | 否        | int        | 是        | 控制         | 是                |无            | 是           | 否 |
| [MIDBaseIsMobile = MIDBaseBegin +17](base_msg_define.md#midbaseled-midbasebegin-17)         | 设备优先使用移动网络配置          | 否        | int        | 是        | 控制         | 是                |无            | 是           | 否 |

## 四、音视频功能定义 MIDVideoBegin = 300
| id                                                                                              |描述                    |是否唯一   |数据类型    |APP可见   |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                          |----------              |---------- |----------  |----------|------------  |---------      |---------        |------                 |------|
| [MIDVideoMic = MIDVideoBegin +1](video_msg_define.md#midvideomic-midvideobegin-1)               | [未启用]控制设备麦克风 | 否        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [MIDVideoSpeaker = MIDVideoBegin +2](video_msg_define.md#midvideospeaker-midvideobegin-2)       | [未启用]控制设备喇叭   | 否        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [MIDVideoAutoRecord = MIDVideoBegin +3](video_msg_define.md#midvideoautorecord-midvideobegin-3) | 自动录像配置           | 否        | int        | 是       | 控制         | 无            |无               | 是                    | 否 |
| [MIDVideoDirection = MIDVideoBegin +4](video_msg_define.md#midvideodirection-midvideobegin-4)   | 控制设备画面翻转       | 否        | int        | 是       | 控制         | 无            |无               | 否                    | 否|

## 五、门铃功能定义 MIDBellBegin = 400
| id     |描述       |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------|----------|----------|----------|----------|------------ |---------|---------|------|------|
| [MIDBellCallMsg = MIDBellBegin +1](bell_msg_define.md#midbellcallmsg-midbellbegin-1)    | 门铃呼叫状态   | 否   | string         | 是            | 显示         | 无      |有       | 否 | 是 |
| [MIDBellLeaveMsg = MIDBellBegin +2](bell_msg_define.md#midbellleavemsg-midbellbegin-2)    | 留言设置(门铃)     | 否 | int     | 是               | 控制         | 有      |无       | 是 | 否 |


## 六、摄像头功能定义 MIDCameraBegin = 500
| id     |描述       |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------|----------|----------|----------|----------|------------ |---------|---------|------|------|
| [MIDCameraWarnEnable = MIDCameraBegin +1](camera_msg_define.md#midcamerawarnenable-midcamerabegin-1)    | 报警开关配置  | 否        | bool     | 是        | 控制         | 是     |无       | 是 | 否 |
| [MIDCameraWarnTime = MIDCameraBegin +2](camera_msg_define.md#midcamerawarntime-midcamerabegin-2)    | 报警时间段配置  | 否        | string     | 是        | 控制         | 是     |无       | 是 | 否 |
| [MIDCameraWarnSensitivity  = MIDCameraBegin +3](camera_msg_define.md#midcamerawarnsensitivity-midcamerabegin-3)    | 报警灵敏度配置  | 否        | int     | 是        | 控制         | 是     |无       | 是 | 否 |
| [MIDCameraWarnSound = MIDCameraBegin +4](camera_msg_define.md#midcamerawarnsound-midcamerabegin-4)   | 报警提示音配置  | 否        | int     | 是        | 控制         | 是     |无       | 是 | 否 |
| [MIDCameraWarnMsg = MIDCameraBegin +5](camera_msg_define.md#midcamerawarnmsg-midcamerabegin-5)    | 报警消息  | 否        | string     | 是        | 显示         | 无      |有       | 否 | 是 |
| [MIDCameraTimeLapse = MIDCameraBegin +6](camera_msg_define.md#midcameratimelapse-midcamerabegin-6)    | 延迟摄影设置    | 否 | string     | 是        | 控制         | 有      |无       | 是 | 否 |
| [MIDCameraWonder = MIDCameraBegin +7](camera_msg_define.md#midcamerawonder-midcamerabegin-7)    | 每日精彩消息     | 否 | string     | 是        | 显示         | 无      |无       | 否 | 否 |
| [MIDCameraLive = MIDCameraBegin +8](camera_msg_define.md#midcameralive-midcamerabegin-8)    | 是否开启直播 (摄像头待机设置)   | 否 | bool        | 是        | 控制         | 有      |无       | 是 | 否 |


## 七、门磁功能定义 MIDDoorSensorBegin = 600
| id     |描述       |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------|----------|----------|----------|----------|------------ |---------|---------|------|------|
| [MIDDSNoticeMsgEnable = MIDDoorSensorBegin +1](doorsensor_msg_define.md#middsnoticemsgenable-middoorsensorbegin-1)    | 门磁消息通知开关设置  | 否        | bool     | 是        | 控制         | 是     |无       | 是 | 否 |