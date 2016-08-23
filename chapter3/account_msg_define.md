## DPIDAccountBind = DPIDAccountBegin +1

*  强制绑定，解绑消息

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|int| 功能消息唯一标识|
|time| int64| 时间点 |
|value|string| |


|  value定义 |  类型|   描述 | 
|---|---|---|
|isBind|bool| true：绑定，false：解绑|
|account |string| 强绑帐号 |

---