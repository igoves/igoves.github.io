---
title: "Некоторые PHP функций"
date: ""
categories: 
  - "php"
tags: 
  - "php"
  - "php"
  - "funkcii"
---

![Некоторые PHP функций](images/1359745731_1322644115_49.jpg "Некоторые PHP функций")

  
  

```
function seo_url($string, $seperator='-') {    $string = strtolower($string);    $string = preg_replace("/[^a-z0-9_\\s-]/", $seperator, $string);    $string = preg_replace("/[\\s-]+/", " ", $string);    $string = preg_replace("/[\\s_]/", $seperator, $string);    return $string;}
```

Делает из \\"Privet Ivan\\" => \\"privet-ivan\\"  
  

```
function detect_encoding($string) {    static $list = array('utf-8', 'windows-1251');     foreach ($list as $item) {     $sample = iconv($item, $item, $string);     if (md5($sample) == md5($string))       return $item;   }   return null; }
```

Функция детектит кодировку  
  

```
function full_url(){    $s = empty($_SERVER["HTTPS"]) ? '' : ($_SERVER["HTTPS"] == "on") ? "s" : "";    $protocol = substr(strtolower($_SERVER["SERVER_PROTOCOL"]), 0, strpos(strtolower($_SERVER["SERVER_PROTOCOL"]), "/")) . $s;    $port = ($_SERVER["SERVER_PORT"] == "80") ? "" : (":".$_SERVER["SERVER_PORT"]);    return $protocol . "://" . $_SERVER['SERVER_NAME'] . $port . $_SERVER['REQUEST_URI'];}
```

Разберает урл на протокол имя сервера порта и сам запрос  
  

```
<?php$host = $_SERVER['HTTP_HOST'];preg_match("/[^\\.\\/]+\\.[^\\.\\/]+$/", $host, $matches);echo "domain name is: {$matches[0]}\\n";?>
```

Получает имя домена  
  

```
echo json_decode(str_replace('%u', '\\\\u', json_encode($str_from_js)));
```

Преобразовует символы Юникода в виде «%uXXXX» в UTF-8  
  
И на закусь некоторые правила htaccess:  

```
.htaccessRewriteEngine OnRewriteCond %{REQUEST_FILENAME} !-fRewriteCond %{REQUEST_FILENAME} !-dRewriteRule ^(.*)$ $1.php [L,QSA]# http://domain/about -> http://domain/about.php --------------------------------------------------.htaccessRewriteEngine OnRewriteCond %{REQUEST_FILENAME} !-fRewriteCond %{REQUEST_FILENAME} !-dRewriteRule ^(.*)$ index.php?q=$1 [L,QSA]# http://domain/about -> http://domain/index.php?q=about
```
