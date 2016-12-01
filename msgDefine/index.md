

# 预定义消息概述

## 一、全局配置类定义 DPIDCFGBegin = 0

|id     |描述                  |数据类型    |  
|-------|-------------------|----------|
| [DPIDRelayServer = DPIDCFGBegin + 1](server_cfg_msg_define.md#dpidrelayserver-dpidcfgbegin-1)             | RelayServer配置      | string     |
| [DPIDHeartbeat = DPIDCFGBegin + 2](server_cfg_msg_define.md#dpidheartbeat-dpidcfgbegin-2)                 | 心跳配置        | string     |
| [DPIDCloudStorage = DPIDCFGBegin + 3](server_cfg_msg_define.md#dpidcloudstorage-dpidcfgbegin-3)             | 云存储配置        | string     | 
| [DPIDClientUpgradeConfig = DPIDCFGBegin + 5](server_cfg_msg_define.md#dpidclientupgradeconfig-dpidcfgbegin-5) | 客户端升级检测地址  | string     |
 



## 二、局域网消息定义 DPIDUDPBegin = 100


## 三、基础功能定义 DPIDBaseBegin = 200


| id                                                                                              |描述                               |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值      | 是否展示图表 | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                          |----------                         |---------- |----------  |---------- |------------  |---------     |---------     |------        |------|
| [DPIDBaseNet = DPIDBaseBegin + 1](base_msg_define.md#dpidbasenetdpid-basebegin-1)                | 网络类型                          | 否        | string     | 是        | 显示         | 无             |无            | 否           | 是 |
| [DPIDBaseMac = DPIDBaseBegin + 2](base_msg_define.md#dpidbasemac-dpidbasebegin-2)                | MAC地址                           | 是        | string     | 是        | 显示         | 无             |无            | 否           | 否 |
| [DPIDBaseSD = DPIDBaseBegin + 3](base_msg_define.md#dpidbasesd-dpidbasebegin-3)                  | 是否接入SD卡                      | 是        | bool       | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseSDStatus = DPIDBaseBegin + 4](base_msg_define.md#dpidbasesdstatus-dpidbasebegin-4)      | SD卡容量信息                      | 否        | string     | 是        | 显示（实时）  | 无              |无            | 否           | 是 |
| [DPIDBasePower = DPIDBaseBegin + 5](base_msg_define.md#dpidbasepower-dpidbasebegin-5)            | 是否连接电源线                    | 是         | bool       | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseBattery = DPIDBaseBegin + 6](base_msg_define.md#dpidbasebattery-dpidbasebegin-6)        | 剩余电量                          | 否        | int        | 是        | 显示（实时）  | 无              |无            | 否           | 是 |
| [DPIDBaseVersion = DPIDBaseBegin + 7](base_msg_define.md#dpidbaseversion-dpidbasebegin-7)        | 软件版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseSysVersion = DPIDBaseBegin + 8](base_msg_define.md#dpidbasesysversion-dpidbasebegin-8)  | 系统版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseLED = DPIDBaseBegin + 9](base_msg_define.md#dpidbaseled-dpidbasebegin-9)                | 设备指示灯配置                    | 否         | bool       | 是        | 控制         | 无              |无            | 是           | 否 |
| [DPIDBaseUptime = DPIDBaseBegin + 10](base_msg_define.md#dpidbaseuptime-dpidbasebegin-10)        | 开机时间                         | 否         | int64        | 是        | 显示         | 无              |无            | 否           | 否 |
| [DPIDBaseCidLog = DPIDBaseBegin + 12](base_msg_define.md#dpidbasecidlog-dpidbasebegin-12)        | 设备上报日志消息                  | 否         | string     | 否        | 无           | 无              |无            | 否           | 否 |
| [DPIDBaseP2PVersion = DPIDBaseBegin + 13](base_msg_define.md#dpidbasep2pversion-dpidbasebegin-13)| 设备P2P版本号                     | 是         | int        | 否        | 无           | 无             |无            | 否           | 是 |
| [DPIDBaseTimezone = DPIDBaseBegin + 14](base_msg_define.md#dpidbasetimezone-dpidbasebegin-14)    | 设备时区配置                      | 否         | int        | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsPushFlow = DPIDBaseBegin + 15](base_msg_define.md#dpidbaseispushflow-dpidbasebegin-15)| 设备推流配置                      | 是         | bool       | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsNTSC = DPIDBaseBegin + 16](base_msg_define.md#dpidbaseisntsc-dpidbasebegin-16)        | 设备电流频率配置                   | 是         | bool      | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsMobile = DPIDBaseBegin + 17](base_msg_define.md#dpidbaseismobile-dpidbasebegin-17)    | 设备优先使用移动网络配置           | 是         | bool       | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseFormatSD = DPIDBaseBegin + 18](base_msg_define.md#dpidbaseformatsd-dpidbasebegin-18)    | 格式化SD卡                        | 否         | 无         | 是        | 控制         | 是              |无            | 否           | 否 |
| [DPIDBaseBind = DPIDBaseBegin + 19](base_msg_define.md#dpidbasebind-dpidbasebegin-19)            | 绑定和解绑记录                        | 否         | string      | 是        | 显示         | 无              |无            | 否           | 否 |
| [DPIDBaseSdkVersion = DPIDBaseBegin + 20](base_msg_define.md#dpidbasesdkversion-dpidbasebegin-20)        | SDK版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseCtrlLog = DPIDBaseBegin + 21](base_msg_define.md#dpidbasectrllog-dpidbasebegin-21)        | 开启客户端和设备端日志                        | 是        | string     | 是        | 控制         | 无              |无            | 否           | 是 |


## 四、音视频功能定义 DPIDVideoBegin = 300
| id                                                                                                  |描述                            |是否唯一   |数据类型      |APP可见   |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                      |---------- |----------  |----------|------------  |---------      |---------        |------                 |------|
| [DPIDVideoMic = DPIDVideoBegin + 1](video_msg_define.md#dpidvideomic-dpidvideobegin-1)               | [未启用]控制设备麦克风           | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoSpeaker = DPIDVideoBegin + 2](video_msg_define.md#dpidvideospeaker-dpidvideobegin-2)       | [未启用]控制设备喇叭             | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoAutoRecord = DPIDVideoBegin + 3](video_msg_define.md#dpidvideoautorecord-dpidvideobegin-3) | 自动录像配置                    | 否        | int        | 是       | 控制         | 无            |无               | 是                    | 否 |
| [DPIDVideoDirection = DPIDVideoBegin + 4](video_msg_define.md#dpidvideodirection-dpidvideobegin-4)   | 控制设备画面翻转                 | 否        | int        | 是       | 控制         | 无            |无               | 否                    | 否|

## 五、门铃功能定义 DPIDBellBegin = 400
| id                                                                                                  |描述                             |是否唯一   |数据类型     |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                       |----------|----------  |---------- |------------ |---------     |---------       |------               |------|
| [DPIDBellCallMsg = DPIDBellBegin + 1](bell_msg_define.md#dpidbellcallmsg-dpidbellbegin-1)            | 门铃呼叫状态                     | 否        | string    | 是         | 显示        | 无           |有              | 否                   | 是 |
| [DPIDBellLeaveMsg = DPIDBellBegin + 2](bell_msg_define.md#dpidbellleavemsg-dpidbellbegin-2)          | 留言设置(门铃)                   | 否       | int       | 是         | 控制        | 有           |无              | 是                   | 否 |


## 六、摄像头功能定义 DPIDCameraBegin = 500
| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                                              |----------        |----------|----------|----------|------------   |---------     |---------|------|------|
| [DPIDCameraWarnEnable = DPIDCameraBegin + 1](camera_msg_define.md#dpidcamerawarnenable-dpidcamerabegin-1)            | 报警开关配置      | 是        | bool     | 是        | 控制         | 是           |无              | 是 | 否 |
| [DPIDCameraWarnTime = DPIDCameraBegin + 2](camera_msg_define.md#dpidcamerawarntime-dpidcamerabegin-2)                | 报警时间段配置    | 否        | string     | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSensitivity  = DPIDCameraBegin + 3](camera_msg_define.md#dpidcamerawarnsensitivity-dpidcamerabegin-3) | 报警灵敏度配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSound = DPIDCameraBegin + 4](camera_msg_define.md#dpidcamerawarnsound-dpidcamerabegin-4)              | 报警提示音配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnMsg = DPIDCameraBegin + 5](camera_msg_define.md#dpidcamerawarnmsg-dpidcamerabegin-5)                  | 报警消息          | 否        | string     | 是        | 显示         | 无         |有               | 否 | 是 |
| [DPIDCameraTimeLapse = DPIDCameraBegin + 6](camera_msg_define.md#dpidcameratimelapse-dpidcamerabegin-6)              | 延迟摄影设置      | 否        | string     | 是        | 控制         | 有         |无               | 是 | 否 |
| [DPIDCameraLive = DPIDCameraBegin + 8](camera_msg_define.md#dpidcameralive-dpidcamerabegin-8)                        | 是否开启直播 (摄像头待机设置)  | 是 | bool   | 是        | 控制         | 有        |无               | 是 | 否 |
| [DPIDCameraHangMode = DPIDCameraBegin + 9](camera_msg_define.md#dpidcamerahangmode-dpidcamerabegin-9)                | 视频模式 (壁挂或吊顶)  | 是    | int        | 是        | 控制         | 有        |无                | 是 | 否 |
| [DPIDCameraCoord = DPIDCameraBegin + 10](camera_msg_define.md#dpidcameracoord-dpidcamerabegin-10)                    | 视频坐标          | 是        | string     | 是        | 控制         | 有        |无                | 是 | 否 |


## 七、帐号相关功能定义 DPIDAccountBegin = 600
| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值    | 是否展示图表    |
|-------                                                                                                              |----------        |----------|----------  |----------|------------  |---------     |----------------|
| [DPIDAccountBind = DPIDAccountBegin + 1](account_msg_define.md#dpidaccountbind-dpidaccountbegin-1)                   | 绑定、解绑消息    | 否       | string     | 是        | 显示         | 无           |是              | 
| [DPIDAccountWonder = DPIDAccountBegin + 2](account_msg_define.md#dpidaccountwonder-dpidaccountbegin-2)               | 每日精彩消息      | 否       | string     | 是        | 显示         | 无           |无              |
| [DPIDAccountShare = DPIDAccountBegin + 3](account_msg_define.md#dpidaccountshare-dpidaccountbegin-3)  | 分享或取消分享设备给好友的消息记录| 否         | string     | 是        | 显示           | 无              |无            |
| [DPIDAccountIsShared = DPIDAccountBegin + 4](account_msg_define.md#dpidaccountisshared-dpidaccountbegin-4)  | 被好友分享或取消分享设备的消息记录| 否         | string     | 是        | 显示           | 无              |无            |
| [DPIDAccountLog = DPIDAccountBegin + 5](account_msg_define.md#dpidaccountlog-dpidaccountbegin-5)  | 客户端上报日志消息| 否         | string     | 否        | 无           | 无              |无            |


## 八、系统相关功能定义 DPIDSystemBegin = 700 

| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值    | 是否展示图表    |
|-------                                                                                                              |----------        |----------|----------  |----------|------------  |---------     |----------------|
| [DPIDSystemMsg = DPIDSystemBegin + 1](system_msg_define.md#dpidsystemmsg-dpidsystembegin-1)                       | 系统消息通知    | 否       | string     | 是        | 显示         | 无           |是              |


# 企业自定义消息 DPIDUserDefinedBegin = 30000

## 一、自定义消息定义 

| id  |  类型 | 描述  |
| ---    |  ---  |  ---  |
| [DPIDUserDefinedBegin = VIDUint32 << 32 + 30001](msg_user_defined.md#dpiduserdefinedbegin)   | uint64 | 自定义消息起始值 |
| [DPIDUserDefinedEnd   = VIDUint32 << 32 + 40000](msg_user_defined.md#dpiduserdefinedbegin)   | uint64 | 自定义消息结束值 |

