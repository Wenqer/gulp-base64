gulp-base64
===========

Gulp task for converting all data found within a stylesheet (those within a url( ... ) declaration) into base64-encoded data URI strings.

## Example usage
```js
var gulp = require('gulp');
var base64 = require('./build/gulp-base64');

//basic example
gulp.task('build', function () {
    return gulp.src('./css/*.css')
        .pipe(base64())
        .pipe(concat('main.css'))
        .pipe(gulp.dest('./public/css'));
});
...
//example with options
gulp.task('build', function () {
    return gulp.src('./css/*.css')
        .pipe(base64({
            baseDir: 'public',
            extensions: ['svg', 'png'],
            debug: true
        }))
        .pipe(concat('main.css'))
        .pipe(gulp.dest('./public/css'));
});

```
## Options

- `baseDir`

        If you have absolute image paths in your stylesheet, the path specified
        in this option will be used as the base directory (relative to gulpfile).

- `extensions`

        proccess only specified extensions.

- `debug`

        enable log to console.
