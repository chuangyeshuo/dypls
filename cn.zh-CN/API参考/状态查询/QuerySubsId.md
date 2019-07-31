# QuerySubsId {#doc_api_Dyplsapi_QuerySubsId .reference}

调用接口QuerySubsId查询绑定唯一标识SubsId。

支持根据X号码查询绑定关系的唯一标识SubsId，在AXB业务中，同一个X号码可能存在多组绑定关系，查询结果会为多条。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyplsapi&api=QuerySubsId&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|是|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|是|QuerySubsId|系统规定参数。取值：**QuerySubsId**。

 |
|PhoneNoX|String|是|17000000000|绑定关系中的隐私号码，即X号码。

 |
|PoolKey|String|是|FC123456|号码池Key。可登录号码隐私保护控制台，在号码池管理中查看号码池Key。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|E7F99446-8191-43C0-99B5-F58A6AEAD779|请求ID。

 |
|SubsId|String|11111111,1111111|绑定关系ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QuerySubsId
&AccessKeyId=LTAIP00vvvvvvvvv
&PhoneNoX=17000000000
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QuerySubsIdResponse>
	  <Message>OK</Message>
	  <SubsId>117809</SubsId>
	  <RequestId>F3BC6628-7976-41BA-87D0-D152BAB2A9C8</RequestId>
	  <Code>OK</Code>
</QuerySubsIdResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"F3BC6628-7976-41BA-87D0-D152BAB2A9C8",
	"SubsId":"117809",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyplsapi)查看更多错误码。

