---
title: "jasny/switch-route - php скрипт генерации быстрых роутов"
categories: 
  - "php"
---

```
function getRoutes(): array
{
    return [
        'GET      /'                  => ['controller' => 'info'],

        'GET      /users'             => ['controller' => 'user', 'action' => 'list'],
        'POST     /users'             => ['controller' => 'user', 'action' => 'add'],
        'GET      /users/{id}'        => ['controller' => 'user', 'action' => 'get'],
        'POST|PUT /users/{id}'        => ['controller' => 'user', 'action' => 'update'],
        'DELETE   /users/{id}'        => ['controller' => 'user', 'action' => 'delete'],

        'GET      /users/{id}/photos' => ['action' => 'list-photos'],
        'POST     /users/{id}/photos' => ['action' => 'add-photos'],

        'POST     /export'            => ['include' => 'scripts/export.php'],
    ];
}
```

```
use Jasny\\SwitchRoute\\Generator;

// Always generate in development env, but not in production.
$overwrite = (getenv('APPLICATION_ENV') ?: 'dev') === 'dev';

$generator = new Generator();
$generator->generate('route', 'generated/route.php', 'getRoutes', $overwrite);
```

  
[https://github.com/jasny/switch-route](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2phc255L3N3aXRjaC1yb3V0ZQ%3D%3D)
