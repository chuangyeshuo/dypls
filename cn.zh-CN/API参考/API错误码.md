# API错误码 {#concept_c53_fyj_ygb .concept}

调用API接口失败时，会返回接口调用错误码。本文档提供API接口错误码列表，请根据错误码和对应错误信息排查问题。

常见接口调用错误码请参考下表：

|错误码（Code）|错误信息（Message）|
|:--------|:------------|
|OK|OK|
|isp.RAM\_PERMISSION\_DENY|RAM权限DENY|
|isv.OUT\_OF\_SERVICE|业务停机|
|isv.PRODUCT\_UN\_SUBSCRIPT|未开通云通信产品的阿里云客户|
|isv.ACCOUNT\_NOT\_EXISTS|账户不存在|
|isv.ACCOUNT\_ABNORMAL|账户异常|
|isp.SYSTEM\_ERROR|isp.SYSTEM\_ERROR|
|isp.UNKNOWN\_ERR\_CODE|运营商未知错误|
|isv.PARTNER\_NOT\_EXIST|未知合作伙伴|
|isv.NO\_NOT\_EXIST|号码不存在|
|isv.ILLEGAL\_ARGUMENT|参数非法|
|isp.DAO\_EXCEPTION|数据库异常|
|isv.NO\_AVAILABLE\_NUMBER|无可用号码|
|isp.VENDOR\_UNAVAILABLE|运营商降级|
|isv.FLOW\_LIMIT|业务流控|
|isv.PARTNER\_IS\_CLOSED|partner被关停|
|isv.FORBIDDEN\_ACTION|无权操作|
|isv.NO\_USED\_BY\_OTHERS|号码被其他业务方占用|
|isv.VENDOR\_BIND\_FAILED|运营商绑定失败|
|isv.EXPIRE\_DATE\_ILLEGAL|过期时间非法|
|isv.MOBILE\_NUMBER\_ILLEGAL|号码格式非法|
|isv.BIND\_CONFLICT|绑定冲突|

