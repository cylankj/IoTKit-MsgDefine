    // EOK 成功
	ErrorOK = 0
    
    // P2P 错误码
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
    
    ErrorP2PDisconetByUser = 11

    
    // 对端不在线
    ErrorVideoPeerNotExist = 100 

    // 对端断开
    ErrorVideoPeerDisconnect = 101 
    
    // 正在查看中
    ErrorVideoPeerInConnect = 102
    
    // 本端未登陆
    ErrorVideoNotLogin = 103
    
    // 未知错误
    ErrorUnknown = 120
    
    // 数据库错误
	ErrorDataBase = 121
    
    // 未登录或无效的会话，客户端和设备端通用
	ErrorInvalidSession = 122

    // 设备端鉴权
    // 厂家CID达到配额。关联消息：注册。
	ECIDExceedQuota = 140
    
    // SN签名验证失败。关联消息：登陆。
	ErrorCIDSNVerifyFailed = 141
    
    ----
    
    // 客户端登陆类.
    // vid, bundleID, vkey校验失败。
	ErrorLoginInvalidVKey = 160
    
    // 帐号或密码错误。
	ErrorLoginInvalidPass = 161
    
    ---

    // 客户端帐号类.
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
    
    //  此手机号码已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorPhoneExist = 186
    
	// 此邮箱已被绑定。关联消息：帐号、手机号、邮箱绑定。
	ErrorEmailExist = 187
    
    // 手机号码不合规
	ErrorIsNotPhone = 188
	
	// 邮箱账号不合规
	ErrorIsNotEmail = 189
    
    ----
    
    // 客户端绑定设备类.
    // CID不存在。关联消息：客户端绑定。
    ErrorCIDNotExist = 200
    
    // 绑定中，正在等待摄像头上传随机数与CID关联关系，随后推送绑定通知
	ErrorCIDBinding = 201
    
    // 设备别名已存在。
	ErrorCIDAliasExist = 202
    
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
    
    // 客户端亲友关系类.
    // 添加好友失败 对方账户未注册
	ErrorFriendInvalidAccount = 240
    
	// 已经是好友关系
	ErrorFriendAlready = 241
    
	// 不能添加自己为好友
	ErrorFriendToSelf = 242
    
	// 好友请求消息过期
	ErrorFriendInvalidRequest = 243
     
    ----
    
    // 获取临时安全凭证
    // 获取失败
    ErrorGetCredentials = 260
    
    // 消息格式错误
    ErrorInvalidMsg = 261
    
    ----

    // APP 侧错误号
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

    ----