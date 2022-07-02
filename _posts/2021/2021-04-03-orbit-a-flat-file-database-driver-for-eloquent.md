---
title: "orbit - a flat-file database driver for Eloquent"
date: "2021-04-03"
categories: 
  - "php"
tags: 
  - "database"
  - "file"
  - "flat"
---

![](images/orbit.png)

```
use Illuminate\Database\Schema\Blueprint;

class Post extends Model
{
    use Orbit\Concerns\Orbital;

    public static function schema(Blueprint $table)
    {
        $table->string('title');
        $table->string('slug');
        $table->text('content')->nullable();
        $table->timestamp('published_at');
    }
}
```

[https://github.com/ryangjchandler/orbit](https://github.com/ryangjchandler/orbit)
