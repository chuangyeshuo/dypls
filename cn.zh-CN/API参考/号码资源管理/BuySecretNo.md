# BuySecretNo {#doc_api_1102369 .reference}

调用BuySecretNo接口购买号码。

在控制台创建号码池之后，号码池默认为空，需要为号码池购买号码。

购买号码操作涉及到资源资费，请确保在使用该接口前，已充分了解X号码隐私保护产品的收费方式和[价格](~~59825~~)。

**注意**：

-   购买号码时，指定归属地如果没有足够号码可供购买，会造成号码购买失败。调用接口BuySecretNo购买号码前，请先通过接口QuerySecretNoRemain查询线上可购号码余量。
-   购买号码的账号必须已实名认证为企业账号。如何进行实名认证，请参考[企业实名认证](~~37172~~)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=BuySecretNo)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|City|String|是|杭州|指定号码的归属地。

 **注意**：

 -   当前仅支持设置归属地为中国大陆地区。
-   95号码不区分地区，如果购买95号码，则该参数应指定为**全国通用**。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|SpecId|Long|是|1|号码类型。其中：

 -   1表示虚商号码，即170或171。
-   2表示运营商号码。
-   3表示95号码。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|BuySecretNo|系统规定参数。取值：**BuySecretNo**。

 |
|DisplayPool|Boolean|否|true|是否将该号码置于显号池。

 **说明：** 该参数仅对开通显号功能的客户生效。

 |
|SecretNo|String|否|130|指定号码前缀。购买号码时，如果指定**SecretNo**，会根据指定的号码前缀模糊匹配手机号。

 最长可指定18位号码前缀。

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
|RequestId|String|2D1AEB96-96D0-454E-B0DC-AE2A8DF08020|请求ID。

 |
|SecretBuyInfoDTO| | |接口调用成功后返回的结构体。

 |
|└SecretNo|String|17100000000|隐私号码，即X号码。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?City=杭州
&PoolKey=FC123456
&SpecId=1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BuySecretNoResponse>
  <SecretBuyInfoDTO>
    <SecretNo>17100000000</SecretNo>
  </SecretBuyInfoDTO>
  <Message>OK</Message>
  <RequestId>2D1AEB96-96D0-454E-B0DC-AE2A8DF08020</RequestId>
  <Code>OK</Code>
</BuySecretNoResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SecretBuyInfoDTO":{
		"SecretNo":"17100000000"
	},
	"Message":"OK",
	"RequestId":"2D1AEB96-96D0-454E-B0DC-AE2A8DF08020",
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

