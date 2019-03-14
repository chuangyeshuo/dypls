# UpdateSubscription {#doc_api_1058887 .reference}

调用接口UpdateSubscription修改绑定关系。

添加号码绑定关系后，可以通过接口**UpdateSubscription**修改绑定关系，例如修改A号码、修改B号码、修改绑定关系有效期、设置单通呼叫限制或修改G号码组。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=UpdateSubscription)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|OperateType|String|是|updateNoA|修改绑定关系的操作，包括：

 -   **updateNoA**：修改A号码。
-   **updateNoB**：修改B号码。
-   **updateExpire**：修改绑定关系有效期。
-   **updateAxgGroup**：修改G号码组。
-   **updateCallRestrict**：设置单通呼叫限制。

 |
|PhoneNoX|String|是|15000000000|号码绑定关系中的X号码。

 |
|SubsId|String|是|1000000768798832|绑定关系ID。

 可以在控制台的**号码管理** \> **号码详情**中查看绑定关系ID，或者在调用BindAxb等号码绑定API时查看返回参数中的**SubsId**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|UpdateSubscription|系统规定参数。取值：**UpdateSubscription**。

 |
|CallRestrict|String|否|CONTROL\_BX\_DISABLE|设置单通呼叫限制，当**OperateType**指定为**updateCallRestrict**时必填。

 取值为：

 -   **CONTROL\_AX\_DISABLE**：A号码无法呼叫X号码。
-   **CONTROL\_BX\_DISABLE**：B号码无法呼叫X号码。
-   **CONTROL\_CLEAR\_DISABLE**：清除呼叫限制。

 |
|Expiration|String|否|2019-09-05 12:00:00|重新设置绑定关系的过期时间，**OperateType**为**updateExpire**时必填。过期时间必须晚于当前时间1分钟以上。

 |
|GroupId|String|否|1234|设置绑定关系中的G号码组ID，当**OperateType**指定为**updateAxgGroup**时必填。

 |
|PhoneNoA|String|否|150000000|设置绑定关系中的A号码，当**OperateType**指定为**updateNoA**时必填。

 |
|PhoneNoB|String|否|150000001|设置绑定关系中的B号码，当**OperateType**指定为**updateNoB**时必填。

 |
|PoolKey|String|否|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 **说明：** PoolKey为必填参数。

 |
|ProductType|String|否|AXB\_170|废弃参数。

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

http(s)://[Endpoint]/?OperateType=updateNoA
&PhoneNoX=15000000000
&SubsId=1000000768798832
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateSubscriptionResponse>
  <Message>OK</Message>
  <RequestId>986BCB6D-C9BF-42F9-91CE-3A9901233D36</RequestId>
  <Code>OK</Code>
</UpdateSubscriptionResponse>

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

