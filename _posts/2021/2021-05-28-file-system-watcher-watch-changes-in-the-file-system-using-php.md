---
title: "file-system-watcher -watch changes in the file system using PHP"
date: "2021-05-28"
categories: 
  - "php"
tags: 
  - "file"
  - "watcher"
---

This package allows you to react to all kinds of changes in the file system.

Here's how you can run code when a new file gets added.

```
use Spatie\Watcher\Watch;

Watch::path($directory)
    ->onFileCreated(function (string $newFilePath) {
        // do something...
    })
    ->start();
```

[https://github.com/spatie/file-system-watcher](https://github.com/spatie/file-system-watcher)
