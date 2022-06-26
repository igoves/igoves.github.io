---
title: "Arrayzy  - php обертка для работы с массивами через ООП"
categories: 
  - "php"
---

Пример chunk

```
$a = A::create(['a', 'b', 'c']);
$a->chunk(2);
$a->toArray(); // [0 => [0 => 'a', 1 => 'b'], 1 => [0 => 'c']]
```

  
Пример очистки

```
$a = A::create(['a', 'b', 'c']);
$a->clear();
$a->toArray(); // []
```

  
Поддерживаемые методы на текущий момент: chunk, clear, combineTo, combineWith, contains, containsKey, count, create, createClone, createFromJson, createFromObject, createFromString, createWithRange, current, customSort, customSortKeys, debug, diffWith, each, exists, export, filter, find, first, flip, getIterator, getKeys, getRandom, getRandomKey, getRandomKeys, getRandomValues, getValues, indexOf, isAssoc, isEmpty, isNumeric, key, last, map, mergeTo, mergeWith, next, offsetExists, offsetGet, offsetSet, offsetUnset, pad, pop, previous, push, reduce, reindex, replaceIn, replaceWith, reverse, shift, shuffle, slice, sort, sortKeys, toArray, toJson, toReadableString, toString, unique, unshift, walk
