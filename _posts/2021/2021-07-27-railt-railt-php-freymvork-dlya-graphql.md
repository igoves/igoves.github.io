---
title: "railt/railt - php фреймворк для GraphQL"
date: ""
categories: 
  - "php"
---

**schema.graphqls**

```
schema {
    query: Example
}

type Example {
    say(message: String = "Hello"): String! 
        @route(action: "ExampleController@say")
}
```

  
**ExampleController.php**

```
class ExampleController
{
    public function say(string $message): string
    {
        return $message;
    }
}
```

  
[https://github.com/railt/railt](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JhaWx0L3JhaWx0)
