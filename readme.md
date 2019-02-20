# gulp-rev-custom [![Build Status](https://travis-ci.org/evont/gulp-rev.svg?branch=master)](https://travis-ci.org/evont/gulp-rev)

[gulp-rev](https://www.npmjs.com/package/gulp-rev-custom) 是基于 [gulp-rev](https://www.npmjs.com/package/gulp-rev) & [gulp-rev-collector](https://www.npmjs.com/package/gulp-rev-collector)改造，将hash 值置于文件后，避免生成多个的文件，同时封装rev-collector， 无需安装两个依赖。

## Install

```
$ npm install --save-dev gulp-rev-custom
```


## Usage

```js
const gulp = require('gulp');
const rev = require('gulp-rev-custom');
const { revCollector } = rev;
gulp.task('default', () =>
	gulp.src('src/*.css')
    .pipe(rev())
    .pipe(rev.manifest({ merge: true }))
		.pipe(gulp.dest('dist'))
);
// or
gulp.task('default', () =>
	gulp.src('src/*.html')
		.pipe(revCollector({
      replaceReved: true,
    }))
		.pipe(gulp.dest('dist'))
);
```

## API
参考[gulp-rev](https://www.npmjs.com/package/gulp-rev) & [gulp-rev-collector](https://www.npmjs.com/package/gulp-rev-collector)
