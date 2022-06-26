---
title: "laracart - пакет для создания товарной корзины в laravel"
categories: 
  - "php"
---

```
LaraCart::add(
    $itemID,
    $name = null,
    $qty = 1,
    $price = '0.00',
    $options = [],
    $taxable = true,
    $lineItem = false
)

// Adding an item to the cart
LaraCart::add(2, 'Shirt', 200, 15.99, [
    'size' => 'XL'
]);

// If you need line items rather than just updating the qty you can do
LaraCart::addLine(2, 'Shirt', 200, 15.99, [
    'size' => 'XL'
]);

// Also you can have your item not taxed
$item = LaraCart::addLine(2, 'Shirt', 200, 15.99, [
    'size' => 'XL'
    ],
    $taxable = false
);
```

  
[https://github.com/lukepolo/laracart](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2x1a2Vwb2xvL2xhcmFjYXJ0)
