# SecretRecording {#concept_ryv_ryj_ygb .concept}

接收录音状态报告，可以获取到通话完成后的录音记录，消息内容包括录音下载的链接，便于平台进行录音管理。

## 消息体结构说明 {#section_a31_4s3_ygb .section}

|名称|类型|是否必须|描述|示例|
|:-|:-|:---|:-|:-|
|pool\_key|String|必须|对应的号池Key|FC123456|
|subs\_id|Number|必须|对应的三元组的绑定关系ID|123456|
|call\_id|String|必须|对应的呼叫记录的call\_id|ACV-FSAC-DSA|
|call\_time|Date|必须|呼叫时间|2018-01-01 11:00:00|

