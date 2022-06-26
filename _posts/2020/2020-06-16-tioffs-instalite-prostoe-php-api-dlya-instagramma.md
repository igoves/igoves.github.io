---
title: "tioffs / InstaLite - простое php api для  инстаграмма"
date: "2020-06-16"
categories: 
  - "php"
tags: 
  - "api"
  - "instagram-2"
---

```
require_once __DIR__ . '/vendor/autoload.php';
use InstaLite\InstaLite;
$instagram = new InstaLite("username", "password", "proxy");
/** search user (return array standart instagram) **/
$user = $instagram->searchUser('alex')->id();
/** search user (return array user id [1,2,3]) **/
$user = $instagram->searchUser('alex')->all();
/** send photo **/
$instagram->uploadPhoto(__DIR__ . '/img.jpg', 'text #hashtag');
/** send message direct **/
$instagram->sendMessage('text message', [1233, 1233, 1223]);
```

[https://github.com/tioffs/InstaLite](https://github.com/tioffs/InstaLite)
