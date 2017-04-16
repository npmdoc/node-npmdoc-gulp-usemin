# api documentation for  [gulp-usemin (v0.3.28)](https://github.com/zont/gulp-usemin#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-usemin.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-usemin) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-usemin.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-usemin)
#### Replaces references to non-optimized scripts or stylesheets into a set of HTML files (or any templates/views).

[![NPM](https://nodei.co/npm/gulp-usemin.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gulp-usemin)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-usemin/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-usemin/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-usemin/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-usemin/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Alexander Zonov"
    },
    "bugs": {
        "url": "https://github.com/zont/gulp-usemin/issues"
    },
    "dependencies": {
        "glob": "~7.1.1",
        "gulp-concat": "~2.6.1",
        "gulp-util": "~3.0.8",
        "through2": "~2.0.3"
    },
    "description": "Replaces references to non-optimized scripts or stylesheets into a set of HTML files (or any templates/views).",
    "devDependencies": {
        "event-stream": "~3.3.4",
        "gulp": "~3.9.1",
        "gulp-clean-css": "~2.3.2",
        "gulp-htmlmin": "~3.0.0",
        "gulp-jshint": "~2.0.4",
        "gulp-less": "3.3.0",
        "gulp-mocha": "~3.0.1",
        "gulp-rev": "~7.1.2",
        "gulp-uglify": "~2.0.1",
        "jshint": "~2.9.4",
        "vinyl-fs": "~2.4.4"
    },
    "directories": {},
    "dist": {
        "shasum": "78f5886189720c48da7a0ffde65f0928fb54fcd1",
        "tarball": "https://registry.npmjs.org/gulp-usemin/-/gulp-usemin-0.3.28.tgz"
    },
    "engines": {
        "node": ">=0.12"
    },
    "gitHead": "0963c4dc8ef6355b1165be7eeabe741f3d6e8903",
    "homepage": "https://github.com/zont/gulp-usemin#readme",
    "keywords": [
        "gulpplugin",
        "usemin",
        "gulp-usemin"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "alexander.zonov"
        }
    ],
    "name": "gulp-usemin",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/zont/gulp-usemin.git"
    },
    "scripts": {
        "test": "gulp"
    },
    "version": "0.3.28"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-usemin](#apidoc.module.gulp-usemin)
1.  [function <span class="apidocSignatureSpan"></span>gulp-usemin (options)](#apidoc.element.gulp-usemin.gulp-usemin)
1.  [function <span class="apidocSignatureSpan">gulp-usemin.</span>toString ()](#apidoc.element.gulp-usemin.toString)



# <a name="apidoc.module.gulp-usemin"></a>[module gulp-usemin](#apidoc.module.gulp-usemin)

#### <a name="apidoc.element.gulp-usemin.gulp-usemin"></a>[function <span class="apidocSignatureSpan"></span>gulp-usemin (options)](#apidoc.element.gulp-usemin.gulp-usemin)
- description and source-code
```javascript
gulp-usemin = function (options) {
  var through = require('through2');
  var gutil = require('gulp-util');
  var blocksBuilder = require('./lib/blocksBuilder.js');
  var htmlBuilder = require('./lib/htmlBuilder.js');

  return through.obj(function(file, enc, callback) {
    if (file.isStream()) {
      this.emit('error', new gutil.PluginError('gulp-usemin', 'Streams are not supported!'));
      callback();
    }
    else if (file.isNull())
      callback(null, file); // Do nothing if no contents
    else {
      try {
        var blocks = blocksBuilder(file, options);
        htmlBuilder(file, blocks, options, this.push.bind(this), callback);
      } catch(e) {
        this.emit('error', e);
        callback();
      }
    }
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-usemin.toString"></a>[function <span class="apidocSignatureSpan">gulp-usemin.</span>toString ()](#apidoc.element.gulp-usemin.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
