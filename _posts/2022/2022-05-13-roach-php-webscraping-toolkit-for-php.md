---
title: "Roach PHP - webscraping toolkit for PHP"
date: "2022-05-13"
categories: 
  - "php"
tags: 
  - "scrapper"
  - "toolkit"
---

```
<?php

use RoachPHPHttpResponse;
use RoachPHPSpiderBasicSpider;

class RoachDocsSpider extends BasicSpider
{
    /**
     * @var string[]
     */
    public array $startUrls = [
        'https://roach-php.dev/docs/spiders'
    ];

    public function parse(Response $response): Generator
    {
        $title = $response->filter('h1')->text();

        $subtitle = $response
            ->filter('main > div:nth-child(2) p:first-of-type')
            ->text();

        yield $this->item([
            'title' => $title,
            'subtitle' => $subtitle,
        ]);
    }
}
```

[https://roach-php.dev/docs/introduction](https://roach-php.dev/docs/introduction)
