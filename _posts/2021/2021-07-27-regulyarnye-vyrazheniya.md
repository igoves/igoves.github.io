---
title: "Регулярные выражения"
categories: 
  - "php"
tags: 
  - "php"
  - "regulyarnye-vyrajeniya"
---

Последнее время очень часто приходиться сталкиваться с регулярными выражениями. И для понимания они очень сложны. Повторить по памяти выражение я не смогу поэтому выложу сюда как записку для себя и как заметку для вас:  
  
**Удалить определенную ссылку**:  

```
$text=preg_replace("~<a href=\\"http://www\\.aaa\\">[^<]+?</a>~",'',$text);
```

  
За это решение спасибо [setty](https://dev.xfor.top/go/aHR0cDovL2ZvcnVtcy5zdW15LnVhL21lbWJlci5waHA%2FdT04Nzc%3D)  
  
**Удалить спецсимволы**:  

```
$text = preg_replace ("~(\\\\\\|\\*|\\?|\\[|\\?|\\]|\\(|\\\\\\$|\\))~", "",$text);
```

  
  
Вывести число подписчиков в **FeedBurner**:  

```
function fb($feed){$s=file_get_contents("http://feedburner.google.com/api/awareness/1.0/GetFeedData?uri={$feed}");preg_match('/circulation="(\\d+)"/', $s, $a);return $a[1];}
```

  
  
Выводим **Alexa Rank**:  

```
function alexa($url) {preg_match('#<div class="data .+?">(.*?)</div>#si', file_get_contents("http://www.alexa.com/siteinfo/{$url}"), $a); return trim(str_replace(",","",strip_tags($a[1])));}
```
