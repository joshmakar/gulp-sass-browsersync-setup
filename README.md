# Gulp, SASS, Browser Sync Basic Configuration

Install the Gulp Command Line Interface

`$ npm install gulp-cli -g`

Create a package.json file

`$ npm init`

Install Gulp, Gulp SASS, and Browser Sync

`$ npm i -D gulp gulp-sass browser-sync`

Create the Gulp File

`/gulpfile.js`  
or  
`/gulpfile.js/index.js`

## Examples

### Default Tasks Example

```javascript
function defaultTask(cb) {
  // place code for your default task here
  cb();
}

exports.default = defaultTask;
```


### Series Example

```javascript
const { series } = require('gulp');

function transpile(cb) {
  // body omitted
  cb();
}

function bundle(cb) {
  // body omitted
  cb();
}

exports.build = series(transpile, bundle);
```


### Parallel Example

```javascript
const { parallel } = require('gulp');

function javascript(cb) {
  // body omitted
  cb();
}

function css(cb) {
  // body omitted
  cb();
}

exports.build = parallel(javascript, css);
```


### Watch Series Example

```javascript
const { watch, series } = require('gulp');

function clean(cb) {
  // body omitted
  cb();
}

function javascript(cb) {
  // body omitted
  cb();
}

function css(cb) {
  // body omitted
  cb();
}

exports.default = function() {
  // You can use a single task
  watch('public/css/*.css', css);
  // Or a composed task
  watch('public/*.js', series(clean, javascript));
};
```