# 通用消息概述

| MID                                                                   |描述                       |  
|-------                                                                         |-----------------|
| [MIDRobotGetData = 20200](open_msg_define.md#midrobotgetdata-20200)            | 获取数据         |
| [MIDRobotGetDataRsp = 20201](open_msg_define.md#midrobotgetdatarsp-20201)      | 获取数据响应     |
| [MIDRobotSetData = 20202](open_msg_define.md#midrobotsetdata-20202)            | 设置数据         | 
| [MIDRobotSetDataRsp = 20203](open_msg_define.md#midrobotsetdatarsp-20203)      | 设置数据响应     |
| [MIDRobotDelData = 20204](open_msg_define.md#midrobotdeldata-20204)            | 删除数据        |
| [MIDRobotDelDataRsp = 20205](open_msg_define.md#midrobotdeldatarsp-20205)      | 删除数据响应    |
| [MIDRobotCountData = 20206](open_msg_define.md#midrobotcountdata-20206)        | 未读消息计数     |
| [MIDRobotCountDataRsp = 20207](open_msg_define.md#midrobotcountdatarsp-20207)  | 未读消息计数响应  |
| [MIDRobotGetDataEx = 20208](open_msg_define.md#midrobotgetdataex-20208)        | 组合查询         |
| [MIDRobotGetDataExRsp = 20209](open_msg_define.md#midrobotgetdataexrsp-20209)  | 组合查询响应     |
| [MIDRobotSyncData = 20210](open_msg_define.md#midrobotsyncdata-20210)          | 同步消息：用于多终端之间的操作同步 |
| [MIDRobotPushData = 20211](open_msg_define.md#midrobotpushdata-20211)          | 推送消息：用于设备端触发的推送消息 |
  

# 预定义消息概述

## 一、全局配置类定义 DPIDCFGBegin = 0

|id     |描述                  |数据类型    |  
|-------|-------------------|----------|
| [DPIDRelayServer = DPIDCFGBegin+1](server_cfg_msg_define.md#dpidrelayserver-dpidcfgbegin1)             | RelayServer配置      | string     |
| [DPIDHeartbeat = DPIDCFGBegin+2](server_cfg_msg_define.md#dpidheartbeat-dpidcfgbegin2)                 | 心跳配置        | string     | 
| [DPIDClientUpgradeConfig = DPIDCFGBegin+5](server_cfg_msg_define.md#dpidclientupgradeconfig-dpidcfgbegin5) | 客户端升级检测地址  | string     |
 



## 二、局域网消息定义 DPIDUDPBegin = 100


## 三、基础功能定义 DPIDBaseBegin = 200


| id                                                                                              |描述                               |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值       | 是否展示图表 | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                          |----------                         |---------- |----------  |---------- |------------  |---------          |---------     |------        |------|
| [DPIDBaseNet = DPIDBaseBegin +1](base_msg_define.md#dpidbasenetdpidbasebegin-1)                 | 网络类型                          | 否        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [DPIDBaseMac = DPIDBaseBegin +2](base_msg_define.md#dpidbasemac-dpidbasebegin-2)                | MAC地址                           | 是        | string     | 是        | 显示         | 无                |无            | 否           | 否 |
| [DPIDBaseSD = DPIDBaseBegin +3](base_msg_define.md#dpidbasesd-dpidbasebegin-3)                  | 是否接入SD卡                      | 是        | bool       | 是        | 显示         | 无                |无            | 否           | 是 |
| [DPIDBaseSDStatus = DPIDBaseBegin +4](base_msg_define.md#dpidbasesdstatus-dpidbasebegin-4)      | SD卡容量信息                      | 否        | string     | 是        | 显示（实时）        | 无                |无            | 否           | 是 |
| [DPIDBasePower = DPIDBaseBegin +5](base_msg_define.md#dpidbasepower-dpidbasebegin-5)            | 是否连接电源线                    | 是        | bool       | 是        | 显示         | 无                |无            | 否           | 是 |
| [DPIDBaseBattery = DPIDBaseBegin +6](base_msg_define.md#dpidbasebattery-dpidbasebegin-6)        | 剩余电量                          | 否        | int        | 是        | 显示（实时）         | 无                |无            | 否           | 是 |
| [DPIDBaseVersion = DPIDBaseBegin +7](base_msg_define.md#dpidbaseversion-dpidbasebegin-7)        | 软件版本号                        | 是        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [DPIDBaseSysVersion = DPIDBaseBegin +8](base_msg_define.md#dpidbasesysversion-dpidbasebegin-8)  | 系统版本号                        | 是        | string     | 是        | 显示         | 无                |无            | 否           | 是 |
| [DPIDBaseLED = DPIDBaseBegin +9](base_msg_define.md#dpidbaseled-dpidbasebegin-9)                | 设备指示灯配置                    | 否        | bool        | 是        | 控制         | 无                |无            | 是           | 否 |
| [DPIDBaseUptime = DPIDBaseBegin +10](base_msg_define.md#dpidbaseuptime-dpidbasebegin-10)        | 开机时间                         | 否        | int        | 是        | 显示         | 无                |无            | 否           | 否 |
| [DPIDBaseClientLog = DPIDBaseBegin +11](base_msg_define.md#dpidbaseclientlog-dpidbasebegin-11)  | 客户端上报日志消息（提交WIFI信息） | 否        | string     | 否        | 无           | 无                |无            | 否           | 否 |
| [DPIDBaseCidLog = DPIDBaseBegin +12](base_msg_define.md#dpidbasecidlog-dpidbasebegin-12)        | 设备上报日志消息                  | 否        | string     | 否        | 无           | 无                |无            | 否           | 否 |
| [DPIDBaseP2PVersion = DPIDBaseBegin +13](base_msg_define.md#dpidbasep2pversion-dpidbasebegin-13)| 设备P2P版本号                     | 是        | int        | 否        | 无           | 无                |无            | 否           | 是 |
| [DPIDBaseTimezone = DPIDBaseBegin +14](base_msg_define.md#dpidbaseled-dpidbasebegin-14)         | 设备时区配置                      | 否        | int        | 是        | 控制         | 是                |无            | 是           | 否 |
| [DPIDBaseIsPushFlow = DPIDBaseBegin +15](base_msg_define.md#dpidbaseled-dpidbasebegin-15)       | 设备推流配置                       | 是        | bool        | 是        | 控制         | 是                |无            | 是           | 否 |
| [DPIDBaseIsNTSC = DPIDBaseBegin +16](base_msg_define.md#dpidbaseled-dpidbasebegin-16)           | 设备电流频率配置                   | 是        | bool        | 是        | 控制         | 是                |无            | 是           | 否 |
| [DPIDBaseIsMobile = DPIDBaseBegin +17](base_msg_define.md#dpidbaseled-dpidbasebegin-17)         | 设备优先使用移动网络配置            | 是        | bool        | 是        | 控制         | 是                |无            | 是           | 否 |
| [DPIDBaseFormatSD = DPIDBaseBegin +18](base_msg_define.md#dpidbaseled-dpidbasebegin-18)         | 格式化SD卡                         | 否        | 无        | 是        | 控制         | 是                |无            | 否           | 否 |

## 四、音视频功能定义 DPIDVideoBegin = 300
| id                                                                                                  |描述                            |是否唯一   |数据类型      |APP可见   |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                      |---------- |----------  |----------|------------  |---------      |---------        |------                 |------|
| [DPIDVideoMic = DPIDVideoBegin +1](video_msg_define.md#dpidvideomic-dpidvideobegin-1)               | [未启用]控制设备麦克风           | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoSpeaker = DPIDVideoBegin +2](video_msg_define.md#dpidvideospeaker-dpidvideobegin-2)       | [未启用]控制设备喇叭             | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoAutoRecord = DPIDVideoBegin +3](video_msg_define.md#dpidvideoautorecord-dpidvideobegin-3) | 自动录像配置                    | 否        | int        | 是       | 控制         | 无            |无               | 是                    | 否 |
| [DPIDVideoDirection = DPIDVideoBegin +4](video_msg_define.md#dpidvideodirection-dpidvideobegin-4)   | 控制设备画面翻转                 | 否        | int        | 是       | 控制         | 无            |无               | 否                    | 否|

## 五、门铃功能定义 DPIDBellBegin = 400
| id                                                                                                  |描述                             |是否唯一   |数据类型     |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                       |----------|----------  |---------- |------------ |---------     |---------       |------               |------|
| [DPIDBellCallMsg = DPIDBellBegin +1](bell_msg_define.md#dpidbellcallmsg-dpidbellbegin-1)            | 门铃呼叫状态                     | 否        | string    | 是         | 显示        | 无           |有              | 否                   | 是 |
| [DPIDBellLeaveMsg = DPIDBellBegin +2](bell_msg_define.md#dpidbellleavemsg-dpidbellbegin-2)          | 留言设置(门铃)                   | 否       | int       | 是         | 控制        | 有           |无              | 是                   | 否 |


## 六、摄像头功能定义 DPIDCameraBegin = 500
| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                                              |----------        |----------|----------|----------|------------   |---------     |---------|------|------|
| [DPIDCameraWarnEnable = DPIDCameraBegin +1](camera_msg_define.md#dpidcamerawarnenable-dpidcamerabegin-1)            | 报警开关配置      | 是        | bool     | 是        | 控制         | 是           |无              | 是 | 否 |
| [DPIDCameraWarnTime = DPIDCameraBegin +2](camera_msg_define.md#dpidcamerawarntime-dpidcamerabegin-2)                | 报警时间段配置    | 否        | string     | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSensitivity  = DPIDCameraBegin +3](camera_msg_define.md#dpidcamerawarnsensitivity-dpidcamerabegin-3) | 报警灵敏度配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSound = DPIDCameraBegin +4](camera_msg_define.md#dpidcamerawarnsound-dpidcamerabegin-4)              | 报警提示音配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnMsg = DPIDCameraBegin +5](camera_msg_define.md#dpidcamerawarnmsg-dpidcamerabegin-5)                  | 报警消息          | 否        | string     | 是        | 显示         | 无         |有               | 否 | 是 |
| [DPIDCameraTimeLapse = DPIDCameraBegin +6](camera_msg_define.md#dpidcameratimelapse-dpidcamerabegin-6)              | 延迟摄影设置      | 否        | string     | 是        | 控制         | 有         |无               | 是 | 否 |
| [DPIDCameraWonder = DPIDCameraBegin +7](camera_msg_define.md#dpidcamerawonder-dpidcamerabegin-7)                    | 每日精彩消息       | 否       | string     | 是        | 显示         | 无         |无               | 否 | 否 |
| [DPIDCameraLive = DPIDCameraBegin +8](camera_msg_define.md#dpidcameralive-dpidcamerabegin-8)                        | 是否开启直播 (摄像头待机设置)  | 是 | bool   | 是        | 控制         | 有        |无               | 是 | 否 |
| [DPIDCameraHangMode = DPIDCameraBegin +9](camera_msg_define.md#dpidcamerahangmode-dpidcamerabegin-9)                | 视频模式 (壁挂或吊顶)  | 是    | int        | 是        | 控制         | 有        |无                | 是 | 否 |
| [DPIDCameraCoord = DPIDCameraBegin +10](camera_msg_define.md#dpidcameracoord-dpidcamerabegin-10)                    | 视频坐标          | 是        | string     | 是        | 控制         | 有        |无                | 是 | 否 |


