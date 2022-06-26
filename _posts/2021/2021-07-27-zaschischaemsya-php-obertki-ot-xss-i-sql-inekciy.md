---
title: "Защищаемся, PHP-обертки от XSS и SQL-иньекций"
categories: 
  - "php"
tags: 
  - "sql-inj"
  - "xss"
---

```
// Функции применяются ко входным параметрам // Защита от SQL-inj function NUMERIC_GET($name) {   $val = isset($_GET[$name]) ? (int)$_GET[$name] : 0;   $val = mysql_real_escape_string($val);   return $val; } function STRING_GET($name) {   $val = isset($_GET[$name]) ? mysql_real_escape_string($_GET[$name]) : '';   return $val; } function NUMERIC_POST($name) {   $val = isset($_POST[$name]) ? (int)$_POST[$name] : 0;   $val = mysql_real_escape_string($val);   return $val; } function STRING_POST($name) {   $val = isset($_POST[$name]) ? mysql_real_escape_string($_POST[$name]) : '';   return $val; } function ARRAY_STRING_POST($name) {   $val = '';   if(isset($_POST[$name]))   {     $request = $_POST[$name];     if(is_array($request))     {       foreach($request as $key => $value)       {          $request[$key] = mysql_real_escape_string($value);       }       $val = $request;     }   }   return $val; } function ARRAY_STRING_GET($name) {   $val = '';   if(isset($_GET[$name]))   {     $request = $_GET[$name];     if(is_array($request))     {       foreach($request as $key => $value)       {          $request[$key] = mysql_real_escape_string($value);       }       $val = $request;     }   }   return $val; } function ARRAY_NUMERIC_POST($name) {   $val = 0;   if(isset($_POST[$name]))   {     $request = $_POST[$name];     if(is_array($request))     {       foreach($request as $key => $value)       {          $request[$key] = (int)$value;          $request[$key] = mysql_real_escape_string($request[$key]);       }       $val = $request;     }   }   return $val; } function ARRAY_NUMERIC_GET($name) {   $val = 0;   if(isset($_GET[$name]))   {     $request = $_GET[$name];     if(is_array($request))     {       foreach($request as $key => $value)       {          $request[$key] = (int)$value;          $request[$key] = mysql_real_escape_string($request[$key]);       }       $val = $request;     }   }   return $val; } // Функция для всех выходных параметров // Защита от XSS function r_echos($text) {    return htmlspecialchars($text); } ?>
```
