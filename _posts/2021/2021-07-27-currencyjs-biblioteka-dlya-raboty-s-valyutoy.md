---
title: "currency.js - библиотека для работы с валютой"
categories: 
  - "js"
---

```
var euro = value => currency(value, { separator: ".", decimal: "," });
euro("2.573.693,75").add("100.275,50").format();  // "2.673.969,25"
euro("1.237,72").subtract(300).format();          // "937,72"

const USD = value => currency(value, { symbol: "$", precision: 2 });
const JPY = value => currency(value, { symbol: "?", precision: 0 });
const GAS = value => currency(value, { precision: 3 });

USD(1234.56).format(true); // "$1,234.56"
JPY(1234.56).format(true); // "?1,235"
GAS(1234.56).format(true); // "$1,234.560"
```

  
[https://github.com/scurker/currency.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NjdXJrZXIvY3VycmVuY3kuanM%3D)
