---
title: "veewee/xml - PHP libraries for work XML without worries"
date: "2021-06-08"
categories: 
  - "php"
tags: 
  - "dom"
  - "xml"
---

```
use function VeeWee\Xml\Dom\Builder\element;
use function VeeWee\Xml\Dom\Builder\children;

element('hello',
    children(
        element('world'),
        element('you')
    )
);
```

```
<hello>
    <world />
    <you />
</hello>
```

[https://github.com/veewee/xml](https://github.com/veewee/xml)
