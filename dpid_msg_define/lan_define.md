## 局域网消息 3.0

## 通用头部

```cpp
struct Header {
    // 固定为 0x3000
    uint16_t   magic;
    // 固定为 0x30ff
    uint16_t   msgid;
    // jsonstr 原始长度
    uin16_t    msglen;
    // 加密的json消息
    // 不定长
    char       jsonstr[0];
}
```

## 加密方法

#### 计算头部的check sum, 1 byte: 

checksum(magic) + checksum(msgid) + checksum(msglen)


#### 加密 jsonstr

以 check sum 做key, 使用AES算法,加密 jsonstr, 并做8 bytes对齐

#### 解密 jsonstr

反过来, 计算 checksum做key, aes 解密, 然后根据真实长度去掉补齐位置

## 局域网消息列表

#### 扫描 ping

```json
{
   "cmd": "ping" 
}
```

#### 扫描响应 ping_ack


```json
{
   "cmd": "ping_ack",
   "cid": "2000001",
   "net": 0 
}
```
