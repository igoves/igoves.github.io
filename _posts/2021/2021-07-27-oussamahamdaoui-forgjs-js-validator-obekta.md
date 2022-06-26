---
title: "oussamahamdaoui/forgJs - js валидатор объекта"
categories: 
  - "js"
---

```
 const passwordRule = new Rule({
    type: 'password',
    minLength: 8,
    uppercase: 1,
    numbers: 1,
    matchesOneOf: ['@', '_', '-', '.', '!'],
  }, null);

  passwordRule.test('@_-bddcd6A'); // returns true
```

  
[https://github.com/oussamahamdaoui/forgJs](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL291c3NhbWFoYW1kYW91aS9mb3JnSnM%3D)
