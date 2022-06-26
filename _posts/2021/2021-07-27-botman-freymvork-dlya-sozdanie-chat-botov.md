---
title: "botman - фреймворк для создание чат-ботов"
categories: 
  - "php"
---

Включает в себя поддержку Slack, Telegram, Microsoft Bot Framework, Nexmo, HipChat, Facebook Messenger and WeChat  

```
use Mpociot\\BotMan\\BotManFactory;
use Mpociot\\BotMan\\BotMan;

$config = [
    'hipchat_urls' => [
        'YOUR-INTEGRATION-URL-1',
        'YOUR-INTEGRATION-URL-2',
    ],
    'nexmo_key' => 'YOUR-NEXMO-APP-KEY',
    'nexmo_secret' => 'YOUR-NEXMO-APP-SECRET',
    'microsoft_bot_handle' => 'YOUR-MICROSOFT-BOT-HANDLE',
    'microsoft_app_id' => 'YOUR-MICROSOFT-APP-ID',
    'microsoft_app_key' => 'YOUR-MICROSOFT-APP-KEY',
    'slack_token' => 'YOUR-SLACK-TOKEN-HERE',
    'telegram_token' => 'YOUR-TELEGRAM-TOKEN-HERE',
    'facebook_token' => 'YOUR-FACEBOOK-TOKEN-HERE',
    'facebook_app_secret' => 'YOUR-FACEBOOK-APP-SECRET-HERE', // Optional - this is used to verify incoming API calls,
    'wechat_app_id' => 'YOUR-WECHAT-APP-ID',
    'wechat_app_key' => 'YOUR-WECHAT-APP-KEY',
];

// create an instance
$botman = BotManFactory::create($config);

// give the bot something to listen for.
$botman->hears('hello', function (BotMan $bot) {
    $bot->reply('Hello yourself.');
});

// start listening
$botman->listen();
```

  
[https://github.com/mpociot/botman](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21wb2Npb3QvYm90bWFu)
