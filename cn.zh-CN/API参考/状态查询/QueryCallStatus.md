# QueryCallStatus {#doc_api_1102519 .reference}

调用接口QueryCallStatus查询呼叫状态。

在业务中使用已创建的绑定关系之前，建议通过接口QueryCallStatus查询呼叫状态，以免呼叫关系异常，影响实际业务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=QueryCallStatus)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SubsId|String|是|1000000768798832|绑定关系ID。

 可以在控制台的**号码管理** \> **号码详情**中查看绑定关系ID，或者在调用BindAxb等号码绑定API时查看返回参数中的**SubsId**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryCallStatus|系统规定参数。取值：**QueryCallStatus**。

 |
|CallNo|String|否|150000000|主叫号码。

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
|RequestId|String|E7F99446-8191-43C0-99B5-F58A6AEAD7D5|请求ID。

 |
|SecretCallStatusDTO| | |接口调用成功后返回的结构体。

 |
|└CalledNo|String|17000000000|被叫的号码，即X号码。

 其中：

 -   当status =1时，calledNo为X号码。
-   当status=2时，calledNo为重新分配的临时X号码。
-   当status=3时为null，表示用户需要自行降级到真实主号。

 |
|└Status|Integer|4|当前的呼叫状态。其中：

 -   1：呼叫正常。
-   2：当前绑定关系呼叫状态异常，平台重新分配了一个临时可用的X号码用于呼叫。
-   3：当前绑定呼叫异常，且分配临时号码失败。建议用户降级为透传真实的被叫号码来继续呼叫。
-   4：绑定关系已经过期。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?SubsId=1000000768798832
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryCallStatusResponse>
  <Message>OK</Message>
  <RequestId>E7F99446-8191-43C0-99B5-F58A6AEAD7D5</RequestId>
  <SecretCallStatusDTO>
    <Status>4</Status>
    <CalledNo>17000000000</CalledNo>
  </SecretCallStatusDTO>
  <Code>OK</Code>
</QueryCallStatusResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"E7F99446-8191-43C0-99B5-F58A6AEAD7D5",
	"SecretCallStatusDTO":{
		"Status":4,
		"CalledNo":"17000000000"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

