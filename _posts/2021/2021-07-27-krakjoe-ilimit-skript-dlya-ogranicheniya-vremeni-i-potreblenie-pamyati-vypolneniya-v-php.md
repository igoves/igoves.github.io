---
title: "krakjoe/ilimit - скрипт для ограничения времени и потребление памяти выполнения в PHP"
date: ""
categories: 
  - "php"
---

Требования  
PHP 7.1+  
**NTS  
pthread.h**  

```
namespace ilimit {
    /**
     * Call a callback while imposing limits on the time and memory that
     * the call may consume.
     *
     * @param callable $callable      The invocation to make.
     * @param array    $arguments     The list of arguments.
     * @param int      $timeout       The maximum execution time, in microseconds.
     * @param int      $maxMemory     The maximum amount of memory, in bytes.
     *                                If set to zero, no limit is imposed.
     * @param int      $checkInterval The interval between memory checks,
     *                                in microseconds. If set to zero or less,
     *                                a default interval of 100 microseconds is used.
     *
     * @return mixed Returns the return value of the callback.
     *
     * @throws Error\\Runtime If timeout is not positive.
     * @throws Error\\Runtime If maxMemory is negative.
     * @throws Error\\System  If the system lacks necessary resources to make the call.
     * @throws Error\\Timeout If the invocation exceeds the allowed time.
     * @throws Error\\Memory  If the invocation exceeds the allowed memory.
     */
    function call(callable $callable, array $arguments, int $timeout, int $maxMemory = 0, int $checkInterval = 0);
}
```

  
[https://github.com/krakjoe/ilimit](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2tyYWtqb2UvaWxpbWl0)
