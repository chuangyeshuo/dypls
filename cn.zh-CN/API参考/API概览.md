# API概览 {#concept_ckp_tjk_zgb .concept}

本文档为您展示号码隐私保护所有可调用的API接口，详细接口信息请参考对应接口文档。

更多 API 资源，请访问 [OpenAPI Explorer](https://api.aliyun.com/)。

## 号码绑定 {#section_ix1_xcs_ggb .section}

|API|描述|
|:--|:-|
|[BindAxb](cn.zh-CN/API参考/号码绑定/BindAxb.md)|添加AXB号码的绑定关系。|
|[BindAxn](cn.zh-CN/API参考/号码绑定/BindAxn.md)|添加AXN号码的绑定关系。|
|[BindAxnExtension](cn.zh-CN/API参考/号码绑定/BindAxnExtension.md)|添加AXN分机号码的绑定关系。|
|[BindAxg](cn.zh-CN/API参考/号码绑定/BindAxg.md)|添加AXG号码的绑定关系。|
|[CreateAxgGroup](cn.zh-CN/API参考/号码绑定/CreateAxgGroup.md)|创建G号码组。|
|[OperateAxgGroup](cn.zh-CN/API参考/号码绑定/OperateAxgGroup.md)|修改G号码组。|
|[UpdateSubscription](cn.zh-CN/API参考/号码绑定/UpdateSubscription.md)|修改绑定关系。|
|[UnbindSubscription](cn.zh-CN/API参考/号码绑定/UnbindSubscription.md)|解除号码的绑定关系。|

## 状态查询 {#section_ktk_xcs_ggb .section}

|API|描述|
|:--|:-|
|[QueryCallStatus](cn.zh-CN/API参考/状态查询/QueryCallStatus.md)|查询呼叫状态。|
|[QuerySubscriptionDetail](cn.zh-CN/API参考/状态查询/QuerySubscriptionDetail.md)|查询号码的绑定关系。|

## 录音文件 {#section_uzn_2kk_zgb .section}

|API|描述|
|:--|:-|
|[QueryRecordFileDownloadUrl](cn.zh-CN/API参考/录音文件/QueryRecordFileDownloadUrl.md)|获取录音文件的下载链接。|

## 号码资源管理 {#section_kh2_hkk_zgb .section}

|API|描述|
|:--|:-|
|[QuerySecretNoRemain](cn.zh-CN/API参考/号码资源管理/QuerySecretNoRemain.md)|查询线上可购号码余量。|
|[BuySecretNo](cn.zh-CN/API参考/号码资源管理/BuySecretNo.md)|购买号码。|
|[ReleaseSecretNo](cn.zh-CN/API参考/号码资源管理/ReleaseSecretNo.md)|释放号码。|

## 回执消息 {#section_z1s_xcs_ggb .section}

|API|描述|
|:--|:-|
|[SecretStartReport](cn.zh-CN/API参考/消息回执/SecretStartReport.md)|接收通话发起时的通话记录报告内容，可以在呼叫发起时立即获取到通话记录信息，包括通话开始时间、主被叫号码等，便于平台进行预判处理。|
|[SecretReport](cn.zh-CN/API参考/消息回执/SecretReport.md)|接收通话结束时的通话记录报告内容，可以在呼叫结束后获取通话记录信息，包括通话开始时间、通话结束时间、主被叫号码等，便于平台进行管理。|
|[SecretSmsIntercept](cn.zh-CN/API参考/消息回执/SecretSmsIntercept.md)|接收短信内容报告，可以获取到短信发送后的内容记录，包括短信发送方、接收方、发送时间等信息，便于平台进行短信管理。|
|[SecretRecording](cn.zh-CN/API参考/消息回执/SecretRecording.md)|接收录音状态报告，可以获取到通话完成后的录音记录，消息内容包括录音下载的链接，便于平台进行录音管理。|

