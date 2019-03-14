# CreateAxgGroup {#doc_api_1058879 .reference}

调用接口CreateAxgGroup创建G号码组。

在AXG号码绑定前，除了购买X号码以外，还必须创建一个G号码组，并在G号码组中添加号码。如果创建G号码组时没有同时添加号码，还可以调用**OperateAxgGroup**接口添加号码。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=CreateAxgGroup)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|CreateAxgGroup|系统规定参数。取值：**CreateAxgGroup**。

 |
|Name|String|否|测试分组|G号码组名称。如果未指定G号码组名称，将以G号码组的ID作为名称。

 取值范围为1~128个字符，支持中文和英文。

 |
|Numbers|String|否|15800000000,15900000000|向新建的G分组中添加的电话号码，多个号码之间用英文逗号（,）分隔，创建时最多添加200个号码。

 |
|Remark|String|否|测试用分组|G号码组的备注信息。取值范围为0~256个字符，支持中文和英文。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~109196~~)。

 |
|GroupId|Long|2000000000001|新建的G号码组的ID，即GID。通过接口BindAXG绑定号码时需要输入此参数。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|635C0FDA-9EBC-43D7-B368-9F583C08A126|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateAxgGroupResponse>
  <Message>OK</Message>
  <RequestId>635C0FDA-9EBC-43D7-B368-9F583C08A126</RequestId>
  <Code>OK</Code>
  <GroupId>2000000000001</GroupId>
</CreateAxgGroupResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"635C0FDA-9EBC-43D7-B368-9F583C08A126",
	"GroupId":2000000000001,
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyplsapi)

