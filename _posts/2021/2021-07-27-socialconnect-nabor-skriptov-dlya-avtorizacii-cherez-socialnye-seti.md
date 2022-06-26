---
title: "SocialConnect - набор скриптов для авторизации через социальные сети"
categories: 
  - "php"
---

Поддерживает instagram, vk, github, Facebook, Twitter  

```
$service = new \\SocialConnect\\Auth\\Service(array(
        'redirectUri' => 'http://sconnect.local/auth/cb',
        'provider' => array(
            'Facebook' => array(
                'applicationId' => '',
                'applicationSecret' => '',
                'scope' => array('email')
            ),
        )
));
$service->setHttpClient(new \\SocialConnect\\Common\\Http\\Client\\Curl());
```

  
[https://github.com/socialconnect](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NvY2lhbGNvbm5lY3Q%3D)
