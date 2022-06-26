---
title: "Gulp плагины gzip, mtime, rsync, rimraf"
date: ""
categories: 
  - "note"
---

Пополнил список [полезных gulp плагинов](https://dev.xfor.top/1784-obzor-poleznyh-gulp-plaginov.html)  
  
**gulp-gzip** — создание gzip архивов (zip и gz)

```
var gulp = require('gulp');
var gzip = require('gulp-gzip');

gulp.task('compress', function() {
    gulp.src('./dev/scripts/*.js')
    .pipe(gzip())
    .pipe(gulp.dest('./public/scripts'));
});
```

  
**gulp-rev-mtime** — создание временной метки для js css

```
var gulp = require('gulp');
var rev = require('gulp-rev-mtime');
 
gulp.task('rev', function () {
    gulp.src('template.html')
        .pipe(rev())
        .pipe(gulp.dest('.'));
});
```

На входе в template.html

```
<link rel="stylesheet" href="main.min.css"/>
 
<script src="abc.js"></script>
<script src="def.js"></script>
```

На выходе получим

```
<link rel="stylesheet" href="main.min.css?v=1393322652000">
 
<script src="abc.js?v=1393321191000"></script>
<script src="def.js?v=1393321187000"></script>
```

  
**gulp-rsync** — rsync, для деплоя файлов на сервер

```
var gulp = require('gulp');
var rsync = require('gulp-rsync');
 
gulp.task('deploy', function() {
  gulp.src('build/**')
    .pipe(rsync({
      root: 'build',
      hostname: 'example.com',
      destination: '/path/to/site'
    }));
});
```

  
**gulp-rimraf** — удаление файлов и директорий

```
var rimraf = require('gulp-rimraf');

gulp.task('task', function() {
  return gulp.src('../temp/*.js', { read: false })
    .pipe(rimraf({ force: true }));
});
```
