---
title: "Правильное ЧПУ для сайта"
categories: 
  - "php"
---

![Правильное ЧПУ для сайта](images/1309168941_6.jpg "Правильное ЧПУ для сайта")

  
Функции взяты с какой-то CMS.  

```
<?php    function getUri() {        $requestURI = explode('/', $_SERVER['REQUEST_URI']);        $scriptName = explode('/',$_SERVER['SCRIPT_NAME']);        for($i= 0;$i < sizeof($scriptName);$i++) {            if ($requestURI[$i] == $scriptName[$i]) {                unset($requestURI[$i]);            }        }                $uri = array_values($requestURI);        if(isset($uri[0])) { $pos = strrpos($uri[0], "?"); if ($pos === false) { $uri[0] = sanitizeURL($uri[0]); } else { $uri[0] = sanitizeURL(substr($uri[0], 0, $pos)); } }        if(isset($uri[1])) { $pos = strrpos($uri[1], "?"); if ($pos === false) { $uri[1] = sanitizeURL($uri[1]); } else { $uri[1] = sanitizeURL(substr($uri[1], 0, $pos)); } }        if(isset($uri[2])) { $pos = strrpos($uri[2], "?"); if ($pos === false) { $uri[2] = sanitizeURL($uri[2]); } else { $uri[2] = sanitizeURL(substr($uri[2], 0, $pos)); } }        if(isset($uri[3])) { $pos = strrpos($uri[3], "?"); if ($pos === false) { $uri[3] = sanitizeURL($uri[3]); } else { $uri[3] = sanitizeURL(substr($uri[3], 0, $pos)); } }        if(isset($uri[4])) { $pos = strrpos($uri[4], "?"); if ($pos === false) { $uri[4] = sanitizeURL($uri[4]); } else { $uri[4] = sanitizeURL(substr($uri[4], 0, $pos)); } }        if(isset($uri[5])) { $pos = strrpos($uri[5], "?"); if ($pos === false) { $uri[5] = sanitizeURL($uri[5]); } else { $uri[5] = sanitizeURL(substr($uri[5], 0, $pos)); } }        return $uri;    }        function sanitizeURL($url) {         $url = trim($url);         $url = rawurldecode($url);         $url = str_replace(array('--','&quot;','!','@','#','$','%','^','*','(',')','+','{','}','|',':','"','<','>',                                  '[',']','\\\\',';',"'",',','/','*','+','~','`','laquo','raquo',']>','&#8216;','&#8217;','&#8220;' ,'&#8221;' ,'&#8211;' ,'&#8212;'),                            array('-','-','','','','','','','','','','','','','','','','','','','','','','','','','','','',''),                            $url);         $url = str_replace('--','-',$url);         $url = rtrim($url, "-");         return $url;     }            print_r(getUri());
```

  
**.htaccess**  

```
<IfModule mod_rewrite.c>    RewriteEngine on    RewriteBase /    RewriteCond %{REQUEST_FILENAME} !-f    RewriteCond %{REQUEST_FILENAME} !-d    RewriteRule ^(.*)$ index.php [QSA,L]</IfModule>
```

  
Скрипт разбивает ГЕТ запрос и создает массив. В данной реализации можно вводить до 6 параметров http://site/param1/param2/../param6.
