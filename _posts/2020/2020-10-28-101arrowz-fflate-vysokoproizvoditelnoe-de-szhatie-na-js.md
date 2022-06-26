---
title: "101arrowz/fflate - высокопроизводительное (де) сжатие на js"
date: "2020-10-28"
categories: 
  - "js"
tags: 
  - "compress"
---

Поддерживает DEFLATE, GZIP, and Zlib data

```
const compressed = new Uint8Array(
  await fetch('/GZIPorZLIBorDEFLATE').then(res => res.arrayBuffer())
);
// Above example with Node.js Buffers:
// Buffer.from('H4sIAAAAAAAAE8tIzcnJBwCGphA2BQAAAA==', 'base64');

const decompressed = fflate.decompressSync(compressed);
```

[https://github.com/101arrowz/fflate](https://github.com/101arrowz/fflate)
