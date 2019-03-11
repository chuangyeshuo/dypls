# SecretStartReport {#concept_c4v_jyj_ygb .concept}

接收通话发起时的通话记录报告内容，可以在呼叫发起时立即获取到通话记录信息，包括通话开始时间、主被叫号码等，便于平台进行预判处理。

## 返回参数 {#section_a31_4s3_ygb .section}

|名称|类型|是否必须|描述|示例|
|:-|:-|:---|:-|:-|
|pool\_key|String|必须|对应的号池Key|FC1234567|
|sub\_id|Long|必须|通话对应的三元组的绑定关系ID|123456|
|call\_id|String|必须|唯一标识一通通话记录的ID|abcdef1234|
|phone\_no|String|必须|AXB中的A号码|15000000000|
|secret\_no|String|必须|AXB中的X号码|1700000000|
|peer\_no|String|必须|AXB中的B号码或者N号码|1580000000|
|called\_display\_no|String|必须|被叫显号|1580100000|
|call\_type|Interger|必须|呼叫类型|0:主叫\(phone\_no打给peer\_no\)；1:被叫\(peer\_no打给phone\_no\)；2:短信发送；3:短信接收; 4:呼叫拦截; 5:短信收发拦截|
|call\_time|String|必须|主叫拨打时间|“2017-09-01 12:00:00”|
|out\_id|String|可选|外部业务ID|123456|

