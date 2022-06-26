---
title: "paragonie/PHP-Cookie - скрипт для безоспасной работы с кукми на php7+"
date: ""
categories: 
  - "php"
---

```
$cookie = new \\ParagonIE\\Cookie\\Cookie('SID');
$cookie->setValue('31d4d96e407aad42');
$cookie->setMaxAge(60 * 60 * 24);
// $cookie->setExpiryTime(time() + 60 * 60 * 24);
$cookie->setPath('/~rasmus/');
$cookie->setDomain('example.com');
$cookie->setHttpOnly(true);
$cookie->setSecureOnly(true);
$cookie->setSameSiteRestriction('Strict');
// echo $cookie;
$cookie->save();
```

  
[https://github.com/paragonie/PHP-Cookie](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BhcmFnb25pZS9QSFAtQ29va2ll)
