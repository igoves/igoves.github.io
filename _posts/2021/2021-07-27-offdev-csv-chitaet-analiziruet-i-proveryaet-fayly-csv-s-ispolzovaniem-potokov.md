---
title: "offdev/csv -читает, анализирует и проверяет файлы CSV с использованием потоков"
date: ""
categories: 
  - "php"
---

```
use GuzzleHttp\\Client;
use Offdev\\Csv\\Stream;
use Offdev\\Csv\\Parser;

$client = new Client();
$response = $client->get('http://httpbin.org/get');
$stream = Stream::factory($response->getBody());

$parser = new Parser($stream);
do {
    $record = $parser->readLine();
    echo $record ? $record->get('header-column2').PHP_EOL : '';
} while (!$parser->eof());
```

[https://github.com/offdev/csv](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL29mZmRldi9jc3Y%3D)
