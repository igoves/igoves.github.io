---
title: "spiral / storage - Object Storage API: Amazon, FTP, SFTP, Filesystem, GridFS"
date: "2021-06-22"
categories: 
  - "php"
tags: 
  - "api"
  - "storage"
---

```
$storage = new \Spiral\Storage\Storage();

$storage->add('example', \Spiral\Storage\Bucket::fromAdapter(
    new \League\Flysystem\Local\LocalFilesystemAdapter(__DIR__ . '/path/to/directory')
));

$file = $storage->bucket('example')
    ->write('file.txt', 'content');
```

[https://github.com/spiral/storage](https://github.com/spiral/storage)
