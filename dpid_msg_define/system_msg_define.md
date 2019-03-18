## 系统相关功能定义 DPIDSystemBegin = 700 
## DPIDSystemMsg = 701

*  系统消息通知

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| |


|  value定义 |  类型|   描述 | 
|---|---|---|
|title|string| 标题 |
|cnt|string| 内容 |
|popup|int| 弹窗样式。 0:不弹窗，1:弹窗 |

---

## 702

*  保留消息号

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| |

## 703

*  保留消息号

|  data定义 |    类型| 描述 | 
|---|---|---|
|id|long| 功能消息唯一标识|
|timeMsec| int64| DP时间点, 毫秒 |
|value|string| |
