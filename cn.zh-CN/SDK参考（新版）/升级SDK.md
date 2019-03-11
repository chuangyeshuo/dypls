# 升级SDK {#concept_amg_2df_zgb .concept}

 新SDK源码已经托管至开源平台Github，可使用GitHub clone的方式使用SDK，也可以使用依赖管理工具安装，Demo代码可通过OpenAPI Explorer生成，所有SDK均只依赖SDK核心库，使用通用的Request及Response来处理接口请求及响应。

## JAVA SDK {#section_ljt_hjl_3gb .section}

下载地址：[JAVA SDK](https://github.com/aliyun/aliyun-openapi-java-sdk/tree/master/aliyun-java-sdk-core) 

新版JAVA SDK仅依赖阿里云JAVA SDK核心库，可使用maven安装依赖，使用CommonRequest、CommonResponse来处理接口请求及响应。请使用CommonRequest实例的putQueryParameter方法设置API参数，CommonResponse实例使用getData方法获取API结果的JSON字符串。

**说明：** 通过JAVA SDK拉取[消息回执](../../../../../cn.zh-CN/API参考/消息回执/简介.md)，请使用[JAVA MNS SDK](http://ytx-sdk.oss-cn-shanghai.aliyuncs.com/dypls_mns_java.zip)。

## .NET SDK {#section_mrm_3jl_3gb .section}

下载地址：[.NET SDK](https://github.com/aliyun/aliyun-openapi-net-sdk/tree/master/aliyun-net-sdk-core) 

新版.NET SDK仅依赖阿里云.NET SDK核心库，可使用NuGet安装依赖，使用CommonRequest、CommonResponse来处理接口请求及响应。 请使用CommonRequest实例的putQueryParameter方法设置API参数，CommonResponse实例使用getData方法获取API结果的JSON字符串。

## PHP SDK {#section_arh_njl_3gb .section}

下载地址：[PHP SDK](https://github.com/aliyun/openapi-sdk-php-client)

使用说明：[PHP SDK使用说明](https://github.com/aliyun/openapi-sdk-php-client/blob/master/README-CN.md)

PHP全新SDK上线，并支持composer安装，请按说明重新设置请求参数。

## Python SDK {#section_flc_4jl_3gb .section}

下载地址：[Python SDK](https://github.com/aliyun/aliyun-openapi-python-sdk/tree/master/aliyun-python-sdk-core)

python-sdk-core已统一支持Python 2.0/3.0，与原有SDK兼容，建议参考[OpenAPI Explorer](https://api.aliyun.com/#/?product=Dyplsapi&lang=PYTHON)提供的Demo重新设置请求参数。

## Node.js SDK {#section_smg_qjl_3gb .section}

详情：[@alicloud/pop-core](https://www.npmjs.com/package/@alicloud/pop-core)

新Node.js SDK仅依赖@alicloud/pop-core，与原SDK兼容。新Node.js SDK不再依赖@alicloud/pls-sdk，请参照Demo修改示例。

**说明：** 通过Node.js SDK拉取[消息回执](../../../../../cn.zh-CN/API参考/消息回执/简介.md)，请使用[原Node.js MNS SDK](https://www.npmjs.com/package/@alicloud/pls-sdk)。

## Go SDK {#section_qnk_rjl_3gb .section}

下载地址：[Go SDK](https://github.com/aliyun/alibaba-cloud-sdk-go/) 

原SDK不支持Golang，使用新SDK请直接参考新Demo即可。

