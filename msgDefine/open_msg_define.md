# 一、原有结构化消息定义

需要服务器解析处理的消息保持原结构化格式不变。
原消息定义：消息头 + 可变消息体
 
|  定义 |  类型|   描述 | 
| ---   | ---  | ---    |
|id     | int  | TCP消息唯一标识 |
|caller | string | 源端标识 |
|callee | string | 目的端标识 |
|data1  | ...    | 自定义  |
|...    | ...    | ...     |
|dataN  | ...    | 自定义  |
 

 ---
 
# 二、新增通用消息定义：


## 2.1 消息定义 - 查询请求 

## MIDRobotGetData = 20200


|  定义 |  类型|   描述 | 
| --- | --- | --- |
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|limit|int| 查询条数 |
|asc|bool| 升降序 |
|reqList|array| 被查询功能的消息列表 |


| 定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 查询时间点 |

说明：
* time统一以服务器时间戳为准。
* 如果asc为真，服务器返回time时间点后的数据，之前的数据不返回。
* 如果asc为否，服务器返回time时间点前的数据，之后的数据不返回。
* 如果time置为0, 默认使用服务器当前时间。
* 如果查询单条记录，limit置为1。
* 如果查询列表，limit >1 && limit <=100。
* 服务器或相应端将响应的seq号与请求的seq保持相同，以保证消息的一一对应。


---

## 2.2 消息定义 - 查询响应
## MIDRobotGetDataRsp = 20201
 

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | data的数组。|

| data定义 |  类型|   描述 | 
|---|---|---|
|id| int | dpid, 开放功能唯一标识 |
|objValueList| array |objValue的数组。 |

| objValue定义 |  类型|   描述 | 
|---|---|---|
|time| int64| 更新时间点 |
|value| int, string, bool, ...| 基础类型： |


说明：

* 每个data都是一个开放功能的完整定义。
* 服务器遍历reqList查询，对每个req生成一个dataList，将所有dataList组合成数组。
* 终端可以根据消息id对应的dataList计算出数量。

## 2.3 消息定义 -  设备上报消息 + 配置请求
## MIDRobotSetData = 20202 

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|reqList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|value| int, string, bool, ...| 基础类型： |



---

## 2.4 消息定义 - 配置响应 

## MIDRobotSetDataRsp = 20203

由开放功能定义表格返回值列决定是否要响应该消息。

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|ret| int | 返回值 |

* time 由服务器提供，客户端更新该消息的缓存时间戳。


---

## 2.5 消息定义 - 删除请求 

## MIDRobotDelData = 20204


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识|
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|reqList | array | 消息数组 |

| 元素定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 删除时间点 |

* time 如果time为真，删除匹配条件的单条记录。如果time为0并且是图表类消息, 则删除该消息的全部消息。

---

## 2.6 消息定义 - 删除响应

## MIDRobotDelDataRsp = 20205


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|ret| int | 返回值 |

* 增加ret为响应码。

##  2.7 消息定义 - 未读消息计数

## MIDRobotCountData = 20206


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|act|int| 操作：如果是查询未读消息计数， 响应MIDRobotCountDataRsp；如果是清零未读消息计数，服务器将未读消息计数清零，不响应MIDRobotCountDataRsp。 enum {MIDRobotCountDataQuery, MIDRobotCountDataClear}|
|reqList | array | 消息数组 |

| 定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |

---

## 2.8 消息定义 - 未读消息计数响应 

## MIDRobotCountDataRsp = 20207


|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | data消息数组 |

| data定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|count| int | 计数 |

## 2.9 消息定义 - 组合查询请求

## MIDRobotGetDataEx = 20208

|  定义 |  类型|   描述 | 
| --- | --- | --- |
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|asc|bool| 升降序 |
|time| int64| 查询时间点 |
|reqList|array| 被查询功能的消息列表 |


| 定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |

* time为0， asc降序，服务器从当前时间点查询。
* 如果是降序，后续查询使用响应的dataList最小时间。
* 如果是升序，后续查询使用响应的dataList最大时间。
* 服务器当前响应最大条数为100.
* 服务器响应条数为0，所有数据已查完。

---

## 2.10 消息定义 - 组合查询响应 

## MIDRobotGetDataExRsp = 20209

|  定义 |  类型|   描述 | 
|---|---|---|
|id| int | TCP消息唯一标识 |
|caller| string | 源端标识 |
|callee| string | 目的端标识 |
|seq|int64| 序列号 |
|dataList | array | data消息数组 |

| data定义 |  类型|   描述 | 
|---|---|---|
|id| int | 开放功能唯一标识 |
|time| int64| 更新时间点 |
|value| int, string, bool, ...| 基础类型： |


说明：

* 每个data都是一个开放功能的完整定义。
* 服务器使用in关键字组合消息ID为一个查询条件，执行一次查询。
* 服务器按照时间段范围查询。


## 2.11 消息定义 - 客户端操作配置后多终端同步

## MIDRobotSyncData = 20210

结构同 [MIDRobotSetData = 20202](open_msg_define.md#midrobotsetdata-20202) 

## 2.12 消息定义 - 设备端事件触发APP端同步

## MIDRobotPuhsData = 20211

结构同 [MIDRobotSetData = 20202](open_msg_define.md#midrobotsetdata-20202) 

--------------------------------------------------------------------------------------------------------------------------------------

* APP端多条查询消息 - 状态类
  
组合查询 - 如同时查询SD卡和网络类型的消息请求：

设备列表cidlist使用这种方式。
{20200, "", "200000001", seq, 1, true, [{4, time},{1, time}]}
    
响应：
{20201, "", "", seq, [[{4, {time, msgpack(*)}], [{1, {time, msgpack(*)}]]}
 
---
   
* APP端多条查询消息 - 图表类

如查询报警消息的请求：
{20200, "", "200000001", seq, 2, true, [{5, time}]}
   
如查询报警消息的响应：
{20201, "", "", seq, [[{5，{time, msgpack(*)}},{5, {time, msgpack(*)}}]]}
   
---
   
* APP端组合查询 - 混合消息图表类

如查询报警消息的请求：
{20208, "", "200000001", seq, 2, true, time, [{5}, {1}]}
   
如查询报警消息的响应：
{20209, "", "", seq, [{5，{time, msgpack(*)}},{1, {time, msgpack(*)}}]}
   
---
  
#  服务器消息缓存原则：缓存最新一条消息。





