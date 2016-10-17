
## DPIDUserDefinedBegin 

* 自定义消息个数共 10000 个 .
* 生成规则：
 
      将企业编号 VID (四位三十六进制字符串)转换为十进制整形 VIDUint32 .
  
      VIDUint32 左移32位，并加上偏移量IDOffset，IDOffset取值范围为 30001 至 40000 ：VIDUint32 << 32 + IDOffset .
  
* 示例：
  
      VID 为 001Z ，IDOffset = 30002 ，则id为 71 << 32 + 30002 = 9689311739391 + 30002 = 9689311769393 .