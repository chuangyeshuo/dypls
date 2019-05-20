# SecretSmsIntercept {#concept_ojg_nyj_ygb .concept}

接收短信内容报告，可以获取到短信发送后的内容记录，包括短信发送方、接收方、发送时间等信息，便于平台进行短信管理。

## 返回参数 {#section_a31_4s3_ygb .section}

|名称|类型|是否必须|描述|示例|
|:-|:-|:---|:-|:-|
|id|Number|必须|唯一标识一条短信记录的ID|123456|
|pool\_key|String|必须|对应的号池Key|FC1234567|
|sub\_id|Number|必须|短信对应的三元组的绑定关系ID|123456|
|send\_no|String|必须|AXB中的A号码|15000000000|
|secret\_no|String|必须|AXB中的X号码|1700000000|
|receive\_no|String|必须|AXB中的B号码|1800000000|
|sms\_content|String|必须|短信内容|hello world|
|partner\_key|String|必须|AXB归属合作伙伴KEY|123456|
|start\_time|Date|必须|短信发送时间|“2018-01-05 12:01:00”|
|out\_id|String|可选|外部业务ID|123456|
|status|Number|可选|智能短信发送状态。 -   1：发送成功。
-   2：发送失败。

 |1|
|sms\_sign|String|可选|智能短信签名。|号码隐私保护|
|sms\_type|Number|必须|短信类型。 -   1：短信截取
-   2：智能短信

 |1|

