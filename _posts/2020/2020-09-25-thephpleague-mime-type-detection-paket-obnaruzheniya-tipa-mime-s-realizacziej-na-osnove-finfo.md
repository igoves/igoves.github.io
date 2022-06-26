---
title: "thephpleague / mime-type-detection - пакет обнаружения типа MIME с реализацией на основе finfo"
date: "2020-09-25"
categories: 
  - "php"
tags: 
  - "detect"
  - "mime"
---

```
$detector = new League\MimeTypeDetection\FinfoMimeTypeDetector();

// Detect by contents, fall back to detection by extension.
$mimeType = $detector->detectMimeType('some/path.php', 'string contents');

// Detect by contents only, no extension fallback.
$mimeType = $detector->detectMimeTypeFromBuffer('string contents');

// Detect by actual file, no extension fallback.
$mimeType = $detector->detectMimeTypeFromFile('existing/path.php');

// Only detect by extension
$mimeType = $detector->detectMimeTypeFromPath('any/path.php');
```

[https://github.com/thephpleague/mime-type-detection](https://github.com/thephpleague/mime-type-detection)
