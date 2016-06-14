# 预定义消息概述

## 一、全局配置类定义 DP_ID_BEGIN_CFG = 0

|id     |描述                  |数据类型    |  
|-------|-------------------|----------|
| 1     | RelayServer配置      | string     |
| 2     | MsgServer配置        | string     | 
| 3     | CidOSSConfig配置     | string     | 
| 4     | ClientOSSConfig配置  | string     | 



## 二、局域网消息定义 DP_ID_BEGIN_UDP = 100


## 三、开放功能定义表格 DP_ID_BEGIN_OPEN = 200

| id     |描述       |是否唯一   |数据类型    |APP可见    |显示/控制     |是否有返回值   | 是否展示图表    | APP多终端是否需要同步 | 是否推送消息到APP端 |
|-------|----------|----------|----------|----------|------------ |---------|---------|------|------|
| DP_ID_BEGIN_OPEN + 1     | 网络类型  | 否        | string     | 是        | 显示         | 无      |无       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 2     | MAC地址   | 是        | string     | 是        | 显示         | 无      |无       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 3     | SD卡信息  | 否        | string     | 是        | 显示         | 无      |无       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 4     | 剩余电量  | 否        | int        | 是        | 显示         | 无      |无       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 5     | 版本号    | 否        | string     | 是        | 显示         | 无      |无       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 6     | 系统版本号| 否        | string     | 是        | 显示         | 无      |无       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 7     | 报警配置  | 否        | string     | 是        | 控制         | 是     |无       | 是 | 否 |
| DP_ID_BEGIN_OPEN + 8     | 报警消息  | 否        | string     | 是        | 显示         | 无      |有       | 否 | 是 |
| DP_ID_BEGIN_OPEN + 9     | 控制设备麦克风 | 否   | bool       | 是        | 控制         | 无      |无       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 10    | 控制设备喇叭   | 否   | bool       | 是        | 控制         | 无      |无       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 11    | 设备画面翻转   | 否   | int        | 是        | 控制         | 无      |无       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 12    | 门铃呼叫状态   | 否   | string     | 是        | 显示         | 无      |有       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 13    | 设备上报日志消息 | 否 | string     | 否        | 控制         | 无      |无       | 否 | 否 |
| DP_ID_BEGIN_OPEN + 14    | 开机时间         | 否 | int        | 是        | 显示         | 无      |无       | 否 | 否 |



