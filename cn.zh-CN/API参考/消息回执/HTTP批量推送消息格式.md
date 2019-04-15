# HTTP批量推送消息格式 {#concept_osb_ck5_hhb .concept}

在控制台设置HTTP回调URL（callback\_url）后，在业务消息产生时，系统会使用HTTP请求以POST方式将业务消息发送到指定的回调URL上，用户可直接接收此消息。本文档介绍HTTP批量推送模式的消息结构。

## 接口规范 {#section_qcg_3k5_hhb .section}

|参数|说明|
|--|--|
|协议|HTTP + JSON|
|请求方式|POST|
|编码|UTF-8|
|超时时间|3秒|

## 请求参数 {#section_w15_rk5_hhb .section}

各种回执消息的请求参数请查看对应文档。

-   [呼叫发起时话单报告（SecretStartReport）](cn.zh-CN/API参考/消息回执/SecretStartReport.md)
-   [呼叫结束后话单报告（SecretReport）](cn.zh-CN/API参考/消息回执/SecretReport.md)
-   [录音状态报告（SecretSmsIntercept）](cn.zh-CN/API参考/消息回执/SecretSmsIntercept.md)
-   [短信内容报告（SecretRecording）](cn.zh-CN/API参考/消息回执/SecretRecording.md)

## 返回参数 {#section_jjx_nk5_hhb .section}

|名称|类型|描述|示例值|是否必须|
|--|--|--|---|----|
|code|Number|应答编码|0|必须|
|msg|String|描述信息|接收成功|可选|

## 示例 {#section_gtd_kk5_hhb .section}

-   **请求示例**

    请求内容为JSON Array格式，单次请求可能会包含多个通话记录。

    ```
    [
      {
        "id" : 12345678,
        "partner_key" : "AB_CD",
        "out_id" : "12345678",
        "sub_id" : 12345678,
        "call_id" : "12345678",
        "call_type" : 1,
        "origin_no" : "12345678",
        "phone_no" : "13800000000",
        "secret_no" : "13800000001",
        "peer_no" : "13800000002",
        "release_dir" : 1,
        "release_cause" : 1,
        "start_time" : "2017-01-01 00:00:00",
        "release_time" : "2017-01-01 00:00:00",
        "call_time" : "2017-01-01 00:00:00",
        "ring_time" : "2017-01-01 00:00:00"
      }
    ]
    ```

-   **请求示例**

    ```
    {
      "code" : 0,
      "msg" : "接收成功"
    }
    ```


