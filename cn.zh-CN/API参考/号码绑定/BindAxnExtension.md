# BindAxnExtension {#doc_api_Dyplsapi_BindAxnExtension .reference}

调用接口BindAxnExtension添加AXN分机号码的绑定关系。

添加AXN分机号码的绑定关系前，请先确定业务场景中AXN号码的A号码和N号码。例如A号码是客户，则X号码是为客户分配的隐私号，其他的任何号码拨打X号码+分机号码都会转接到A号码，A拨打X的时候回呼叫会转接到绑定时所传入的默认B号码。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=BindAxnExtension)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Expiration|String|是|2019-09-05 12:00:00|绑定关系的过期时间。必须晚于当前时间1分钟以上。

 |
|PhoneNoA|String|是|15000000000|AXN中的A号码。

 A号码可设置为手机号码或固定电话，固定电话需要加区号，区号和号码中间不需要加连字符，例如057188992688。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|BindAxnExtension|系统规定参数。取值：**BindAxnExtension**。

 |
|ExpectCity|String|否|北京|指定城市进行X号码的选号。

 如果当前号池中没有该城市的可用号码，或未指定此参数，将从当前号码池中随机分配一个其他城市的号码作为X号码。

 如果配置了严格模式，则不存在符合条件的号码时会提示分配错误。

 |
|Extension|String|否|130|X号码的分机号码，1~3位。

 |
|IsRecordingEnabled|Boolean|否|true|是否需要针对该绑定关系产生的所有通话录制通话录音。

 |
|OutId|String|否|abcdef|外部业务扩展字段，通话记录回执消息中会回传此参数。

 |
|OutOrderId|String|否|abcdef|外部业务ID。

 |
|PhoneNoB|String|否|15000000001|AXN中的B号码，A号码拨打X号码时会转接到B号码，可通过接口**UpdateSubscription**更新B号码。

 B号码可设置为手机号码或固定电话，固定电话需要加区号，区号和号码中间不需要加连字符，例如057188992688。

 |
|PhoneNoX|String|否|17000000000|AXN中的X号码。未指定X号码时，将根据参数**ExpectCity**从指定号码池中随机指定一个号码作为X号码。

 X号码是您绑定号码前在控制台或通过接口**BuySecretNo**购买的电话号码，用于转接电话。

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
|RequestId|String|9297B722-A016-43FB-B51A-E54050D9369D|请求ID。

 |
|SecretBindDTO| | |绑定成功后返回的结构体。

 |
|└Extension|String|130|分机号码。

 |
|└SecretNo|String|17000000000|隐私号码，即X号码。

 |
|└SubsId|String|1000000820000605|绑定关系ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Expiration=2019-09-05 12:00:00
&PhoneNoA=15000000000
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BindAxnExtensionResponse>
  <Message>OK</Message>
  <RequestId>9297B722-A016-43FB-B51A-E54050D9369D</RequestId>
  <Code>OK</Code>
  <SecretBindDTO>
    <Extension>130</Extension>
    <SecretNo>17000000000</SecretNo>
    <SubsId>1000000820000605</SubsId>
  </SecretBindDTO>
</BindAxnExtensionResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"9297B722-A016-43FB-B51A-E54050D9369D",
	"Code":"OK",
	"SecretBindDTO":{
		"Extension":"130",
		"SecretNo":"17000000000",
		"SubsId":"1000000820000605"
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

