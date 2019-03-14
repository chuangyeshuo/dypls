# OperateAxgGroup {#doc_api_1058878 .reference}

调用接口OperateAxgGroup修改G号码组。

创建G号码组之后，可以通过接口**OperateAxgGroup**修改G号码组，例如向G号码组中增加号码、删除号码、全量替换号码。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyplsapi&api=OperateAxgGroup)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|GroupId|Long|是|1234|AXG中的G组ID，即GID。

 可以通过以下方式查看GID：

 -   在[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)中的**号码池管理**页面筛选出**AXG隐私号**，并单击**G号码组管理**即可查看所有G号码组的GID。
-   如果G号码组是通过接口**CreateAxgGroup**创建的，则接口的返回参数**GroupID**就是此处的请求参数**GroupID**。

 |
|Numbers|String|是|15800000000,15900000000|向新建的G分组中添加的电话号码，多个号码之间用英文逗号（,）分隔，每次最多添加200个号码。

 |
|OperateType|String|是|addNumbers|对G号码组的操作类型，包括：

 -   **addNumbers**：添加号码。
-   **deleteNumbers**：删除号码。
-   **overwriteNumbers**：全量替换号码。会将G号码组中原有的电话号码全部删除，并重新添加号码。**说明**：
-   全量替换号码时，G号码组中原有的号码不能超过200个。
-   每次添加号码时，最多添加200个号码。

 |
|PoolKey|String|是|FC123456|号码池Key。请登录[号码隐私保护控制台](https://dypls.console.aliyun.com/dypls.htm#/account)，在**号码池管理**中查看号码池Key。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|OperateAxgGroup|系统规定参数。取值：**OperateAxgGroup**。

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

http(s)://[Endpoint]/?GroupId=1234
&Numbers=15800000000,15900000000	
&OperateType=addNumbers
&PoolKey=FC123456
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<OperateAxgGroupResponse>
  <Message>OK</Message>
  <RequestId>986BCB6D-C9BF-42F9-91CE-3A9901233D36</RequestId>
  <Code>OK</Code>
</OperateAxgGroupResponse>

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

