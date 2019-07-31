# UnbindSubscription {#doc_api_Dyplsapi_UnbindSubscription .reference}

调用接口UnbindSubscription解除号码的绑定关系。

释放号码前，必须调用接口**UnbindSubscription**解除绑定关系。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=UnbindSubscription&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SecretNo|String|是|17000000000|隐私号码。调用BindAXG等号码绑定接口时指定或自动分配的X号码。

 |
|SubsId|String|是|1000000768798832|绑定关系ID。

 可以在控制台的**号码管理** \> **号码详情**中查看绑定关系ID，或者在调用BindAxb等号码绑定API时查看返回参数中的**SubsId**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|UnbindSubscription|系统规定参数。取值：**UnbindSubscription**。

 |
|ProductType|String|否|AXB\_170|产品类型。

 **说明：** 适用于原阿里大于客户，阿里云用户可忽略。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ChargeId|String|true|废弃参数。

 |
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

http(s)://[Endpoint]/?SecretNo=17000000000
&SubsId=1000000768798832
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UnbindSubscriptionResponse>
	  <Message>OK</Message>
	  <RequestId>9B2757F9-8FD0-48B9-9640-EF54783A06C4</RequestId>
	  <ChargeId>true</ChargeId>
	  <Code>OK</Code>
</UnbindSubscriptionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"9B2757F9-8FD0-48B9-9640-EF54783A06C4",
	"ChargeId":true,
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

