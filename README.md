# Gulp, SASS, TypeScript, Browser Sync Basic Configuration

Install the Gulp Command Line Interface

`$ npm install gulp-cli -g`

Clone the Repository

`$ git clone https://github.com/joshmakar/gulp-sass-typescript-browsersync-setup.git`  
or specify the directory name  
`$ git clone https://github.com/joshmakar/gulp-sass-typescript-browsersync-setup.git my-project`

CD into the Directory and NPM Install

`$ npm install`

# Alternatively Setup Your Environment Manually

Install the Gulp Command Line Interface

`$ npm install gulp-cli -g`

Create a package.json file

`$ npm init`

Install Gulp, Gulp SASS, TypeScript, Gulp TypeScript, and Browser Sync

`$ npm i -D gulp gulp-sass typescript gulp-typescript browser-sync`

Create the Gulp File

`/gulpfile.js`  
or  
`/gulpfile.js/index.js`

## Example Gulp File Configurations

### Default Tasks Example

```javascript
function defaultTask(cb) {
  // place code for your default task here
  cb();
}

exports.default = defaultTask;
```

*Run with*  
`$ gulp`


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

*Run with*  
`$ gulp build`


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

*Run with*  
`$ gulp build`


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

*Run with*  
`$ gulp`