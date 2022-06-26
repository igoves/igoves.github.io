---
title: "Unirest for PHP - легковесная библиотека для работы с HTTP"
date: ""
categories: 
  - "php"
---

**Что может**  
\- методы: GET , HEAD , POST , PUT , DELETE , CONNECT , OPTIONS , TRACE , PATCH  
\- поддержка gzip  
\- поддержка параметров формы, загрузку файлов  
\- настраиваемое время таймаута  
\- настраиваемые заголовки по умолчанию для каждого запроса  
\- автоматическая JSON парс в родной объект для ответов JSON  
  
**Требования** : cURL и PHP 5.4+  
  
Пример создания запроса

```
$headers = array("Accept" => "application/json");
$body = array("foo" => "hellow", "bar" => "world");

$response = Unirest\\Request::post("http://mockbin.com/request", $headers, $body);

$response->code;        // HTTP Status code
$response->headers;     // Headers
$response->body;        // Parsed body
$response->raw_body;    // Unparsed body
```

  
Пример загрузки файла

```
$headers = array("Accept" => "application/json");
$body = array("file" => Unirest\\File::add("/tmp/file.txt"));

$response = Unirest\\Request::post("http://mockbin.com/request", $headers, $body);
```

  
[https://github.com/Mashape/unirest-php](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL01hc2hhcGUvdW5pcmVzdC1waHA%3D)
