gulp-base64
===========

Gulp task for converting all data found within a stylesheet (those within a url( ... ) declaration) into base64-encoded data URI strings. This includes images and fonts.

## Example usage
```js
var gulp = require('gulp');
var base64 = require('./build/gulp-base64');

gulp.task('build', function () {
    return gulp.src('./css/*.css')
        .pipe(base64())
        .pipe(concat('main.css'))
        .pipe(gulp.dest('./public/css'));
});

```
