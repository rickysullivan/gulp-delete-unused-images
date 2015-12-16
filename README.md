# Gulp Delete Unused Images

gulp-delete-unused-images is a Gulp plugin which will find unused graphics inside text files (html|css|js) and deletes them.

Inspired by [https://github.com/mcfedr/gulp-unused-images](https://github.com/mcfedr/gulp-unused-images)

## Installation

    npm install gulp-delete-unused-images --save

## Options

* `log` *boolean* | default: **false**

    Log the output to console

* `delete` *boolean* | default: **true**

	Delete the files :)

## Usage

    var deleteUnusedImages = require('gulp-delete-unused-images');

    gulp.src(['dev/images/**/*', 'dev/edm.html'])
      .pipe(plumber())
      .pipe(deleteUnusedImages({
        log: true,
        delete: true
      }))
      .pipe(gulp.dest('./deploy')

## Contributing

I'm new to writing Gulp plugins, be gentle. If there's anything you find wrong with this, please help.

## Release History

* 0.0.1 Initial release
