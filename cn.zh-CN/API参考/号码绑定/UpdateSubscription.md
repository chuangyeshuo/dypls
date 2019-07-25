# UpdateSubscription {#doc_api_Dyplsapi_UpdateSubscription .reference}

调用接口UpdateSubscription修改绑定关系。

添加号码绑定关系后，可以通过接口**UpdateSubscription**修改绑定关系，例如修改A号码、修改B号码、修改绑定关系有效期、设置单通呼叫限制或修改G号码组。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=UpdateSubscription&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|OperateType|String|是|updateNoA|修改绑定关系的操作，包括：

 -   **updateNoA**：修改A号码。
-   **updateNoB**：修改B号码。
-   **updateExpire**：修改绑定关系有效期。
-   **updateAxgGroup**：修改G号码组。
-   **updateCallRestrict**：设置单通呼叫限制。
-   **updateCallDisplayType**：更新呼叫显号逻辑。
-   **updateOutId**：更新OutId字段。
-   **updateIsRecordingEnabled**：更新绑定中录音状态。

 |
|PhoneNoX|String|是|15000000000|号码绑定关系中的X号码。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SubsId|String|是|1000000768798832|绑定关系ID。

 可以在控制台的**号码管理** \> **号码详情**中查看绑定关系ID，或者在调用BindAxb等号码绑定API时查看返回参数中的**SubsId**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|UpdateSubscription|系统规定参数。取值：**UpdateSubscription**。

 |
|CallDisplayType|Integer|否|1|重置绑定关系中的号码显示逻辑，1：主被叫显示中间号码X；2：B/N侧号码呼叫时，给A侧号码显示B/N的真实号码；3：A侧号码呼叫时，给B/N侧号码显示真实号码。

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
|IsRecordingEnabled|Boolean|否|true|重新设置绑定关系中的录音状态

 |
|OutId|String|否|abcdef|重新设置绑定关系中的OutId

 |
|PhoneNoA|String|否|150000000|设置绑定关系中的A号码，当**OperateType**指定为**updateNoA**时必填。

 |
|PhoneNoB|String|否|150000001|设置绑定关系中的B号码，当**OperateType**指定为**updateNoB**时必填。

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

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

