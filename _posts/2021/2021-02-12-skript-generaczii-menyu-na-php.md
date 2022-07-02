---
title: "Скрипт генерации меню на PHP"
date: "2021-02-12"
categories: 
  - "php"
---

```
require 'vendor/autoload.php';

use Knp\Menu\MenuFactory;
use Knp\Menu\Renderer\ListRenderer;

$factory = new MenuFactory();
$menu = $factory->createItem('My menu');
$menu->addChild('Home', ['uri' => '/']);
$menu->addChild('Comments', ['uri' => '#comments']);
$menu->addChild('Symfony', ['uri' => 'http://symfony.com/']);
$menu->addChild('Happy Awesome Developers');

$renderer = new ListRenderer(new \Knp\Menu\Matcher\Matcher());
echo $renderer->render($menu);
```

[https://github.com/KnpLabs/KnpMenu](https://github.com/KnpLabs/KnpMenu)

```
$pages = [
    '/' => 'Home',
    '/about' => 'About',
    '/contact' => 'Contact',
];

Menu::build($pages, function ($menu, $label, $url) {
    $menu->add($url, $label);
})->render();
```

[https://github.com/spatie/menu](https://github.com/spatie/menu)
