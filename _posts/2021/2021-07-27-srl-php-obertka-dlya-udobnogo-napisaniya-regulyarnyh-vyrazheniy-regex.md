---
title: "SRL-PHP - обертка для удобного написания регулярных выражений Regex"
categories: 
  - "php"
---

Такая регулярка:  

```
/^([A-Z0-9._%+-])+@[A-Z0-9.-]+\\.[A-Z]{2,}$/i
```

  
с помощью этой библиотеки это будет выглядеть так:  

```
$query = SRL::startsWith()
    ->anyOf(function (Builder $query) {
        $query->digit()
            ->letter()
            ->oneOf('._%+-');
    })->onceOrMore()
    ->literally('@')
    ->anyOf(function (Builder $query) {
        $query->digit()
            ->letter()
            ->oneOf('.-');
    })->onceOrMore()
    ->literally('.')
    ->letter()->atLeast(2)
    ->mustEnd()->caseInsensitive();
```

  
[https://github.com/SimpleRegex/SRL-PHP](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1NpbXBsZVJlZ2V4L1NSTC1QSFA%3D)
