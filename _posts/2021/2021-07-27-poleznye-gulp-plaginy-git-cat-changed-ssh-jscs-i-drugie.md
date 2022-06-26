---
title: "Полезные gulp-плагины: git, cat, changed, ssh, jscs и другие"
date: ""
categories: 
  - "note"
---

Обновил списочек новыми на мой взгляд полезными [плагинами](https://dev.xfor.top/1784-obzor-poleznyh-gulp-plaginov.html).  
  
**gulp-git** — для работы с git  

```
// Run git commit 
// src are the files to commit (or ./*) 
gulp.task('commit', function(){
  return gulp.src('./git-test/*')
    .pipe(git.commit('initial commit'));
});
```

  
**gulp-changed** — обработка только измененых файлов  

```
gulp.task('default', function () {
    return gulp.src(SRC)
        .pipe(changed(DEST))
        // ngAnnotate will only get the files that 
        // changed since the last time it was run 
        .pipe(ngAnnotate())
        .pipe(gulp.dest(DEST));
});
```

  
**gulp-cat** — выводит файл в консоль  

```
gulp.task('default', function() {
    return gulp.src('./README.md')
        .pipe(cat());
});
```

  
**gulp-svgmin** — минимизация svg файлов  

```
gulp.task('default', function () {
    return gulp.src('logo.svg')
        .pipe(svgmin())
        .pipe(gulp.dest('./out'));
});
```

  
**gulp-image-embed** — конвертирует img в стилях в data-URI  

```
gulp.task('embed', function(){
  return gulp.src('*.css')
    .pipe(embed({
      asset: 'static'
    }))
    .pipe(gulp.dest('build.css'));
});
```

  
**gulp-ssh** — для работы с SSH и SFTP  

```
var config = {
  host: '192.168.0.21',
  port: 22,
  username: 'iojs',
  privateKey: fs.readFileSync('/Users/zensh/.ssh/id_rsa')
}
  
var gulpSSH = new GulpSSH({
  ignoreErrors: false,
  sshConfig: config
})
 
gulp.task('exec', function () {
  return gulpSSH
    .exec(['uptime', 'ls -a', 'pwd'], {filePath: 'commands.log'})
    .pipe(gulp.dest('logs'))
})
```

  
**gulp-css-base64** — конвертация данных в стилях в base64 data URI  

```
gulp.task('default', function () {
    return gulp.src('src/css/input.css')
        .pipe(cssBase64({
            baseDir: "../../images",
            maxWeightResource: 100,
            extensionsAllowed: ['.gif', '.jpg']
        }))
        .pipe(gulp.dest('dist'));
});
```

  
**gulp-jscs** — проверяет ваш js на правильность javascript Code Style http://jscs.info/  

```
gulp.task('default', function () {
    return gulp.src('src/app.js')
        .pipe(jscs());
});
```
