---
title: "amphp/mysql - асинхронный mysql клиент на php"
categories: 
  - "php"
---

```
\\Amp\\run(function() {
    $connection = new Amp\\Mysql\\Connection("host=".DB_HOST.";user=".DB_USER.";pass=".DB_PASS);
    yield $connection->connect();
    $resultSet = yield $connection->query("SELECT 10");
    $rows = yield $resultSet->fetchAll();
    var_dump($rows); // Array(1) { 0 => Array(1) { 0 => 10 } }
});
```

  
[https://github.com/amphp/mysql](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FtcGhwL215c3Fs)
