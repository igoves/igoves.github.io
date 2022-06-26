---
title: "Guzzle - PHP HTTP client"
date: ""
categories: 
  - "php"
---

```
$client = new GuzzleHttp\\Client();
$res = $client->get('https://api.github.com/user', ['auth' =>  ['user', 'pass']]);
echo $res->getStatusCode();
// "200"
echo $res->getHeader('content-type');
// 'application/json; charset=utf8'
echo $res->getBody();
// {"type":"User"...'

// Send an asynchronous request.
$request = new \\GuzzleHttp\\Psr7\\Request('GET', 'http://httpbin.org');
$promise = $client->sendAsync($request)->then(function ($response) {
    echo 'I completed! ' . $response->getBody();
});
$promise->wait();
```

  
[http://guzzle.readthedocs.org/en/latest/](https://dev.xfor.top/go/aHR0cDovL2d1enpsZS5yZWFkdGhlZG9jcy5vcmcvZW4vbGF0ZXN0Lw%3D%3D)
