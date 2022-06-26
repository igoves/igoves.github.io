---
title: "php-ssh - php api для работы с ssh"
categories: 
  - "php"
---

Пример

```
<?php

// simple configuration to connect "my-host"
$configuration = new Ssh\\SshConfigFileConfiguration('/Users/username/.ssh/config', 'my-host');
$authentication = $configuration->getAuthentication('optional_passphrase', 'optional_username');

echo $exec->run('ls -lah');
```

  
[https://github.com/Herzult/php-ssh](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0hlcnp1bHQvcGhwLXNzaA%3D%3D)
