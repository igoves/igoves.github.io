---
title: "Функция определения смартфона PHP"
categories: 
  - "php"
tags: 
  - "php"
  - "smartphone"
---

```
function check_smartphone() {    if ( $_SESSION['mobile_enable'] ) return true;    $phone_array = array('iphone', 'android', 'pocket', 'palm', 'windows ce', 'windowsce', 'cellphone', 'opera mobi', 'operamobi', 'ipod', 'small', 'sharp', 'sonyericsson', 'symbian', 'symbos', 'opera mini', 'nokia', 'htc_', 'samsung', 'motorola', 'smartphone', 'blackberry', 'playstation portable', 'tablet browser', 'android');    $agent = strtolower( $_SERVER['HTTP_USER_AGENT'] );    foreach ($phone_array as $value) {        if ( strpos($agent, $value) !== false ) return true;    }    return false;}
```
