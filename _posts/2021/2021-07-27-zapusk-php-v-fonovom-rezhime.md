---
title: "Запуск php в фоновом режиме"
date: ""
categories: 
  - "php"
tags: 
  - "php"
  - "fonovyy-rejim"
---

  

```
<?phpfunction doSomthing(){    // here we do somthing on server side}ignore_user_abort(false);if (ob_get_level() == 0)    ob_start();// redirect lient to some site or abort connecionheader("Location: http://www.example.com/");ob_flush();flush();$counter = 1;while (true){     ob_flush();    flush();    sleep(1);    doSomthing();    $counter++;    if ($counter == 30)        break;}ob_end_flush();?>
```

  
Вот такие дела, остановился все же на CRON\\'e без гемморно и по моему правильней всего -)
