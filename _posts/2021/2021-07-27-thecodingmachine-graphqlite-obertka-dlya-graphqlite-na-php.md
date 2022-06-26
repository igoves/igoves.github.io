---
title: "thecodingmachine/graphqlite - обертка для graphqlite на php"
date: ""
categories: 
  - "php"
---

```
/**
 * @Type()
 */
class Product
{
    /**
     * @Field()
     */
    public function getName(): string
    {
        return $this->name;
    }
    // ...
}
```

  

```
{
  product(id: 42) {
    name
  }
}
```

  
[https://github.com/thecodingmachine/graphqlite](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RoZWNvZGluZ21hY2hpbmUvZ3JhcGhxbGl0ZQ%3D%3D)
