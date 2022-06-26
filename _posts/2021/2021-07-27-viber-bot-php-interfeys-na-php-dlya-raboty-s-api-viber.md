---
title: "viber-bot-php - интерфейс на php для работы с API viber"
categories: 
  - "php"
---

**Пример**  

```
<?php

require_once("../vendor/autoload.php");

use Viber\\Bot;
use Viber\\Api\\Sender;

$apiKey = '<PLACE-YOU-API-KEY-HERE>';

// reply name
$botSender = new Sender([
    'name' => 'Whois bot',
    'avatar' => 'https://developers.viber.com/img/favicon.ico',
]);

try {
    $bot = new Bot(['token' => $apiKey]);
    $bot
    ->onConversation(function ($event) use ($bot, $botSender) {
        // this event fires if user open chat, you can return "welcome message"
        // to user, but you can't send more messages!
        return (new \\Viber\\Api\\Message\\Text())
            ->setSender($botSender)
            ->setText("Can i help you?");
    })
    ->onText('|whois .*|si', function ($event) use ($bot, $botSender) {
        // match by template, for example "whois Bogdaan"
        $bot->getClient()->sendMessage(
            (new \\Viber\\Api\\Message\\Text())
            ->setSender($botSender)
            ->setReceiver($event->getSender()->getId())
            ->setText("I do not know )")
        );
    })
    ->run();
} catch (Exception $e) {
    // todo - log exceptions
}
```

  
[https://github.com/bogdaan/viber-bot-php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2JvZ2RhYW4vdmliZXItYm90LXBocA%3D%3D)
