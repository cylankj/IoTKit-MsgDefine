# 结构定义

* iot_atomic_data 原子数据定义

    ```cpp
    // 所有设备及APP数据的交互都以atomic 为基础
    // 服务器上预定义了一系列id， 如版本号等
    // 也可以选择在IoT后台添加自定义的数据类型
    typedef struct {
        unsigned int        id;
        char *              value;
        unsigned int        seq;
        unsigned int        ret_code;
    } iot_atomic_data;
    ```
    
* 网络类型

    ```cpp
    typedef enum {
        IOT_NET_WIFI,
        IOT_NET_3G,
        IOT_NET_4G,
        IOT_NET_2G
    } iot_nettype;
    ```