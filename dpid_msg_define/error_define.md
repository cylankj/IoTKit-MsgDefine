    // EOK = 0 成功
    
    ------

### P2P 错误码

    ErrorP2PDns = 1
    
    ErrorP2PSocket = 2
    
    ErrorP2PCallerRelay = 3
    
    ErrorP2PCallerStun = 4
 
    ErrorP2PCalleeStun = 5
    
    ErrorP2PCalleeWaitCallerCheckNetTimeOut = 6

    ErrorP2PPeerTimeOut = 7

    ErrorP2PUserCancel = 8
    
    ErrorP2PConnectionCheck = 9
    
    ErrorP2PChannel = 10
    // 对端断开
    ErrorP2PDisconetByUser = 11
    
    ErrorP2PUnKnown12 = 12
    // 对端超时断开  
    ErrorP2PRTCPTimeout = 13

    ------

    // 对端不在线
    ErrorVideoPeerNotExist = 100 

    // 对端断开
    ErrorVideoPeerDisconnect = 101 
    
    // 正在查看中
    ErrorVideoPeerInConnect = 102
    
    // 本端未登陆
    ErrorVideoNotLogin = 103

    -----

### 通用类
    // 未知错误
    ErrorUnknown = 120
    
    // 数据库错误
	ErrorDataBase = 121
    
    // 未登录或无效的会话，客户端和设备端通用
	ErrorInvalidSession = 122
   
    // 消息格式错误
    ErrorInvalidMsg = 123
    
    // 消息速率超过限制，请控制合理流速（100个每秒）
    ErrorMsgRateExceedLimit = 124

    ------

### 设备端鉴权
    // 厂家CID达到配额，请到萝卜头平台申请配额。关联消息：注册。
	ErrorCIDExceedQuota = 140
    
    // SN签名验证失败， sn、signature及公钥不匹配。 关联消息：登陆。
	ErrorCIDSNVerifyFailed = 141
	
	// 公钥不存在, 请到萝卜头平台上传您的公钥（注意，请保管好您的私钥，不要泄漏）。关联消息：登陆。
	ErrorPublicKeyNotExist = 142
	
	// CID重复。关联消息：登陆。
    ErrorCIDIsDuplicate = 143
    
    // ErrorCIDNotRegistered CID未注册
	ErrorCIDNotRegistered = 144
    
    ----
    
### 设备端功能类

    // 双鱼眼摄像头电量低于5%
    ErrorCIDLowBattery = 150
    
    ---
    
### 客户端登陆类.
    // vid, bundleID, vkey校验失败。
	ErrorLoginInvalidVKey = 160
    
    // 帐号或密码错误。
	ErrorLoginInvalidPass = 161
	
    // 第三方帐号登陆： access_token 验证失败。
	ErrorOpenLoginInvalidToken = 162
    
    // SDK正在初始化，请等待
    ErrorIniting = 163
    ---

### 客户端帐号类.
    // 短信验证码错误。
	ErrorSMSCodeNotMatch = 180  
    
	// 短信验证码超时。
	ErrorSMSCodeTimeout = 181
    
    // 帐号不存在。
	ErrorAccountNotExist = 182
	
    // 帐号已存在。
	ErrorAccountAlreadyExist = 183
    
    // 原始密码与新密码相同。关联消息：修改密码。
	ErrorSamePass = 184
    
    // 原密码错误。关联消息：修改密码。
	ErrorInvalidPass = 185
    
    // 此手机号码已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorPhoneExist = 186
    
	// 此邮箱已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorEmailExist = 187
    
    // 手机号码不合规
	ErrorIsNotPhone = 188
	
	// 邮箱账号不合规
	ErrorIsNotEmail = 189
	
    // 忘记密码时，邮箱或手机号不存在时报错
    ErrorInvalidPhoneNumber = 190
	
	// 第三方账号设置密码超时
	ErrorSetPassTimeout = 191
	
	// 十分钟内获取验证码超过3次
	ErrorGetCodeTooFrequent = 192
	
    
    ----
    
