---
title: "Goodby CSV - высокоэффективная гибкая и расширяемая библиотека CSV import/export на PHP"
date: ""
categories: 
  - "php"
---

```
use Goodby\\CSV\\Import\\Standard\\Lexer;
use Goodby\\CSV\\Import\\Standard\\Interpreter;
use Goodby\\CSV\\Import\\Standard\\LexerConfig;

$lexer = new Lexer(new LexerConfig());
$interpreter = new Interpreter();
$interpreter->addObserver(function(array $row) {
    // do something here.
    // for example, insert $row to database.
});
$lexer->parse('data.csv', $interpreter);
```

  
Скрипт не нагружает память, обрабатывается строчка, за строчкой, не перегружая память. Поддерживает мультибайтовость, например SJIS-win, EUC-JP and UTF-8. Скрипт описан юнит тестами и полностью готов для использования в проектах.  
  
**Требования**  
\- PHP 5.3.2 or later  
\- mbstring  
  
[https://github.com/goodby/csv](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2dvb2RieS9jc3Y%3D "https://github.com/goodby/csv")
