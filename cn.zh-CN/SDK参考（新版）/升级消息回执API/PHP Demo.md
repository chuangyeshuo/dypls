# PHP Demo {#concept_mcx_zjl_3gb .concept}

依赖OpenAPI PHP Client包和OpenAPI PHP SDK包。

-   OpenAPI PHP Client

-   下载地址：[openapi-sdk-php-client](https://github.com/aliyun/openapi-sdk-php-client)

-   安装说明[OpenAPI PHP Client 安装说明](https://github.com/aliyun/openapi-sdk-php-client/blob/master/README-CN.md)

-   OpenAPI PHP SDK

-   下载地址：[openapi-sdk-php](https://github.com/aliyun/openapi-sdk-php)

-   安装说明[OpenAPI PHP SDK 安装说明](https://github.com/aliyun/openapi-sdk-php/blob/master/README-CN.md)


Demo如下：

```
<?php
use AlibabaCloud\Client\AlibabaCloud;
use AlibabaCloud\Client\Exception\ClientException;
use AlibabaCloud\Client\Exception\ServerException;
use AlibabaCloud\Dybaseapi\MNS\Requests\BatchReceiveMessage;
use AlibabaCloud\Dybaseapi\MNS\Requests\BatchDeleteMessage;

AlibabaCloud::accessKeyClient('<AccessKeyId>', '<AccessSecret>')
    ->regionId('cn-hangzhou')
    ->asGlobalClient();

$queueName = '<QueueName>'; // 队列名称
$messageType = '<MessageType>'; // 需要接收的消息类型

$response = null;
$token = null;
$i = 0;

do {
    try {
        if (null == $token || strtotime($token['ExpireTime']) - time() > 2 * 60) {
            $response = AlibabaCloud::rpcRequest()
                ->product('Dybaseapi')
                ->version('2017-05-25')
                ->action('QueryTokenForMnsQueue')
                ->method('POST')
                ->host("dybaseapi.aliyuncs.com")
                ->options([
                    'query' => [
                        'MessageType' => $messageType,
                        'QueueName' => $queueName,
                    ],
                ])
                ->request()
                ->toArray();
        }

        $token = $response['MessageTokenDTO'];

        $mnsClient = new \AlibabaCloud\Dybaseapi\MNS\MnsClient(
            "http://1943695596114318.mns.cn-hangzhou.aliyuncs.com",
            $token['AccessKeyId'],
            $token['AccessKeySecret'],
            $token['SecurityToken']
        );
        $mnsRequest = new BatchReceiveMessage(10, 5);
        $mnsRequest->setQueueName($queueName);
        $mnsResponse = $mnsClient->sendRequest($mnsRequest);

        $receiptHandles = Array();
        foreach ($mnsResponse->Message as $message) {
            // 用户逻辑：
            // $receiptHandles[] = $message->ReceiptHandle; // 加入$receiptHandles数组中的记录将会被删除
            $messageBody = base64_decode($message->MessageBody); // base64解码后的JSON字符串
            print_r($messageBody . "\n");
        }

        if (count($receiptHandles) > 0) {
            $deleteRequest = new BatchDeleteMessage($queueName, $receiptHandles);
            $mnsClient->sendRequest($deleteRequest);
        }
    } catch (ClientException $e) {
        echo $e->getErrorMessage() . PHP_EOL;
    } catch (ServerException $e) {
        if ($e->getCode() == 404) {
            $i++;
        }
        echo $e->getErrorMessage() . PHP_EOL;
    }
} while ($i < 3);
```

