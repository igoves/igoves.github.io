---
title: "laravel-mojito - облегченный пакет для тестирования представлений Laravel в изоляции"
date: "2020-07-01"
categories: 
  - "php"
tags: 
  - "laravel"
  - "testing"
---

![](images/example.png)

```
class WelcomeTest extends TestCase
{
    // First, add the `InteractsWithViews` trait to your test case class.
    use InteractsWithViews; 

    public function testDisplaysLaravel()
    {
        // Then, get started with Mojito using the `assertView` method.
        $this->assertView('welcome')->contains('Laravel');
    }
}
```

[https://github.com/nunomaduro/laravel-mojito](https://github.com/nunomaduro/laravel-mojito)