### 客户端绑定设备类.
    // CID不存在。关联消息：客户端绑定。
    ErrorCIDNotExist = 200
    
    // 绑定中，正在等待摄像头上传随机数与CID关联关系，随后推送绑定通知
	ErrorCIDBinding = 201
    
    // 设备别名已存在。
	ErrorCIDAliasExist = 202
	
    // 设备未绑定，不可操作未绑定设备。
	ErrorCIDNotBind = 203
	
	// 设备已经被其他账号绑定。
	ErrorCIDBinded = 204
    
    ----
    
    // 客户端分享设备类.
    // 此帐号还没有注册。
	ErrorShareInvalidAccount = 220
    
	// 此帐号已经分享。
	ErrorShareAlready = 221
    
    // 您不能分享给自己。
	ErrorShareToSelf = 222
    
    // 设备分享，被分享账号不能超过5个。
	ErrorShareExceedsLimit = 223
    
    ----
    
### 客户端亲友关系类.
	// 已经是好友关系
	ErrorFriendAlready = 241
    
	// 不能添加自己为好友
	ErrorFriendToSelf = 242
    
	// 好友请求消息过期
	ErrorFriendInvalidRequest = 243
     
    ----
    
    // 云存储 获取临时安全凭证
    // 获取失败
    ErrorGetCredentials = 260

    
    ----

### APP 端错误号
    // 非法的调用，ex: 摄像头/APP 调用对方才有的功能
    ErrorInvalidMethod = 1000
    
    // 非法的调用参数，ex: 登陆不带用户名 
    ErrorInvalidParameter = 1001

    // 非法的状态， ex: 和摄像头在连接状态再次调用连接
    ErrorInvalidState = 1002
   
    // 解析域名失败
    ErrorResolve = 1003

    // 连接服务器失败
    ErrorConnect = 1004
    
    
    ---
    
### DP 操作错误号
    // 每日精彩收藏夹达到上线（50条）
    ErrorWonderFavoriteExceedLimit = 1050
    
    
### 萝卜头平台 OSSAPI 操作错误号
    // 设备未开启云存储服务
    ErrorOSSAPIDeviceNotOpen = 1100    
    
    // 设备云存储服务过期
    ErrorOSSAPIDeviceExpired = 1101    
    
    // 用户关闭云存储服务
    ErrorOSSAPIUserOFFUploading = 1102    

-----

### SD卡错误码
    // 未知错误
    ErrorSDUnknown = 2001   

    // 输入参数有误
    ErrorSDInvParam = 2002   

    // 没有空闲空间
    ErrorSDNoSpace = 2003   

    // 没有可用的存储设备
    ErrorSDNoDevice = 2004   

    // 要写入的帧数据长度过长，簇中放不下
    ErrorSDTooLarge = 2005   

    // 没有记录
    ErrorSDNoRecords = 2006   

    // 录像中不能进行一些操作
    ErrorSDRecording = 2007   

    // 格式化过程中
    ErrorSDFormating =  2008   

    // 写失败
    ErrorSDWrite = 2009   

    // 内存申请失败
    ErrorSDNoMemory = 2010  

    // 读失败
    ErrorSDRead = 2011  

    // 检索/读取过程中不能进行一些操作
    ErrorSDOperating = 2012  

    // 列表检索过程中不能进行一些操作
    ErrorSDListSearching = 2013  

    // 已存在句柄
    ErrorSDExistHandle = 2014  

    // 要写入的帧pts异常
    ErrorSDInvPTS = 2015  

    // 存储设备上的文件系统过旧
    ErrorSDFSVersionOld = 2020  

    // 存储设备上的文件系统较新
    ErrorSDFSVersionNew = 2021  

    // 文件系统无法识别
    ErrorSDFSDamaged = 2022  

    // 存储设备读写出错
    ErrorSDFSReadWrite = 2023  

    // 未正常关闭存储设备(需要进行断电恢复)
    ErrorSDFSDirty = 2024  

    // 文件系统未初始化或已关闭
    ErrorSDFSInitialized = 2025  

    // 文件系统索引块异常(需要进行数据恢复)
    ErrorSDFIDXAbnormal = 2026  
    
    // 历史录像已读完
    ErrorSDHistoryAll = 2030

    // 历史录像读取失败
    ErrorSDFileIO = 2031
    
    // 历史录像卡读取失败,同 ErrorSDRead
    ErrorSDIO = 2032

