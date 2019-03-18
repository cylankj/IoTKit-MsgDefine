# 阿里IOT第三方账号接入接口

## 接口地址
```
测试环境：http://yun3.jfgou.com/api/userauth/aliiot
正式环境：http://yun.jfgou.com/api/userauth/aliiot
```

## token生成
1.生成待加密字符串，格式为：
```
account=%s&timestamp=%d&vid=%s&vkey=%s
```
如:account=tangke@cylan.com.cn&timestamp=1507774838&vid=0001&vkey=1234567890

2.对待加密字符串MD5加密得到校验码sign

3.生成token明文字符串，格式为：
```
account=%s&timestamp=%d&vid=%s&sign=%s
```
如account=tangke@cylan.com.cn&timestamp=1507774838&vid=0001&sign=8237ef3d3f70a8687e565c10421d70c3

4.对token明文base64编码得到token：

  编码规则： 
  * 字符集："ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"
  * Padding："="

附1：以上各参介绍：

| 参数名 | 数据类型 | 说明 |
|:------|:-------|:----|
| account | 字符串 | 账户名 |
| timestamp | 整型 | 生成token的时间，单位：秒 |
| vid | 字符串 | 由萝卜头平台分配 |
| vkey | 字符串 | 由萝卜头平台分配 |
| sign | 字符串 | 校验码 |

附2：python实现：
```python
import base64
import hashlib
import time

account = "tangke@cylan.com.cn"
time_now = int(time.time())
vid = "0001"
vkey = "1234567890"

sign_str = "account=%s&timestamp=%d&vid=%s&vkey=%s"%(account, time_now, vid, vkey)
m = hashlib.md5()
m.update(sign_str)
sign = m.hexdigest()
print sign

token_str = "account=%s&timestamp=%d&vid=%s&sign=%s"%(account, time_now, vid, sign)
token = base64.b64encode(token_str)
print token
```