---
title: "JoliNotif - отправка уведомлений на рабочем столе из php приложения"
date: "2020-12-30"
categories: 
  - "php"
tags: 
  - "desktop"
  - "notify"
---

![](images/demo.gif)

Работает на Linux, Windows или MacOS.

```
include __DIR__.'/vendor/autoload.php';

use Joli\JoliNotif\Notification;
use Joli\JoliNotif\NotifierFactory;

// Create a Notifier
$notifier = NotifierFactory::create();

// Create your notification
$notification =
    (new Notification())
    ->setTitle('Notification title')
    ->setBody('This is the body of your notification')
    ->setIcon(__DIR__.'/path/to/your/icon.png')
    ->addOption('subtitle', 'This is a subtitle') // Only works on macOS (AppleScriptNotifier)
    ->addOption('sound', 'Frog') // Only works on macOS (AppleScriptNotifier)
;

// Send it
$notifier->send($notification);
```

[https://github.com/jolicode/JoliNotif](https://github.com/jolicode/JoliNotif)
