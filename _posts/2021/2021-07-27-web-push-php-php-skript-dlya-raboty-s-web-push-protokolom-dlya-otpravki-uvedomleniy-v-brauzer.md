---
title: "web-push-php - php скрипт для работы с web-push протоколом для отправки уведомлений в браузер"
categories: 
  - "php"
---

```
<?php

use Minishlink\\WebPush\\WebPush;

// array of notifications
$notifications = array(
    array(
        'endpoint' => 'https://updates.push.services.mozilla.com/push/abc...', // Firefox 43+
        'payload' => 'hello !',
        'userPublicKey' => 'BPcMbnWQL5GOYX/5LKZXT6sLmHiMsJSiEvIFvfcDvX7IZ9qqtq68onpTPEYmyxSQNiH7UD/98AUcQ12kBoxz/0s=', // base 64 encoded, should be 88 chars
        'userAuthToken' => 'CxVX6QsVToEGEcjfYPqXQw==', // base 64 encoded, should be 24 chars
    ), array(
        'endpoint' => 'https://android.googleapis.com/gcm/send/abcdef...', // Chrome
        'payload' => null,
        'userPublicKey' => null,
        'userAuthToken' => null,
    ), array(
        'endpoint' => 'https://example.com/other/endpoint/of/another/vendor/abcdef...',
        'payload' => '{msg:"test"}',
        'userPublicKey' => '(stringOf88Chars)', 
        'userAuthToken' => '(stringOf24Chars)',
    ),
);

$webPush = new WebPush();

// send multiple notifications with payload
foreach ($notifications as $notification) {
    $webPush->sendNotification(
        $notification['endpoint'],
        $notification['payload'], // optional (defaults null)
        $notification['userPublicKey'], // optional (defaults null)
        $notification['userAuthToken'] // optional (defaults null)
    );
}
$webPush->flush();

// send one notification and flush directly
$webPush->sendNotification(
    $notifications[0]['endpoint'],
    $notifications[0]['payload'], // optional (defaults null)
    $notifications[0]['userPublicKey'], // optional (defaults null)
    $notifications[0]['userAuthToken'], // optional (defaults null)
    true // optional (defaults false)
);
```

  
[https://github.com/web-push-libs/web-push-php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dlYi1wdXNoLWxpYnMvd2ViLXB1c2gtcGhw)
