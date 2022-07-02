---
title: "moneyphp/money - PHP implementation of Fowler's Money pattern"
date: "2021-06-07"
categories: 
  - "php"
tags: 
  - "money"
---

```
<?php

use Money\Money;

$fiveEur = Money::EUR(500);
$tenEur = $fiveEur->add($fiveEur);

list($part1, $part2, $part3) = $tenEur->allocate([1, 1, 1]);
assert($part1->equals(Money::EUR(334)));
assert($part2->equals(Money::EUR(333)));
assert($part3->equals(Money::EUR(333)));
```

[https://github.com/moneyphp/money](https://github.com/moneyphp/money)
