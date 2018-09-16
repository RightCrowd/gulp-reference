# gulp-reference
Visual Studio <reference>。<br>
Concat your Javascript modules together for use with visual studio [`reference`](https://msdn.microsoft.com/en-us/library/bb385682(v=vs.110).aspx) tag.


####`main.js`:
```javascript
/// <reference path='~/module.js' />
var defineMain = true;
```
####`module.js`:
```javascript
var defineModule = true;
```
####`gulpfile.js`
```javascript
var gulp = require("gulp");
var reference = require("gulp-reference");

gulp.task("build", function () {
    gulp.src("main.js")
        .pipe(reference())
        .pipe(gulp.dest("output.js"));
}
```
####`module.js`+`main.js`=`output.js`
```javascript
var defineModule = true;
var defineMain = true;
```


