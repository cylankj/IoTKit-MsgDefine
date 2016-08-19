    // EOK 成功
	ErrorOK = 0
    
    // P2P 错误码
    ErrorP2PDns = 1
    // 旧码 P2P_ERROR_DNS,
    
    ErrorP2PSocket = 2
    // 旧码 P2P_ERROR_SOCKET,
    
    ErrorP2PCallerRelay = 3
    // 旧码 P2P_ERROR_CALLER_RELAY,
    
    ErrorP2PCallerStun = 4
    // 旧码 P2P_ERROR_CALLER_STUN,
    
    ErrorP2PCalleeStun = 5
    // 旧码 P2P_ERROR_CALLEE_STUN,
    
    ErrorP2PCalleeWaitCallerCheckNetTimeOut = 6
    // 旧码 P2P_ERROR_CALLEE_WAIT_CALLER_CHECKNET_TIMEOUT,
    
    ErrorP2PPeerTimeOut = 7
    // 旧码 P2P_ERROR_PEER_TIMEOUT,
    
    ErrorP2PUserCancel = 8
    // 旧码 P2P_ERROR_USER_CANCEL,
    
    ErrorP2PConnectionCheck = 9
    // 旧码 P2P_ERROR_CONNECTION_CHECK,
    
    ErrorP2PChannel = 10
    // 旧码 P2P_ERROR_CHANNEL,
    
    ErrorP2PDisconetByUser = 11
    // 旧码 P2P_ERROR_DISCONNECT_BY_USER,

    //直播类
    
    // ErrorVideoPeerNotExist 对端不在线。
    ErrorVideoPeerNotExist = 100 
    //旧码：CAUSE_PEERNOTEXIST       = 100,       对端不在线
    
    // ErrorVideoPeerDisconnect 对端断开
    ErrorVideoPeerDisconnect = 101 
    //旧码：CAUSE_PEERDISCONNECT     = 101,       对端断开
    
    
    // ErrorVideoPeerInConnect 正在查看中
    ErrorVideoPeerInConnect = 102
    //旧码：CAUSE_PEERINCONNECT      = 102,       正在查看中
    
    //ErrorVideoNotLogin 本端未登陆
    ErrorVideoNotLogin = 103
    //旧码：CAUSE_CALLER_NOTLOGIN    = 103,      本端未登陆
    

    // ret错误码定义

    // ErrorUnknown 未知错误
    ErrorUnknown = 120
    // 旧码 EUnknown = 1
    
    // ErrorDataBase 数据库错误
	ErrorDataBase = 121
    // 旧码 EDataBase = -1
    
    // ErrorInvalidSession  未登录或无效的会话，客户端和设备端通用。
	ErrorInvalidSession = 122
    // 旧码 ESessionTimeout = 2
    
    
    // 设备端鉴权。
    //ECIDExceedQuota 厂家CID达到配额。关联消息：注册。
	ECIDExceedQuota = 140
    // 旧码 ECIDExceedQuota = 61
    
    // ErrorCIDSNVerifyFail SN签名验证失败。关联消息：登陆。
	ErrorCIDSNVerifyFailed = 141
    // 旧码 ESNVerifyFailed = 63
    
    ----
    
    // 客户端登陆类.
    //ErrorInvalidVKey vid, bundleID, vkey校验失败。
	ErrorLoginInvalidVKey = 160
    // 旧码 EInvalidVKey = 65
    
    // ErrorLoginInvalidPass 帐号或密码错误。
	ErrorLoginInvalidPass = 161
    // 旧码 ELoginFailed = 11   
    
    ---

    // 客户端帐号类.
    // ErrorSMSCodeNotMatch 短信验证码错误。
	ErrorSMSCodeNotMatch = 180  
    // 旧码 ESMSCodeNotMatch = 26
    
	// ErrorSMSCodeTimeout 短信验证码超时。
	ErrorSMSCodeTimeout = 181
    // 旧码 ESmsCodeTimeout = 14
    
    // ErrorAccountNotExist 帐号不存在。
	ErrorAccountNotExist = 182
    // 旧码 EAccountNotExist = 10
	
    // ErrorAccountAlreadyExist 帐号已存在。
	ErrorAccountAlreadyExist = 183
    // 旧码 EPhoneAlreadyExist = 13
    
    // ErrorSamePass 原始密码与新密码相同。关联消息：修改密码。
	ErrorSamePass = 184
    // 旧码 ESamePass = 23
    
    // ErrorInvalidPass 原密码错误。关联消息：修改密码。
	ErrorInvalidPass = 185
    // 旧码 EInvalidPass = 28
    
    // ErrorPhoneExist  此手机号码已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorPhoneExist = 186
    // 旧码 EPhoneExist = 52
    
	// ErrorEmailExist 此邮箱已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorEmailExist = 187
    // 旧码 EEmailExist = 53
    
    // 手机号码不合规
	EIsNotPhone = 188
	
	// 邮箱账号不合规
	EIsNotEmail = 189
    
    ----
    
    // 客户端绑定设备类.
    // ErrorCIDNotExist CID不存在。关联消息：客户端绑定。
    ErrorCIDNotExist = 200
    // 旧码 ECIDNotExist = 9
    
    //ErrorCIDBinding 绑定中，正在等待摄像头上传随机数与CID关联关系，随后推送绑定通知
	ErrorCIDBinding = 201
    // 旧码 ECIDBinding = 64
    
    // ErrorCIDAliasExist 设备别名已存在。
	ErrorCIDAliasExist = 202
    // 旧码 EAliasExist = 38
    
    ----
    
    // 客户端分享设备类.
    // ErrorShareInvalidAccount 此帐号还没有注册。
	ErrorShareInvalidAccount = 220
    // 旧码 EInvalidAccount = 54
    
	// ErrorShareAlready 此帐号已经分享。
	ErrorShareAlready = 221
    // 旧码 EAlreadyShared = 55
    
    // ErrorShareToSelf 您不能分享给自己。
	ErrorShareToSelf = 222
    // 旧码 EShareToSelf = 57
    
    //ErrorShareExceedsLimit 设备分享，被分享账号不能超过5个。
	ErrorShareExceedsLimit = 223
    // 旧码 EShareExceedsLimit = 62
    
    ----
    
    // 客户端亲友关系类.
    //ErrorFriendInvalidAccount 添加好友失败 对方账户未注册
	ErrorFriendInvalidAccount = 240
    // 旧码 EInvalidToAccount = 66
    
	//ErrorFriendAlready  已经是好友关系
	ErrorFriendAlready = 241
    // 旧码 EAlreadyFriend = 67 
    
	//ErrorFriendToSelf 不能添加自己为好友
	ErrorFriendToSelf = 242
    // 旧码 EAddSelf = 68
    
	//ErrorFriendInvalidRequest 好友请求消息过期
	ErrorFriendInvalidRequest = 243
    // 旧码 EInvalidFriendRequest = 69
     
    ----
    
    // 获取临时安全凭证
    // 获取失败
    EGetCredentials = 260
    
    ----

    // APP 侧错误号
    // ErrorInvalidMethod 非法的调用，ex: 摄像头/APP 调用对方才有的功能
    ErrorInvalidMethod = 1000
    
    // ErrorInvalidParameter 非法的调用参数，ex: 登陆不带用户名 
    ErrorInvalidParameter = 1001

    // ErrorInvalidState 非法的状态， ex: 和摄像头在连接状态再次调用连接
    ErrorInvalidState = 1002
   
    // ErrorResolve 解析域名失败
    ErrorResolve = 1003

    // ErrorConnect 连接服务器失败
    ErrorConnect = 1004

    ----