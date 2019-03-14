# ReleaseSecretNo {#doc_api_1058877 .reference}

调用接口ReleaseSecretNo释放号码。

释放号码之后，次月开始不再计费。

**说明：** 释放号码之前，请先在[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)上查看该号码是否有绑定关系。号码无任何绑定关系时才能释放。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=ReleaseSecretNo)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

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

## 返回参数 {#resultMapping .section}

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

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

