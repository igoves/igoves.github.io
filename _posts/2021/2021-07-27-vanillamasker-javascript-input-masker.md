---
title: "VanillaMasker - javascript input masker"
date: ""
categories: 
  - "js"
---

![VanillaMasker - javascript input masker](images/1409054587_untitled-1.png "VanillaMasker - javascript input masker")

  

```
// Input number example: 1234567890var masker = new VanillaMasker({  // Decimal precision -> "90"  precision: 2,   // Decimal separator -> ",90"  separator: ',',   // Number delimiter -> "12.345.678"  delimiter: '.',   // Money unit -> "R$ 12.345.678,90"  unit: 'R$',   // Money unit -> "12.345.678,90 R$"  suffixUnit: 'R$',   // Force type only number instead decimal,  // masking decimals with ",00"  // Zero cents -> "R$ 1.234.567.890,00"  zeroCents: true,  // Enable console.log warnings  suppressLogging: true});
```

  
[http://bankfacil.github.io/vanilla-masker/](https://dev.xfor.top/go/aHR0cDovL2JhbmtmYWNpbC5naXRodWIuaW8vdmFuaWxsYS1tYXNrZXIv)
