---
title: "telegram-api - пхп апи для создание бота телеграм"
date: ""
categories: 
  - "php"
---

![telegram-api - пхп апи для создание бота телеграм ](images/logo-php7-telegram-bot-api-small.png "telegram-api - пхп апи для создание бота телеграм ")

  

```
<?php

use \\unreal4u\\TelegramAPI\\HttpClientRequestHandler;
use \\unreal4u\\TelegramAPI\\TgLog;
use \\unreal4u\\TelegramAPI\\Telegram\\Methods\\SendMessage;

$loop = \\React\\EventLoop\\Factory::create();
$handler = new HttpClientRequestHandler($loop);
$tgLog = new TgLog(BOT_TOKEN, $handler);

$sendMessage = new SendMessage();
$sendMessage->chat_id = A_USER_CHAT_ID;
$sendMessage->text = 'Hello world!';

$tgLog->performApiRequest($sendMessage);
$loop->run();
```

  
[https://github.com/unreal4u/telegram-api](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3VucmVhbDR1L3RlbGVncmFtLWFwaQ%3D%3D)
