---
title: "NovaGram - php api для телеграм бота"
date: "2020-12-31"
categories: 
  - "php"
tags: 
  - "api"
  - "bot"
  - "telegram"
---

Поддерживает все команды Bot Api 5.0

```
use skrtdev\NovaGram\Bot;
use skrtdev\Telegram\Message;

$Bot = new Bot("YOUR_TOKEN");

$Bot->onCommand("start", function (Message $message) use ($Bot) {
    $message->reply("Hey! Nice to meet you. Use /info to know more about me.");
});

$Bot->onCommand("info", function (Message $message) use ($Bot) {
    $message->reply("Well, I'm just an example, but you can learn more about NovaGram at docs.novagram.ga");
});
```

[https://github.com/skrtdev/NovaGram](https://github.com/skrtdev/NovaGram)
