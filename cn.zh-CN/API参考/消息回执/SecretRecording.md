# SecretRecording {#concept_ryv_ryj_ygb .concept}

接收录音状态报告，接收到此消息即表示录音已经生成，可以根据消息内容，通过【[录音文件](https://help.aliyun.com/document_detail/110264.html)】查询接口下载相应录音文件。

## 消息体结构说明 {#section_a31_4s3_ygb .section}

|名称|类型|是否必须|描述|示例|
|:-|:-|:---|:-|:-|
|pool\_key|String|必须|对应的号池Key|FC123456|
|subs\_id|Number|必须|对应的三元组的绑定关系ID|123456|
|call\_id|String|必须|对应的呼叫记录的call\_id|ACV-FSAC-DSA|
|call\_time|Date|必须|呼叫时间|2018-01-01 11:00:00|

