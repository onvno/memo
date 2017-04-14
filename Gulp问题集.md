### Gulp问题集

#### 如何忽略某一目录下的子目录文件

如需要忽略`app`下的`_tmp`文件，以下为错误方案

```
gulp.task('copy', function() {
    return gulp.src(['app/**', '!app/_tmp/**'])
        .pipe(gulp.dest('dist'));
});
```

正确方案需要将目录及目录下的文件一并ignore：

```
gulp.task('copy', function() {
    return gulp.src(['app/**', '!app/_temp', '!app/_tmp/**'])
        .pipe(gulp.dest('dist'));
});
```

更简洁语法：

```
gulp.src(['app/**', '!app/_tmp{,/**/*}'])
```



#### 拷贝设置基本目录

方法：

```
gulp.src([
        'market/src/conf/**/*',
        'market/src/css/**/*'
    ],{base:'market/src'})
```







