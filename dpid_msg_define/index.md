
## 一、全局配置类定义 DPIDCFGBegin = 0

|id     |描述                  |数据类型    |  
|-------|-------------------|----------|
| [DPIDRelayServer = 1](server_cfg_msg_define.md#dpidrelayserver-dpidcfgbegin-1)             | RelayServer配置      | string     |
| [DPIDHeartbeat = 2](server_cfg_msg_define.md#dpidheartbeat-dpidcfgbegin-2)                 | 心跳配置        | string     |
| [DPIDCloudStorage = 3](server_cfg_msg_define.md#dpidcloudstorage-dpidcfgbegin-3)             | 云存储配置        | string     | 
| [DPIDClientUpgradeConfig = 5](server_cfg_msg_define.md#dpidclientupgradeconfig-dpidcfgbegin-5) | 客户端升级检测地址  | string     |
 



## 二、局域网消息定义 DPIDUDPBegin = 100


## 三、基础功能定义 DPIDBaseBegin = 200


| id                                                                                              |描述                               |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值      | 是否展示图表 | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                          |----------                         |---------- |----------  |---------- |------------  |---------     |---------     |------        |------|
| [DPIDBaseNet = 201](base_msg_define.md#dpidbasenetdpid-201)                | 网络类型                          | 否        | string     | 是        | 显示         | 无             |无            | 否           | 是 |
| [DPIDBaseMac = 202](base_msg_define.md#dpidbasemac-202)                | MAC地址                           | 是        | string     | 是        | 显示         | 无             |无            | 否           | 否 |
| [DPIDBaseFormatSDAck = 203](base_msg_define.md#dpidbaseformatsdack-203)                | 格式化SD卡响应                           | 是        | string     | 是        | 显示         | 无             |无            | 否           | 否 |
| [DPIDBaseSDStatus = 204](base_msg_define.md#dpidbasesdstatus-204)      | SD卡容量信息                      | 否        | string     | 是        | 显示（实时）  | 无              |无            | 否           | 是 |
| [DPIDBasePower = 205](base_msg_define.md#dpidbasepower-205)            | 是否连接电源线                    | 是         | bool       | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseBattery = 206](base_msg_define.md#dpidbasebattery-206)        | 剩余电量                          | 否        | int        | 是        | 显示（实时）  | 无              |无            | 否           | 是 |
| [DPIDBaseVersion = 207](base_msg_define.md#dpidbaseversion-207)        | 软件版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseSysVersion = 208](base_msg_define.md#dpidbasesysversion-208)  | 系统版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseLED = 209](base_msg_define.md#dpidbaseled-209)                | 设备指示灯配置                    | 否         | bool       | 是        | 控制         | 无              |无            | 是           | 否 |
| [DPIDBaseUptime = 210](base_msg_define.md#dpidbaseuptime-210)        | 开机时间                         | 否         | int64        | 是        | 显示         | 无              |无            | 否           | 否 |
| [DPIDBaseCidLog = 212](base_msg_define.md#dpidbasecidlog-212)        | 设备上报日志消息                  | 否         | string     | 否        | 无           | 无              |无            | 否           | 否 |
| [DPIDBaseP2PVersion = 213](base_msg_define.md#dpidbasep2pversion-213)| 设备P2P版本号                     | 是         | int        | 否        | 无           | 无             |无            | 否           | 是 |
| [DPIDBaseTimezone = 214](base_msg_define.md#dpidbasetimezone-214)    | 设备时区配置                      | 否         | int        | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsPushFlow = 215](base_msg_define.md#dpidbaseispushflow-215)| 设备推流配置                      | 是         | bool       | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsNTSC = 216](base_msg_define.md#dpidbaseisntsc-216)        | 设备电流频率配置                   | 是         | bool      | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseIsMobile = 217](base_msg_define.md#dpidbaseismobile-217)    | 设备优先使用移动网络配置           | 是         | bool       | 是        | 控制         | 是              |无            | 是           | 否 |
| [DPIDBaseFormatSD = 218](base_msg_define.md#dpidbaseformatsd-218)    | 格式化SD卡                        | 否         | 无         | 是        | 控制         | 是              |无            | 否           | 否 |
| [DPIDBaseBind = 219](base_msg_define.md#dpidbasebind-219)            | 绑定和解绑记录                        | 否         | string      | 是        | 显示         | 无              |无            | 否           | 否 |
| [DPIDBaseSdkVersion = 220](base_msg_define.md#dpidbasesdkversion-220)        | SDK版本号                        | 是        | string     | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseCtrlLog = 221](base_msg_define.md#dpidbasectrllog-221)        | 开启客户端和设备端日志                        | 是        | string     | 是        | 控制         | 无              |无            | 否           | 是 |
| [DPIDBaseSDInfoOnOff = 222](base_msg_define.md#dpidbasesdinfoonoff-222)                  | 是否插入SD卡及错误的信息                      | 是        | bool       | 是        | 显示         | 无              |无            | 否           | 是 |
| [DPIDBaseIsExistMobile = 223](base_msg_define.md#dpidbaseisexistmobile-223)    | 设备是否存在可用的移动网络配置           | 是         | bool       | 是        | 显示         | 是              |无            | 是           | 否 |
| [DPIDBaseCtrlLogUploadFile = 224](base_msg_define.md#dpidbasectrlloguploadfile-224) | 通知设备端上传日志压缩包                        | 是        | string     | 是        | 控制         | 无              |无            | 否           | 是 |




## 四、音视频功能定义 DPIDVideoBegin = 300
| id                                                                                                  |描述                            |是否唯一   |数据类型      |APP可见   |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                      |---------- |----------  |----------|------------  |---------      |---------        |------                 |------|
| [DPIDVideoMic = 301](video_msg_define.md#dpidvideomic-301)               | [未启用]控制设备麦克风           | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoSpeaker = 302](video_msg_define.md#dpidvideospeaker-302)       | [未启用]控制设备喇叭             | 是        | bool       | 是       | 控制         | 无            |无               | 否                    | 否 |
| [DPIDVideoAutoRecord = 303](video_msg_define.md#dpidvideoautorecord-303) | 自动录像配置                    | 否        | int        | 是       | 控制         | 无            |无               | 是                    | 否 |
| [DPIDVideoDirection = 304](video_msg_define.md#dpidvideodirection-304)   | 控制设备画面翻转                 | 否        | int        | 是       | 控制         | 无            |无               | 否                    | 否|

## 五、门铃功能定义 DPIDBellBegin = 400
| id                                                                                                  |描述                             |是否唯一   |数据类型     |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                              |----------                       |----------|----------  |---------- |------------ |---------     |---------       |------               |------|
| [DPIDBellCallMsg = 401](bell_msg_define.md#dpidbellcallmsg-401)            | 门铃呼叫状态                     | 否        | string    | 是         | 显示        | 无           |有              | 否                   | 是 |
| [DPIDBellLeaveMsg = 402](bell_msg_define.md#dpidbellleavemsg-402)          | 留言设置(门铃)                   | 否       | int       | 是         | 控制        | 有           |无              | 是                   | 否 |
| [DPIDBellCallMsgV3 = 403](bell_msg_define.md#dpidbellcallmsg-403)            | 门铃呼叫状态3.0版                     | 否        | string    | 是         | 显示        | 无           |有              | 否                   | 是 |

## 六、摄像头功能定义 DPIDCameraBegin = 500
| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------                                                                                                              |----------        |----------|----------|----------|------------   |---------     |---------|------|------|
| [DPIDCameraWarnEnable = 501](camera_msg_define.md#dpidcamerawarnenable-501)            | 报警开关配置      | 是        | bool     | 是        | 控制         | 是           |无              | 是 | 否 |
| [DPIDCameraWarnTime = 502](camera_msg_define.md#dpidcamerawarntime-502)                | 报警时间段配置    | 否        | string     | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSensitivity  = 503](camera_msg_define.md#dpidcamerawarnsensitivity-503) | 报警灵敏度配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnSound = 504](camera_msg_define.md#dpidcamerawarnsound-504)              | 报警提示音配置    | 否        | int        | 是        | 控制         | 是         |无               | 是 | 否 |
| [DPIDCameraWarnMsg = 505](camera_msg_define.md#dpidcamerawarnmsg-505)                  | 报警消息          | 否        | string     | 是        | 显示         | 无         |有               | 否 | 是 |
| [DPIDCameraTimeLapse = 506](camera_msg_define.md#dpidcameratimelapse-506)              | 延迟摄影设置      | 否        | string     | 是        | 控制         | 有         |无               | 是 | 否 |
| [DPIDCameraStandby = 508](camera_msg_define.md#dpidcamerastandby-508)                        | 是否开启直播 (摄像头待机设置)  | 是 | bool   | 是        | 控制         | 有        |无               | 是 | 否 |
| [DPIDCameraHangMode = 509](camera_msg_define.md#dpidcamerahangmode-509)                | 视频模式 (壁挂或吊顶)  | 是    | string        | 是        | 控制         | 有        |无                | 是 | 否 |
| [DPIDCameraCoord = 510](camera_msg_define.md#dpidcameracoord-510)                    | 视频坐标          | 是        | string     | 是        | 控制         | 有        |无                | 是 | 否 |
       |无                | 是 | 否 |
| [DPIDCameraWarnAndWonder = 511](camera_msg_define.md#dpidcamerawarnandwonder-511)                    | 报警消息与每日精彩的收藏关系          | 是        | string     | 是        | 控制         | 有        |无                | 是 | 否 |
| [DPIDCameraWarnMsgV3 = 512](camera_msg_define.md#dpidcamerawarnmsgv3-512)                  | 报警消息3.0版          | 否        | string     | 是        | 显示         | 无         |有               | 否 | 是 |

## 七、帐号相关功能定义 DPIDAccountBegin = 600
| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值    | 是否展示图表    |
|-------                                                                                                              |----------        |----------|----------  |----------|------------  |---------     |----------------|
| [DPIDAccountBind = 601](account_msg_define.md#dpidaccountbind-601)                   | 绑定、解绑消息    | 否       | string     | 是        | 显示         | 无           |是              | 
| [DPIDAccountWonder = 602](account_msg_define.md#dpidaccountwonder-602)               | 每日精彩消息      | 否       | string     | 是        | 显示         | 无           |无              |
| [DPIDAccountShare = 603](account_msg_define.md#dpidaccountshare-603)  | 分享或取消分享设备给好友的消息记录| 否         | string     | 是        | 显示           | 无              |无            |
| [DPIDAccountIsShared = 604](account_msg_define.md#dpidaccountisshared-604)  | 被好友分享或取消分享设备的消息记录| 否         | string     | 是        | 显示           | 无              |无            |
| [DPIDAccountLog = 605](account_msg_define.md#dpidaccountlog-605)  | 客户端上报日志消息| 否         | string     | 否        | 无           | 无              |无            |


## 八、系统相关功能定义 DPIDSystemBegin = 700 

| id                                                                                                                  |描述              |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值    | 是否展示图表    |
|-------                                                                                                              |----------        |----------|----------  |----------|------------  |---------     |----------------|
| [DPIDSystemMsg = 701](system_msg_define.md#dpidsystemmsg-701)                       | 系统消息通知    | 否       | string     | 是        | 显示         | 无           |是              |


## 九、企业自定义消息 DPIDUserDefinedBegin = 30000

| id  |  类型 | 描述  |
| ---    |  ---  |  ---  |
| [DPIDUserDefinedBegin = VIDUint32 << 32 + 30001](user_defined_msg.md#dpiduserdefinedbegin)   | uint64 | 自定义消息起始值 |
| [DPIDUserDefinedEnd = VIDUint32 << 32 + 40000](user_defined_msg.md#dpiduserdefinedbegin)   | uint64 | 自定义消息结束值 |

