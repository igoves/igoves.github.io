---
title: "regex - php обертка для preg_ функций"
categories: 
  - "php"
---

```
use Spatie\\Regex\\Regex;

// Using `match`
Regex::match('/a/', 'abc'); // `MatchResult` object
Regex::match('/a/', 'abc')->hasMatch(); // true
Regex::match('/a/', 'abc')->result(); // 'a'

// Capturing groups with `match`
Regex::match('/a(b)/', 'abc')->result(); // 'ab'
Regex::match('/a(b)/', 'abc')->group(1); // 'a'

// Using `matchAll`
Regex::matchAll('/a/', 'abcabc')->hasMatch(); // true
Regex::matchAll('/a/', 'abcabc')->results(); // Array of `MatchResult` objects

// Using replace
Regex::replace('/a/', 'b', 'abc')->result(); // 'bbc';
Regex::replace('/a/', function (MatchResult $result) {
    return $result->result() . 'Hello!';
}, 'abc')->result(); // 'aHello!bc';
```

  
[https://github.com/spatie/regex](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NwYXRpZS9yZWdleA%3D%3D)
