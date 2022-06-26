---
title: "Hoa\\Websocket  - вебсокет библиотека"
date: ""
categories: 
  - "php"
---

Имеет в себе 6 слушателей: open, message, binary-message, ping, close and error  
Пример

```
$websocket = new Hoa\\Websocket\\Server(
    new Hoa\\Socket\\Server('ws://127.0.0.1:8889')
);
$websocket->on('open', function (Hoa\\Event\\Bucket $bucket) {
    echo 'new connection', "\\n";

    return;
});
$websocket->on('message', function (Hoa\\Event\\Bucket $bucket) {
    $data = $bucket->getData();
    echo '> message ', $data['message'], "\\n";
    $bucket->getSource()->send($data['message']);
    echo '< echo', "\\n";

    return;
});
$websocket->on('close', function (Hoa\\Event\\Bucket $bucket) {
    echo 'connection closed', "\\n";

    return;
});
$websocket->run();
```

  
[https://github.com/hoaproject/websocket](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2hvYXByb2plY3Qvd2Vic29ja2V0)
