---
title: "cachetool - CLI приложение для раобты с apc & opcache"
date: ""
categories: 
  - "php"
---

```
apc
  apc:bin:dump             Get a binary dump of files and user variables
  apc:bin:load             Load a binary dump into the APC file and user variables
  apc:cache:clear          Clears APC cache (user, system or all)
  apc:cache:info           Shows APC user & system cache information
  apc:cache:info:file      Shows APC file cache information
  apc:key:delete           Deletes an APC key
  apc:key:exists           Checks if an APC key exists
  apc:key:fetch            Shows the content of an APC key
  apc:key:store            Store an APC key with given value
  apc:sma:info             Show APC shared memory allocation information
apcu
  apcu:cache:clear         Clears APCu cache
  apcu:cache:info          Shows APCu user & system cache information
  apcu:cache:info:keys     Shows APCu keys cache information
  apcu:key:delete          Deletes an APCu key
  apcu:key:exists          Checks if an APCu key exists
  apcu:key:fetch           Shows the content of an APCu key
  apcu:key:store           Store an APCu key with given value
  apcu:regexp:delete       Deletes all APCu key matching a regexp
  apcu:sma:info            Show APCu shared memory allocation information
opcache
  opcache:configuration    Get configuration information about the cache
  opcache:reset            Resets the contents of the opcode cache
  opcache:status           Show summary information about the opcode cache
  opcache:status:scripts   Show scripts in the opcode cache
stat
  stat:clear               Clears the file status cache, including the realpath cache
  stat:realpath_get        Show summary information of realpath cache entries
  stat:realpath_size       Display size of realpath cache
```

  
[https://github.com/gordalina/cachetool](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2dvcmRhbGluYS9jYWNoZXRvb2w%3D)
