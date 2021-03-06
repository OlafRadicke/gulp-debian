### gulp-debian
> :tropical_drink: Gulp plug-in to create a Debian package.

[![Build Status](https://travis-ci.org/stpettersens/gulp-debian.png?branch=master)](https://travis-ci.org/stpettersens/gulp-debian)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](https://github.com/feross/standard)
[![npm version](https://badge.fury.io/js/gulp-debian.svg)](http://npmjs.com/package/gulp-debian)
[![Dependency Status](https://david-dm.org/stpettersens/gulp-debian.png?theme=shields.io)](https://david-dm.org/stpettersens/gulp-debian) [![Development Dependency Status](https://david-dm.org/stpettersens/gulp-debian/dev-status.png?theme=shields.io)](https://david-dm.org/stpettersens/gulp-debian#info=devDependencies)

##### Install

    $ npm install --save-dev gulp-debian

##### Usage
```js
'use strict'

const gulp = require('gulp')
const deb = require('gulp-debian')

gulp.task('default', function () {
  return gulp.src(['demo.sh','blob.bin'])
  .pipe(deb({
     package: 'demo',
     version: '0.1-1',
     section: 'base',
     priority: 'optional',
     architecture: 'i386',
     maintainer: 'Mr. Apt <apt@nowhere.tld>',
     description: 'A dummy package',
     _target: 'opt/demo',
     _out: 'dist'
  }))
})
```

##### Options

* Options: Object containing properties for a Debian file and the following parameters:
	* _target: string - The installation target for the created Debian package (mandatory).
	* _out: string - The target directory to create the Debian package in (mandatory).
	* _verbose: boolean - Verbose output from dpkg-deb utility (optional; true if omitted).

##### Contributors

* [Sam Saint-Pettersen](https://github.com/stpettersens)
* [Oliver Skånberg-Tippen](https://github.com/oskanberg)
* [Olaf Radicke](https://github.com/OlafRadicke)


##### License

[MIT](https://opensource.org/licenses/MIT)
