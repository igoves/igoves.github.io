---
title: "xxczaki/cashify - js скрипт конвертации валюты, наследник money.js"
categories: 
  - "js"
tags: 
  - "convert"
  - "currency"
  - "valyuta"
  - "konvertaciya"
---

```
const {Cashify} = require('cashify');

const rates = {
	GBP: 0.92,
	EUR: 1.00,
	USD: 1.12
};

const cashify = new Cashify({base: 'EUR', rates});

const result = cashify.convert(10, {from: 'EUR', to: 'GBP'});

console.log(result); //=> 9.2
```

  
[https://github.com/xxczaki/cashify](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3h4Y3pha2kvY2FzaGlmeQ%3D%3D)
