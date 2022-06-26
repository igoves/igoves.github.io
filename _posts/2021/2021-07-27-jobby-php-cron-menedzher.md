---
title: "jobby - PHP cron менеджер"
date: ""
categories: 
  - "php"
---

Позволяет создавать и добавлять job-ы без правки crontab.  
**Пример использования**  

```
<?php 

require_once __DIR__ . '/vendor/autoload.php';

$jobby = new Jobby\\Jobby();

// Every job has a name
$jobby->add('CommandExample', [
    // Run a shell commands
    'command'  => 'ls',

    // Ordinary crontab schedule format is supported.
    // This schedule runs every hour.
    // You could also insert DateTime string in the format of Y-m-d H:i:s.
    'schedule' => '0 * * * *',

    // Stdout and stderr is sent to the specified file
    'output'   => 'logs/command.log',

    // You can turn off a job by setting 'enabled' to false
    'enabled'  => true,
]);

$jobby->add('ClosureExample', [
    // Invoke PHP closures
    'closure'  => function() {
        echo "I'm a function!\\n";
        return true;
    },

    // This function will run every other hour
    'schedule' => '0 */2 * * *',

    'output'   => 'logs/closure.log',
]);

$jobby->run();
```

[https://github.com/jobbyphp/jobby/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2pvYmJ5cGhwL2pvYmJ5Lw%3D%3D)
