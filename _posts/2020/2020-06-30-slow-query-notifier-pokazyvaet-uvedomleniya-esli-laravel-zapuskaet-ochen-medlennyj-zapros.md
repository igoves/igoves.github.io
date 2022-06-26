---
title: "slow-query-notifier - показывает уведомления, если Laravel запускает очень медленный запрос"
date: "2020-06-30"
categories: 
  - "php"
tags: 
  - "laravel"
  - "query"
---

```
// app/Providers/AppServiceProvider.php

use SlowQueryNotifier\SlowQueryNotifierFacade as SlowQueryNotifier;

public function boot()
{
    SlowQueryNotifier::toEmail('admin@example.com');
}
```

[https://github.com/thomasjohnkane/slow-query-notifier](https://github.com/thomasjohnkane/slow-query-notifier)
