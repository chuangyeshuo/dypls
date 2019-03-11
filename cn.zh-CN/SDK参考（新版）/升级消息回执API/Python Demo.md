# Python Demo {#concept_pv1_ckl_3gb .concept}

依赖Python语言的阿里云SDK核心库及dybaseapi，其中dybaseapi包用于拉取MNS消息。

-   [阿里云SDK核心库（Python）](https://github.com/aliyun/aliyun-openapi-python-sdk/tree/master/aliyun-python-sdk-core)
-   [dybaseapi （Python）](https://github.com/aliyun/aliyun-openapi-python-sdk/tree/master/aliyun-python-sdk-dybaseapi)

Demo如下：

```
#!/usr/bin/env python
# coding=utf8

import time
from aliyunsdkcore.acs_exception.exceptions import ServerException
from aliyunsdkcore.client import AcsClient
from aliyunsdkdybaseapi.request.v20170525.QueryTokenForMnsQueueRequest import QueryTokenForMnsQueueRequest
from aliyunsdkcore.profile import region_provider
from datetime import datetime
from aliyunsdkdybaseapi.mns.account import Account
from aliyunsdkdybaseapi.mns.queue import *
from aliyunsdkdybaseapi.mns.mns_exception import *

try:
    import json
except ImportError:
    import simplejson as json


# TODO 需要替换成您需要接收的消息类型
message_type = "<MessageType>"
# TODO 需要替换成您的队列名称。在云通信页面开通相应业务消息后，就能在页面上获得对应的queueName
queue_name = "<QueueName>"

# 云通信固定的endpoint地址
endpoint = "http://1943695596114318.mns.cn-hangzhou.aliyuncs.com"

acs_client = AcsClient("<AccessKeyId>", "<AccessKeySecret>", "cn-hangzhou")
region_provider.add_endpoint("Dybaseapi", "dybaseapi.aliyuncs.com", "cn-hangzhou")


# 云通信业务token存在失效时间，需动态更新。
class Token():
    def __init__(self):
        self.token = None
        self.tmp_access_id = None
        self.tmp_access_key = None
        self.expire_time = None

    def is_refresh(self):
        if self.expire_time is None:
            return 1
        # 失效时间与当前系统时间比较，提前2分钟刷新token
        now = datetime.now()
        expire = datetime.strptime(self.expire_time, "%Y-%m-%d %H:%M:%S")
        if expire <= now or (expire - now).seconds < 120:
            return 1
        return 0

    def refresh(self):
        print("start refresh token...")
        request = QueryTokenForMnsQueueRequest()
        request.set_MessageType(message_type)
        request.set_QueueName(queue_name)
        response = acs_client.do_action_with_exception(request)
        # print response
        if response is None:
            raise ServerException("GET_TOKEN_FAIL", "获取token时无响应")

        response_body = json.loads(response)

        if response_body.get("Code") != "OK":
            raise ServerException("GET_TOKEN_FAIL", "获取token失败")

        sts_token = response_body.get("MessageTokenDTO")
        self.tmp_access_key = sts_token.get("AccessKeySecret")
        self.tmp_access_id = sts_token.get("AccessKeyId")
        self.expire_time = sts_token.get("ExpireTime")
        self.token = sts_token.get("SecurityToken")

        print("finish refresh token...")


# 初始化 token, my_account, my_queue
token, my_account, my_queue = Token(), None, None

# 循环读取删除消息直到队列空
# receive message请求使用long polling方式，通过wait_seconds指定长轮询时间为3秒

## long polling 解析:
### 当队列中有消息时，请求立即返回；
### 当队列中没有消息时，请求在MNS服务器端挂3秒钟，在这期间，有消息写入队列，请求会立即返回消息，3秒后，请求返回队列没有消息；

wait_seconds = 3
print("%sReceive And Delete Message From Queue%s\nQueueName:%s\nWaitSeconds:%s\n" % (
    10 * "=", 10 * "=", queue_name, wait_seconds))

while True:
    receipt_handles = []
    # 读取消息
    try:
        # token过期是否需要刷新
        if token.is_refresh() == 1:
            # 刷新token
            token.refresh()
            if my_account:
                my_account.mns_client.close_connection()
                my_account = None

        if not my_account:
            my_account = Account(endpoint, token.tmp_access_id, token.tmp_access_key, token.token)
            my_queue = my_account.get_queue(queue_name)

        # 接收消息
        recv_msgs = my_queue.batch_receive_message(10, wait_seconds)

        for recv_msg in recv_msgs:
            # TODO 业务处理

            # receipt_handles.append(recv_msg.receipt_handle)
            print("Receive Message Succeed! ReceiptHandle:%s MessageBody:%s MessageID:%s" % (
                recv_msg.receipt_handle, recv_msg.message_body, recv_msg.message_id))

    except MNSExceptionBase as e:
        if e.type == "QueueNotExist":
            print("Queue not exist, please create queue before receive message.")
            break
        elif e.type == "MessageNotExist":
            print("Queue is empty! sleep 10s")
            time.sleep(10)
            continue
        print("Receive Message Fail! Exception:%s\n" % e)
        break

    # 删除消息
    try:
        if len(receipt_handles) > 0:
            # my_queue.delete_message(receipt_handles)
            print("Delete Message Succeed!  ReceiptHandles:%s" % receipt_handles)
    except MNSExceptionBase as e:
        print("Delete Message Fail! Exception:%s\n" % e)
```

