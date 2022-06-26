---
title: "matteosister/gitelephant - php скрипт управления git-ом"
date: ""
categories: 
  - "php"
---

![matteosister/gitelephant - php скрипт управления git-ом](https://camo.githubusercontent.com/7a2fb1d0d88d411694087d16c3d0d6a6f69a9d76/68747470733a2f2f7261772e6769746875622e636f6d2f6d617474656f7369737465722f476974456c657068616e742f646576656c6f702f67726170686963732f676974656c657068616e745f3630302e706e67 "matteosister/gitelephant - php скрипт управления git-ом")

  
Пример использования

```
use GitElephant\\Repository;
$repo = new Repository('/path/to/git/repository');

// or the factory method
$repo = Repository::open('/path/to/git/repository');
$repo->getCommit(); // get a Commit instance of the current HEAD
$repo->getCommit('v1.0'); // get a Commit instance for a tag
$repo->getCommit('1ac370d'); // full sha or part of it

// or directly create a commit object
$commit = new Commit($repo, '1ac370d');
$commit = new Commit($repo, '1ac370d'); // head commit

// count commits
$repo->countCommits('1ac370d'); // number of commits to arrive at 1ac370d
// commit is countable, so, with a commit object, you can do
$commit->count();
// as well as
count($commit);
```

  
[https://github.com/matteosister/gitelephant](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21hdHRlb3Npc3Rlci9naXRlbGVwaGFudA%3D%3D)
