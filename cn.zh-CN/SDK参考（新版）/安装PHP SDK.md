# 安装PHP SDK {#concept_wqb_ytb_fhb .concept}

您可以通过直接添加阿里云SDK依赖包的方式安装阿里云PHP SDK。

## 前提条件 {#section_e3r_ngb_fhb .section}

在安装和使用阿里云PHP SDK前，确保您已经：

-   请确认您的系统满足[环境要求](https://github.com/aliyun/openapi-sdk-php-client/blob/master/docs/zh/0-Prerequisites.md)。
-   已经注册阿里云账号并生成访问访问密钥（AccessKey）。详细步骤请参考[创建AccessKey](~~53045~~)。

**说明：** 强烈建议使用cURL扩展，并使用TLS后端编译cURL 7.16.2+。

## 安装步骤 {#section_n5w_dvb_fhb .section}

请参考以下步骤，使用Composer安装依赖。

如果在您的系统上全局安装Composer，您可以在项目目录中运行以下内容，将 Alibaba Cloud Client for PHP 添加为依赖项。

``` {#codeblock_m9c_43e_bnh}
composer require alibabacloud/client
```

通过 Composer 和其他方式安装的详细信息，请查看[安装说明](https://github.com/aliyun/openapi-sdk-php-client/blob/master/docs/zh/1-Installation.md)。

在安装完成后，您可以使用[OpenAPI Explorer](https://api.aliyun.com/#/?product=Dysmsapi&lang=PHP)来生成相关API的Demo，并应用在您的项目中。如需了解更多，请参考更详细的[安装及使用指南](https://github.com/aliyun/openapi-sdk-php-client)。

## PHP SDK GitHub地址 {#section_fbm_lzg_fhb .section}

[PHP SDK核心库](https://github.com/aliyun/openapi-sdk-php-client)

