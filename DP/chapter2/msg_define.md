# 消息定义

* MPID_KEY_EXCHANGE(0)  秘钥交换

    ```cpp
    // 序列号  
    unsigned int        seq;  
    // 16字节计算结果  
    unsigned char[16]   pkey;   
    ```

* MPID_ENCRYPT_MSG(1)   加密数据传输

    ```cpp
    // 解密后的数据将是完整的一个[id, caller, callee, payload] 的msgpack 打包结构
    unsigned char       msg[];
    ```
    
* MPID_DEV_LOGIN_RQT(100)   设备登录请求

    ```cpp
    // 厂商id
    unsigned int        vid;
    // 设备id
    unsigned int        pid;
    
    // 设备序列号
    char *              sn;
    // 设备私钥对sn的签名
    char *              sn_sign;
    // 设备mac地址
    char *              mac;
    
    // 网络类型，可选为xxxx
    iot_nettype         network_type;
    // 无线网络ssid
    char *              ssid;
    
    // 版本号
    unsigned int        version;
    // 版本描述字符串
    char *              version_str;
    
    // 开机时间
    unsigned int        uptime;
    
    // 服务器公钥证书
    char *              server_pem;
    ```    

* MPID_DEV_LOGIN_RSP(101)   设备登录响应

    ```cpp
    // 登录错误号， 可选xxxx
    int                 error;
    ```
    
* MPID_ATOMIC_DATA  atomic数据消息

    ```cpp
    // 数据是多方向的 设备<-->server<-->APP
    iot_atomic_data[0]   data;
    ```