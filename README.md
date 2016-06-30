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

```
var deleteUnusedImages = require('gulp-delete-unused-images');

gulp.src(['dev/images/**/*', 'dev/edm.html'])
  .pipe(plumber())
  .pipe(deleteUnusedImages({
    log: true,
    delete: true
  }))
  .pipe(gulp.dest('./deploy'));
```

## Contributing

I'm new to writing Gulp plugins, be gentle. If there's anything you find wrong with this, please help.

## Known Issues

- Using an image file extension in a CSS class will result in a match and won't delete the image. The same happens using dot notation in JavaScript files  

    ```
    div.jpg { background-image: url('images/some-image.jpg'); }

    ---

    if (myObj.file.images.jpg) {
    //...
    }
    ```

- If multiple image files exist in subfolders that are under the root directory and the name is referenced in the source file. It won't delete any of the named files that match.  

    ```
    images/filename.jpg
    images/subfolder/filename.jpg

    ...

    <img src="images/subfolder/filename.jpg" alt="Some great file">
    ```

## Release History

* 0.0.4 Update README
* 0.0.3 Fix options
* 0.0.2 Patches for regex
* 0.0.1 Initial release
