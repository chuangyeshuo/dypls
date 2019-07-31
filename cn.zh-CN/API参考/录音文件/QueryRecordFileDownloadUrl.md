# QueryRecordFileDownloadUrl {#doc_api_Dyplsapi_QueryRecordFileDownloadUrl .reference}

调用接口QueryRecordFileDownloadUrl获取录音文件的下载链接。

如果在绑定关系中开启了录音功能，该绑定关系产生的所有通话均会被录音，可以通过接口**QueryRecordFileDownloadUrl**获取录音文件的下载链接，下载录音文件。

**注意**：

-   URL链接的有效期为2小时。获取下载链接后请尽快下载录音文件。
-   录音文件的存储周期是14天，仅支持下载14天内通话记录的录音文件。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=QueryRecordFileDownloadUrl&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CallId|String|是|abcedf1234|呼叫记录ID，用于标识一条通话记录。

 请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**呼叫记录查询**中查看**呼叫记录ID**。

 |
|CallTime|String|是|2019-03-05 12:00:00|呼叫记录中的呼叫发起时间。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**呼叫记录查询**中查看**呼叫发起时间**，或者在话单回执消息中查看call\_time字段。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryRecordFileDownloadUrl|系统规定参数。取值：**QueryRecordFileDownloadUrl**。

 |
|ProductType|String|否|AXB\_170|产品类型。

 **说明：** 适用于原阿里大于客户，阿里云用户可忽略。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~109196~~)。

 |
|DownloadUrl|String|http://secret-axb-record-files.oss-cn-shanghai.aliyuncs.com/1000000820257625\_66647243838006067251551752068865.mp3?Expires=1551759607&OSSAccessKeyId=LTAI27GqAW1VrcQA&Signature=tK6Yq9KusU4n%2BZQWXI7lg4/WmEA%3D|录音文件的下载链接URL。URL链接的有效期为2小时。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|1AB3CEF7-DCBE-488C-9C33-D180982CE031|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CallId=abcedf1234
&PoolKey=FC123456
&CallTime=2019-03-05 12:00:00
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRecordFileDownloadUrlResponse>
	  <Message>OK</Message>
	  <RequestId>1AB3CEF7-DCBE-488C-9C33-D180982CE031</RequestId>
	  <DownloadUrl>http://secret-axb-record-files.oss-cn-shanghai.aliyuncs.com/1000000820257625_66647243838006067251551752068865.mp3?Expires=1551759607&amp;OSSAccessKeyId=LTAI27GqAW1VrcQA&amp;Signature=tK6Yq9KusU4n%2BZQWXI7lg4/WmEA%3D</DownloadUrl>
	  <Code>OK</Code>
</QueryRecordFileDownloadUrlResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"1AB3CEF7-DCBE-488C-9C33-D180982CE031",
	"DownloadUrl":"http://secret-axb-record-files.oss-cn-shanghai.aliyuncs.com/1000000820257625_66647243838006067251551752068865.mp3?Expires=1551759607&OSSAccessKeyId=LTAI27GqAW1VrcQA&Signature=tK6Yq9KusU4n%2BZQWXI7lg4/WmEA%3D",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

