---
title: "How to optimize ORDER BY RANDOM()"
date: "2021-06-21"
categories: 
  - "note"
tags: 
  - "random"
  - "sql"
---

```
SELECT * FROM repositories ORDER BY RANDOM() LIMIT 3
```

It is slow on big data.

## Implementation

The following solution is built for PostgreSQL, but can be easily applied to any other database.

```
ALTER TABLE repositories ADD COLUMN randomness point;
UPDATE opendor SET randomness = point(random(), random());
CREATE INDEX repositories_randomness on repositories using spgist(randomness);
```

```
SELECT * FROM repositories ORDER BY randomness <-> point(0.753,0.294) LIMIT 3;
```
