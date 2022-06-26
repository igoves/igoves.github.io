---
title: "Защищаемся от xcrf на php"
date: ""
categories: 
  - "php"
tags: 
  - "php"
  - "token"
  - "xcrf"
---

```
$secretkey = date("m.d.y");//убераем авторизированный токенsetcookie ("token", '', time() - 12200);//ставим токен авторизированныйsetcookie ("token", sha1($username.$secretkey), time() + 12200);if (!isset($_COOKIE['token'])) {    //нет токена = умри!    die();} else {    if ( sha1($_COOKIE['user'].$secretkey) !== $_COOKIE['token'] ) {        setcookie ("user", "", time() - 3600);        setcookie ("token", "", time() - 3600);        show_login("Please Login");        die();    }}
```
