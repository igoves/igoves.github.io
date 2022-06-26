---
title: "IsoCodes - валидатор стандартов ISO, GS1, телефонов и др."
categories: 
  - "php"
---

```
// Trading items with GTIN barcodes in GS1 system? 
$isBarcode = Ean13::validate('4719512002889')

// Calling phone numbers in Palo Alto?
$isPhonable = PhoneNumber::validate('+1-650-798-2800', 'US')

// Buying Apple stocks?
$isISIN = Isin::validate('US0378331005'); // Apple Inc. (AAPL)
```

  
[https://github.com/ronanguilloux/isocodes](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JvbmFuZ3VpbGxvdXgvaXNvY29kZXM%3D)
