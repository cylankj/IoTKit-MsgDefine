## 第三方账号系统校验access_token 

## 1. 标准协议: ##

第三方账号登陆采用OAuth2.0标准协议来进行用户身份验证和获取用户授权，其认证流程简单、安全。

如果您想对OAuth2.0开放标准进行扩展阅读，请参看：[OAuth标准（英文）](http://oauth.net/2/) | [OAuth维基百科（中文） ](http://zh.wikipedia.org/zh/OAuth)

## 2. 关键参数：##

**access_token**（受信访问令牌）： 由第三方账号系统分配的临时凭证，每次用户登录时生成。

**open_id**（授权用户对应的唯一标识）：是用户身份的唯一标识，加菲狗系统会将此open_id进行存储，用于用户下次登录时辨识其身份。

**URL**（access_token的认证网址）： 加菲狗系统会调用该URL接口验证access_token的有效性。

以上参数均由**由对接方提供。**


## 3.使用流程 ##

第三方账号系统校验总体处理流程如下：
Step1：接入萝卜头平台open.robotscloud.com申请，获取VID和VKEY，填写URL资料；
Step2：客户端调用SDK的openLogin接口，填充参数access_token及open_id；
Step3：萝卜头平台到URL网址验证access_token；
Step4：通过验证，open_id在萝卜头平台合法使用。


## 4. 萝卜头平台到URL网址验证access_token接口说明 ##

**协议：** 支持HTTP， HTTPS。

**HTTP[S] GET 请求**

|请求参数|必须|字段类型|说明|
| --- | --- | --- | ---|
|access_token|true|String| 受信访问令牌|



**HTTP[S]响应**

|响应参数|字段类型|说明|
| --- | --- | --- |
|code|string|状态码。定义：200 正确返回；500 系统内部错误；100002 access_token过期|
|message|string|code非200情况下系统提示信息|
|value| 组合参数| 详见下述定义|
|redirect|string|保留字段|


|value参数|字段类型|说明|
| --- | --- | --- |
|expired_at| int64| 毫秒， access_token的过期时间戳(如：1433075493123)|
|open_id|string|授权用户对应的唯一标识|
|vid|string | 萝卜头平台的企业编号：四位36进制字符串 |



### 示例： ###

**请求：**
URL?access_token=********

**Token有效时的响应：**
{"code":"200","message":"","value":{"expired_at":1433075493，"open_id":"YMpfqmaiwUIpJg6m5YuYzZajnE7c1","vid":"00FF"},"redirect":""}

**Token失效时的响应：**
{"code":"100002","message":"token 已失效","redirect":"","value":""}
