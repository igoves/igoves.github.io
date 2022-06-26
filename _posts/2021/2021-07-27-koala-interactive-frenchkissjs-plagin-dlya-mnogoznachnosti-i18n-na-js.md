---
title: "koala-interactive/frenchkiss.js - плагин для многоязычности i18n на js"
date: ""
categories: 
  - "js"
---

```
import frenchkiss from 'frenchkiss';

// Define the locale language
frenchkiss.locale('en');

// Add translations in each languages
frenchkiss.set('en', {
  hello: 'Hello {name} !',
  goodbye: 'Bye !',
  // and other sentences...
});

frenchkiss.t('hello', {
  name: 'John',
}); // => 'Hello John !'
```

  
Работает как на фронтенде так и на бекенде (node.js)  
[https://github.com/koala-interactive/frenchkiss.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2tvYWxhLWludGVyYWN0aXZlL2ZyZW5jaGtpc3MuanM%3D)
