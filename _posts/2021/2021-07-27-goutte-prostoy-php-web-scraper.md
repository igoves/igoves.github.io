---
title: "Goutte - простой PHP Web Scraper"
date: ""
categories: 
  - "php"
---

```
use Goutte\\Client;
$client = new Client();
// переходим на сайт 
$crawler = $client->request('GET', 'http://www.symfony.com/blog/');
// нажать на ссылку
$link = $crawler->selectLink('Security Advisories')->link();
$crawler = $client->click($link);
// получить данные
$crawler->filter('h2 > a')->each(function ($node) {
    print $node->text()."\\n";
});
```

  
[https://github.com/FriendsOfPHP/Goutte](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0ZyaWVuZHNPZlBIUC9Hb3V0dGU%3D)
