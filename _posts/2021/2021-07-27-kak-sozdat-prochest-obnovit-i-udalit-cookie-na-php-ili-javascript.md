---
title: "Как создать, прочесть, обновить и удалить Cookie на PHP или Javascript"
date: ""
categories: 
  - "php"
---

**PHP**  
**Создать**  

```
$cookie_name = 'veselov_php_cookie';$cookie_value = 'test_cookie_set_with_php';setcookie($cookie_name, $cookie_value, time() + (86400 * 30), '/'); // 86400 = 1 day
```

  
**Прочесть**  

```
$cookie_name = 'veselov_php_cookie';if(!isset($_COOKIE[$cookie_name])) {  print 'Cookie with name "' . $cookie_name . '" does not exist...';} else {  print 'Cookie with name "' . $cookie_name . '" value is: ' . $_COOKIE[$cookie_name];}
```

  
**Обновить**  

```
$cookie_name = 'pontikis_net_php_cookie';$cookie_value = 'test_cookie_updated_with_php';setcookie($cookie_name, $cookie_value, time() + (86400 * 30), '/'); // 86400 = 1 day
```

  
**Удалить**  

```
$cookie_name = 'pontikis_net_php_cookie';unset($_COOKIE[$cookie_name]);// empty value and expiration one hour before$res = setcookie($cookie_name, '', time() - 3600);
```

  
Проверить работают ли куки  

```
setcookie('check_cookies_enabled', 'test', time() + 3600, '/');if(count($_COOKIE) > 0) {  print 'Cookies are enabled!';} else {  print 'Cookies are disabled...';}
```

  
  
**javascript**  
**Создать**  

```
var cookie_name = 'veselov_js_cookie';var cookie_value = 'test_cookie_created_with_javascript';create_cookie(cookie_name, cookie_value, 30, "/");
```

  
Функция create\_cookie  

```
function create_cookie(name, value, days2expire, path) {  var date = new Date();  date.setTime(date.getTime() + (days2expire * 24 * 60 * 60 * 1000));  var expires = date.toUTCString();  document.cookie = name + '=' + value + ';' +                   'expires=' + expires + ';' +                   'path=' + path + ';';}
```

  
**Прочесть**  

```
var cookie_name = 'veselvo_js_cookie';var res = retrieve_cookie(cookie_name);if(res) {  alert('Cookie with name "' + cookie_name + '" value is ' + '"' res + '"');} else {  alert('Cookie with name "' + cookie_name + '" does not exist...');}
```

  
функция retrieve\_cookie  

```
function retrieve_cookie(name) {  var cookie_value = "",    current_cookie = "",    name_expr = name + "=",    all_cookies = document.cookie.split(';'),    n = all_cookies.length;   for(var i = 0; i < n; i++) {    current_cookie = all_cookies[i].trim();    if(current_cookie.indexOf(name_expr) == 0) {      cookie_value = current_cookie.substring(name_expr.length, current_cookie.length);      break;    }  }  return cookie_value;}
```

  
**Обновить**  
Просто пересоздаем куку с новым значением  

```
var cookie_name = 'veselov_js_cookie';var cookie_name = 'test_cookie_updated_with_javascript';create_cookie(cookie_name, cookie_value, 60, "/");
```

  
**Удалить**  

```
var cookie_name = 'veselov_js_cookie';delete_cookie(cookie_name);
```

  
функция удалить delete\_cookie  

```
function delete_cookie(name) {  document.cookie = name + "=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";}
```

  
Проверить работают ли куки  

```
if(navigator.cookieEnabled) {  alert('Cookies are enabled!');} else {  alert('Cookies are disabled...');}
```
