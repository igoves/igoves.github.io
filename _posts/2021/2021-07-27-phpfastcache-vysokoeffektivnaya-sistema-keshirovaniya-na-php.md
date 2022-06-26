---
title: "phpfastcache - высокоэффективная система кэширования на php"
date: ""
categories: 
  - "js"
---

Пример

```
use phpFastCache\\Helper\\Psr16Adapter;

$Psr16Adapter = new Psr16Adapter($defaultDriver);

if(!$Psr16Adapter->has('test-key')){
    // Setter action
    $data = 'lorem ipsum';
    $Psr16Adapter->set('test-key', 'lorem ipsum', 300);// 5 minutes
}else{
    // Getter action
    $data = $Psr16Adapter->get('test-key');
}

```

  
[https://github.com/phpsocialnetwork/phpfastcache](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BocHNvY2lhbG5ldHdvcmsvcGhwZmFzdGNhY2hl)
