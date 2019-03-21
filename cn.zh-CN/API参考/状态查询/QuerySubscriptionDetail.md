# QuerySubscriptionDetail {#doc_api_1102517 .reference}

调用接口QuerySubscriptionDetail查询号码的绑定关系。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=QuerySubscriptionDetail)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|是|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|是|QuerySubscriptionDetail|系统规定参数。取值：**QuerySubscriptionDetail**。

 |
|PhoneNoX|String|是|17000000000|绑定关系中的隐私号码，即X号码。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SubsId|String|是|1000000768798832|绑定关系ID。

 可以在控制台的**号码管理** \> **号码详情**中查看绑定关系ID，或者在调用BindAxb等号码绑定API时查看返回参数中的**SubsId**。

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
|RequestId|String|066E6E47-04CB-4774-A976-4F73CB76D4A3|请求ID。

 |
|SecretBindDetailDTO| | |接口调用成功后返回的结构体。

 |
|└CallRestrict|String|CONTROL\_BX\_DISABLE|单通呼叫限制的状态。如果没有设置单通呼叫限制，则不返回该参数。

 其中：

 -   **CONTROL\_AX\_DISABLE**：A号码无法呼叫X号码。
-   **CONTROL\_BX\_DISABLE**：B号码无法呼叫X号码。

 |
|└ExpireDate|String|2019-09-05 12:00:00|绑定关系的过期时间。

 |
|└Extension|String|130|AXG分机号中的分机号码。

 |
|└GmtCreate|String|2019-03-05 12:00:00|绑定关系的创建时间。

 |
|└GroupId|Long|2000000130001|绑定关系中的G号码组ID，即GID。

 |
|└NeedRecord|Boolean|true|是否设置了对该绑定关系产生的所有通话录制通话录音。

 |
|└PhoneNoA|String|15000000000|绑定关系中的A号码。

 |
|└PhoneNoB|String|15000000001|绑定关系中的B号码。

 |
|└PhoneNoX|String|17000000000|绑定关系中的隐私号码，即X号码。

 |
|└Status|Long|1|该绑定关系的状态。

 其中：

 -   0：已失效。
-   1：生效中。

 |
|└SubsId|String|1000000768798832|绑定关系ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?PhoneNoX=17000000000
&SubsId=1000000768798832
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QuerySubscriptionDetailResponse>
  <Message>OK</Message>
  <RequestId>066E6E47-04CB-4774-A976-4F73CB76D4A3</RequestId>
  <SecretBindDetailDTO>
    <Status>1</Status>
    <ExpireDate>2019-09-05 12:00:00</ExpireDate>
    <PhoneNoX>17000000000</PhoneNoX>
    <NeedRecord>false</NeedRecord>
    <PhoneNoB>15000000001</PhoneNoB>
    <PhoneNoA>15000000000</PhoneNoA>
    <SubsId>1000000768798832</SubsId>
    <GmtCreate>2019-03-02 19:30:11</GmtCreate>
  </SecretBindDetailDTO>
  <Code>OK</Code>
</QuerySubscriptionDetailResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"066E6E47-04CB-4774-A976-4F73CB76D4A3",
	"SecretBindDetailDTO":{
		"Status":1,
		"PhoneNoX":"17000000000",
		"ExpireDate":"2019-09-05 12:00:00",
		"NeedRecord":false,
		"PhoneNoB":"15000000001",
		"SubsId":"1000000768798832",
		"PhoneNoA":"15000000000",
		"GmtCreate":"2019-03-02 19:30:11"
	},
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

