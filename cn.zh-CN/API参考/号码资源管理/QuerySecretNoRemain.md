# QuerySecretNoRemain {#doc_api_Dyplsapi_QuerySecretNoRemain .reference}

调用接口QuerySecretNoRemain查询线上可购号码余量。

购买号码时，指定归属地如果没有足够号码可供购买，会造成号码购买失败。调用接口BuySecretNo购买号码前，请先通过接口QuerySecretNoRemain查询线上可购号码余量。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=QuerySecretNoRemain)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|City|String|是|杭州|号码的归属地。

 -   **SpecId**设置为1或2时，可以在参数**City**中指定查询

 1. 支持输入单个城市名称查询。

 2. 支持输入“全国”查询，可返回全国可购号码余量。

 3. 支持输入“全国列表”查询，将返回全国城市中有号码的城市及数量，无号码的城市不会返回。

 -   **SpecId**设置为3时，95号码不区分归属地，只能查询全部95号码可购余量，即必须指定**City**为**全国通用**。

 **说明：** 当前仅支持设置归属地为中国大陆地区。

 |
|SpecId|Long|是|1|号码类型。其中：

 -   1表示虚商号码，即170或171。
-   2表示运营商号码。
-   3表示95号码。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QuerySecretNoRemain|系统规定参数。取值：**QuerySecretNoRemain**。

 |
|SecretNo|String|否|130|号码前缀。查询可购号码余量时，如果指定**SecretNo**，表示查询指定前缀的号码余量。

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
|RequestId|String|9FC30594-3841-43AD-9008-03393BCB5CD2|请求ID。

 |
|SecretRemainDTO| | |接口调用成功后返回的结构体。

 |
|└Amount|Long|0|可购号码余量。

 |
|└City|String|杭州|号码的归属地。

 |
|└RemainDTOList| | |【全国列表】模式下，接口调用成功后返回的结构体。

 |
|└Amount|Long|5|可购号码余量。

 |
|└City|String|北京|可购号码城市。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?City=杭州
&SpecId=1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QuerySecretNoRemainResponse>
  <SecretRemainDTO>
    <Amount>0</Amount>
    <City>杭州</City>
  </SecretRemainDTO>
  <Message>OK</Message>
  <RequestId>9FC30594-3841-43AD-9008-03393BCB5CD2</RequestId>
  <Code>OK</Code>
</QuerySecretNoRemainResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SecretRemainDTO":{
		"Amount":0,
		"City":"杭州"
	},
	"Message":"OK",
	"RequestId":"9FC30594-3841-43AD-9008-03393BCB5CD2",
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

