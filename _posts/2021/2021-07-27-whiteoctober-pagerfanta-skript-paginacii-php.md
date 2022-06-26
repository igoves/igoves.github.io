---
title: "whiteoctober/Pagerfanta - скрипт пагинации php"
categories: 
  - "php"
---

Пример

```
<?php

use Pagerfanta\\Adapter\\ArrayAdapter;
use Pagerfanta\\Pagerfanta;

$adapter = new ArrayAdapter($array);
$pagerfanta = new Pagerfanta($adapter);

$pagerfanta->setMaxPerPage($maxPerPage); // 10 by default
$maxPerPage = $pagerfanta->getMaxPerPage();

$pagerfanta->setCurrentPage($currentPage); // 1 by default
$currentPage = $pagerfanta->getCurrentPage();

$nbResults = $pagerfanta->getNbResults();
$currentPageResults = $pagerfanta->getCurrentPageResults();

$pagerfanta->getNbPages();

$pagerfanta->haveToPaginate(); // whether the number of results if higher than the max per page

$pagerfanta->hasPreviousPage();
$pagerfanta->getPreviousPage();
$pagerfanta->hasNextPage();
$pagerfanta->getNextPage();
```

  
[https://github.com/whiteoctober/Pagerfanta](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3doaXRlb2N0b2Jlci9QYWdlcmZhbnRh)
