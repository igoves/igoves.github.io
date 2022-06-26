---
title: "assert - php скрипт для создания ассертов"
date: ""
categories: 
  - "php"
---

```
use Webmozart\\Assert\\Assert;

class Employee
{
    public function __construct($id)
    {
        Assert::integer($id, 'The employee ID must be an integer. Got: %s');
        Assert::greaterThan($id, 0, 'The employee ID must be a positive integer. Got: %s');
    }
}
new Employee('foobar');
// => InvalidArgumentException: 
//    The employee ID must be an integer. Got: string

new Employee(-10);
// => InvalidArgumentException: 
//    The employee ID must be a positive integer. Got: -10
```

  
[https://github.com/webmozart/assert](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dlYm1vemFydC9hc3NlcnQ%3D)
