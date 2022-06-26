---
title: "slugify - js скрипт без зависимостей создания slug из любой строки"
categories: 
  - "js"
---

```
const slugify = require('@sindresorhus/slugify');

slugify('I ? Dogs');
//=> 'i-love-dogs'

slugify('  D?j? Vu!  ');
//=> 'deja-vu'

slugify('fooBar 123 $#%');
//=> 'foo-bar-123'

slugify('BAR and baz', {separator: '_'});
//=> 'bar_and_baz'
```

  
[https://github.com/sindresorhus/slugify](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NpbmRyZXNvcmh1cy9zbHVnaWZ5)
