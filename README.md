# mini-xhr

[![NPM version][npm-image]][npm-url]
[![build status][travis-image]][travis-url]
[![David deps][david-image]][david-url]
[![devDependencies Status][david-dev-image]][david-dev-url]
[![node version][node-image]][node-url]
[![npm download][download-image]][download-url]
[![npm license][license-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/mini-xhr.svg?style=flat-square
[npm-url]: https://npmjs.org/package/mini-xhr
[travis-image]: https://img.shields.io/travis/cycdpo/mini-xhr.svg?style=flat-square
[travis-url]: https://travis-ci.org/cycdpo/mini-xhr
[david-image]: https://img.shields.io/david/cycdpo/mini-xhr.svg?style=flat-square
[david-url]: https://david-dm.org/cycdpo/mini-xhr
[david-dev-image]: https://david-dm.org/cycdpo/mini-xhr/dev-status.svg?style=flat-square
[david-dev-url]: https://david-dm.org/cycdpo/mini-xhr?type=dev
[node-image]: https://img.shields.io/badge/node.js-%3E=_6.0-green.svg?style=flat-square
[node-url]: http://nodejs.org/download/
[download-image]: https://img.shields.io/npm/dm/mini-xhr.svg?style=flat-square
[download-url]: https://npmjs.org/package/mini-xhr
[license-image]: https://img.shields.io/npm/l/mini-xhr.svg?style=flat-square

## Install
```shell
# via npm
$ npm install mini-xhr --save

# or via yarn
$ yarn add mini-xhr
```

## Usage
```javascript
import miniXhr from 'mini-xhr';

# OR
const miniXhr = require('mini-xhr');

miniXhr(url [, options])
  .then((data) => {
    // handle data
  });
```

* options:
  * `mode`: [String] Allows three modes.
    * `'xhr'`(Default)
    * `'jsonp'`
    * `'script'`
  * `method`: [String] Xhr action. Default `'POST'`.
  * `data`: [Object] The key-value pair that needs to be transmitted. Default `{}`.
  * `dataType`: [String] Request data type. Default `''`. Other: `'json'`
  * `timeout`: [Number] Set the timeout. Default `0`.
  * `timeoutCB`: [Function] Set the time-out callback function. Default `null`.

### Use in browser: E.g.
```html
<script src="miniXhr.min.js"></script>
<script>
  miniXhr('/getData' , {
    mode: 'jsonp',
    dataType: 'json',
    data: {
      key1: value1,
      key2: value2,
    }
  })
    .then(function(data) {
      // data handle
    });
</script>
```

