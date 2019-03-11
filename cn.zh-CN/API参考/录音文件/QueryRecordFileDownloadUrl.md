# QueryRecordFileDownloadUrl {#doc_api_1039838 .reference}

调用接口QueryRecordFileDownloadUrl获取录音文件的下载链接。

如果在绑定关系中开启了录音功能，该绑定关系产生的所有通话均会被录音，可以通过接口**QueryRecordFileDownloadUrl**获取录音文件的下载链接，下载录音文件。

**注意**：

-   URL链接的有效期为2小时。获取下载链接后请尽快下载录音文件。
-   录音文件的存储周期是14天，仅支持下载14天内通话记录的录音文件。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=QueryRecordFileDownloadUrl)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CallId|String|是|abcedf1234|呼叫记录ID，用于标识一条通话记录。

 请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**呼叫记录查询**中查看**呼叫记录ID**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryRecordFileDownloadUrl|系统规定参数。取值：**QueryRecordFileDownloadUrl**。

 |
|CallTime|String|否|2019-03-05 12:00:00|呼叫记录中的呼叫发起时间。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**呼叫记录查询**中查看**呼叫发起时间**，或者在话单回执消息中查看call\_time字段。

 **说明：** CallTime为必填参数。

 |
|PoolKey|String|否|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 **说明：** PoolKey为必填参数。

 |
|ProductType|String|否|AXB\_170|废弃字段，无须关注。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~101346~~)。

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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

