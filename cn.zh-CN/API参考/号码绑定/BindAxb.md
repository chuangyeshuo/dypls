# BindAxb {#doc_api_Dyplsapi_BindAxb .reference}

调用接口BindAxb添加AXB号码的绑定关系。

绑定AXB号码前，请先明确您的业务场景中AXB三元组的A角色和B角色。例如，在打车应用场景中，A可以是乘客角色，B是司机角色；房产类业务场景中，A可能是用户，B是房产中介。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=BindAxb&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Expiration|String|是|2019-09-05 12:00:00|绑定关系的过期时间。必须晚于当前时间1分钟以上。

 |
|PhoneNoA|String|是|15000000000|AXB中的A号码。

 A号码可设置为手机号码或固定电话，固定电话需要加区号，区号和号码中间不需要加连字符，例如057188992688。

 |
|PhoneNoB|String|是|15000000001|AXB中的B号码，A号码拨打X号码时会转接到B号码，可通过接口**UpdateSubscription**更新B号码。

 B号码可设置为手机号码或固定电话，固定电话需要加区号，区号和号码中间不需要加连字符，例如057188992688。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|BindAxb|系统规定参数。取值：**BindAxb**。

 |
|CallDisplayType|Integer|否|1|重置绑定关系中的号码显示逻辑，1：主被叫显示中间号码X；2：B/N侧号码呼叫时，给A侧号码显示B/N的真实号码；3：A侧号码呼叫时，给B/N侧号码显示真实号码。

 |
|ExpectCity|String|否|北京|指定城市进行X号码的选号。

 如果当前号池中没有该城市的可用号码，或未指定此参数，将从当前号码池中随机分配一个其他城市的号码作为X号码。

 如果配置了严格模式，则不存在符合条件的号码时会提示分配错误。

 |
|IsRecordingEnabled|Boolean|否|true|是否需要针对该绑定关系产生的所有通话录制通话录音。

 |
|OutId|String|否|abcdef|外部业务扩展字段，通话记录回执消息中会回传此参数。

 |
|OutOrderId|String|否|abcdef|外部业务ID。

 |
|PhoneNoX|String|否|17000000000|AXB中的X号码。未指定X号码时，将根据参数**ExpectCity**从指定号码池中随机指定一个号码作为X号码。

 X号码是您绑定号码前在控制台或通过接口**BuySecretNo**购买的电话号码，用于转接电话。

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
|RequestId|String|9297B722-A016-43FB-B51A-E54050D9369D|请求ID。

 |
|SecretBindDTO| | |绑定成功后返回的结构体。

 |
|Extension|String|130|分机号码。接口BindAxb不涉及分机号码，请忽略该返回参数。

 |
|SecretNo|String|17100000000|隐私号码，即X号码。

 |
|SubsId|String|1000000768393849|绑定关系ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?PhoneNoA=15000000000
&Expiration=2019-09-05 12:00:00
&PhoneNoB=15000000001
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BindAxbResponse>
	  <Message>OK</Message>
	  <RequestId>9297B722-A016-43FB-B51A-E54050D9369D</RequestId>
	  <Code>OK</Code>
	  <SecretBindDTO>
		    <Extension>130</Extension>
		    <SecretNo>17100000000</SecretNo>
		    <SubsId>1000000768393849</SubsId>
	  </SecretBindDTO>
</BindAxbResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"9297B722-A016-43FB-B51A-E54050D9369D",
	"Code":"OK",
	"SecretBindDTO":{
		"Extension":"130",
		"SecretNo":"17100000000",
		"SubsId":"1000000768393849"
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

