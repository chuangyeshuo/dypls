# ReleaseSecretNo {#doc_api_Dyplsapi_ReleaseSecretNo .reference}

调用接口ReleaseSecretNo释放号码。

释放号码之后，次月开始不再计费。

**说明：** 释放号码之前，请先在[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)上查看该号码是否有绑定关系。号码无任何绑定关系时才能释放。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=ReleaseSecretNo&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SecretNo|String|是|130|指定号码前缀。购买号码时，如果指定**SecretNo**，会根据指定的号码前缀模糊匹配手机号。

 最长可设置18位号码前缀。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|LTAIP00vvvvvvvvv

 |
|Action|String|否|ReleaseSecretNo|系统规定参数。取值：**ReleaseSecretNo**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~109196~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|986BCB6D-C9BF-42F9-91CE-3A9901233D36|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?PoolKey=FC123456
&SecretNo=130
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ReleaseSecretNoResponse>
	  <Message>OK</Message>
	  <RequestId>986BCB6D-C9BF-42F9-91CE-3A9901233D36</RequestId>
	  <Code>OK</Code>
</ReleaseSecretNoResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"986BCB6D-C9BF-42F9-91CE-3A9901233D36",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

