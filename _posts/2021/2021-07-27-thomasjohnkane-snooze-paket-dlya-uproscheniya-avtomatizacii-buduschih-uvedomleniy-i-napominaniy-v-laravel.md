---
title: "thomasjohnkane/snooze - пакет для упрощения автоматизации будущих уведомлений и напоминаний в Laravel"
date: ""
categories: 
  - "php"
tags: 
  - "laravel"
  - "notify"
  - "schedule"
  - "snooze"
---

```
use Thomasjohnkane\\Snooze\\Traits\\SnoozeNotifiable;

class User extends Model {
    use SnoozeNotifiable;

    // ...
}

// Schedule a birthday notification
$user->notifyAt(new BirthdayNotification, Carbon::parse($user->birthday));

// Schedule for a week from now
$user->notifyAt(new NextWeekNotification, Carbon::now()->addDays(7));

// Schedule for new years eve
$user->notifyAt(new NewYearNotification, Carbon::parse('last day of this year'));
```

  
[https://github.com/thomasjohnkane/snooze](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3Rob21hc2pvaG5rYW5lL3Nub296ZQ%3D%3D)
