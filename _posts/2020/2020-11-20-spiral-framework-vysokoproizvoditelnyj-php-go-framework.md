---
title: "Spiral Framework - высокопроизводительный PHP / Go Framework"
date: "2020-11-20"
categories: 
  - "go"
---

```
namespace App\Bootloader;

use Spiral\Boot\Bootloader\Bootloader;
use Spiral\Router\Route;
use Spiral\Router\RouterInterface;

class RoutesBootloader extends Bootloader
{
    public function boot(RouterInterface $router)
    {
        $router->setRoute(
            'home',                                   // route name 
            new Route(
                '/',                                  // pattern
                function () { return 'hello world'; } // handler
            )
        );
    }
}
```

[https://spiral.dev/](https://spiral.dev/)
