# 安装Java SDK {#concept_mlr_q2b_fhb .concept}

您可以通过直接添加Maven依赖或下载阿里云Java SDK的开发工具包的方式安装阿里云Java SDK。

**说明：** 无论通过何种方式安装Java SDK，都必须安装阿里云Java SDK核心库。

## 前提条件 {#section_e3r_ngb_fhb .section}

在安装和使用阿里云Java SDK前，确保您已经：

-   安装Java环境。阿里云Java SDK要求使用JDK1.6或更高版本。
-   已经注册阿里云账号并生成访问访问密钥（AccessKey）。详细步骤请参考[创建AccessKey](~~53045~~)。

## Java SDK安装方式 {#section_n1y_thb_fhb .section}

您可以通过以下两种方式安装Java SDK。

-   [添加Maven依赖 （推荐）](#)
-   [在集成开发环境中导入JAR文件](#)

## 添加Maven依赖 （推荐） {#section_gjk_qgb_fhb .section}

如果您使用Maven管理Java项目，可以通过在pom.xml文件中添加Maven依赖安装Java 阿里云SDK。您可以在Maven库中查看各云产品的Maven依赖信息。

添加以下依赖安装阿里云Java SDK核心库。

```
<dependency>
    <groupId>com.aliyun</groupId>
    <artifactId>aliyun-java-sdk-core</artifactId>
    <version>4.1.0</version>
</dependency>
```

在安装完成后，您可以使用[OpenAPI Explorer](https://api.aliyun.com/#/?product=Dysmsapi&lang=JAVA)来生成相关API的Demo并应用在您的项目中。

## 在集成开发环境中导入JAR文件 {#section_n3d_rgb_fhb .section}

无论您使用Eclipse还是IntelliJ作为集成开发环境，都可以通过导入[aliyu-java-sdk-core JAR文件](http://sdk-release2.oss-cn-hangzhou.aliyuncs.com/tarfiles/aliyun-java-sdk-core-4.1.0.jar)的方式安装阿里云Java SDK。

-   **Eclipse**

    使用Eclipse完成以下操作，在Eclipse的项目中安装阿里云Java SDK：

    1.  将下载的aliyun-java-sdk-core.jar文件复制到您的项目文件夹中。
    2.  在Eclipse中打开您的项目，右键单击该项目，单击Properties。
    3.  在弹出的对话框中，单击**Java Build Path** \> **Libraries** \> **Add JARs**添加下载的JAR文件。
    4.  单击**Apply and Close**。
-   **IntelliJ**

    使用IntelliJ完成以下操作，在IntelliJ的项目中安装阿里云Java SDK。

    1.  将下载的aliyun-java-sdk-core.jar文件复制到您的项目文件夹中。
    2.  在IntelliJ中打开您的项目，在菜单栏中单击**File** \> **Project Structure**。
    3.  单击**Apply**，然后单击OK。

在安装完成后，您可以使用[OpenAPI Explorer](https://api.aliyun.com/#/?product=Dysmsapi&lang=JAVA)来生成相关API的Demo并应用在您的项目中。

## Java SDK GitHub地址 {#section_fbm_lzg_fhb .section}

[Java SDK核心库](https://github.com/aliyun/aliyun-openapi-java-sdk/tree/master/aliyun-java-sdk-core)

