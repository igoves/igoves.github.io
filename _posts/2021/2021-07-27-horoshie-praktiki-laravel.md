---
title: "Хорошие практики Laravel"
categories: 
  - "note"
---

[![Хорошие практики Laravel](images/logo-russian.png "Хорошие практики Laravel")](https://raw.githubusercontent.com/alexeymezenin/laravel-best-practices/master/images/logo-russian.png)

  
SRP  
Плохо:

```
public function getFullNameAttribute()
{
    if (auth()->user() && auth()->user()->hasRole('client') && auth()->user()->isVerified()) {
        return 'Mr. ' . $this->first_name . ' ' . $this->middle_name . ' ' . $this->last_name;
    } else {
        return $this->first_name[0] . '. ' . $this->last_name;
    }
}
```

  
Хорошо:

```
public function getFullNameAttribute()
{
    return $this->isVerifiedClient() ? $this->getFullNameLong() : $this->getFullNameShort();
}

public function isVerifiedClient()
{
    return auth()->user() && auth()->user()->hasRole('client') && auth()->user()->isVerified();
}

public function getFullNameLong()
{
    return 'Mr. ' . $this->first_name . ' ' . $this->middle_name . ' ' . $this->last_name;
}

public function getFullNameShort()
{
    return $this->first_name[0] . '. ' . $this->last_name;
}
```

  
[https://github.com/alexeymezenin/laravel-best-practices/blob/master/russian.md](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FsZXhleW1lemVuaW4vbGFyYXZlbC1iZXN0LXByYWN0aWNlcy9ibG9iL21hc3Rlci9ydXNzaWFuLm1k)
