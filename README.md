# api documentation for  [rss-watcher (v1.3.0)](https://github.com/nikezono/node-rss-watcher)  [![npm package](https://img.shields.io/npm/v/npmdoc-rss-watcher.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-rss-watcher) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-rss-watcher.svg)](https://travis-ci.org/npmdoc/node-npmdoc-rss-watcher)
#### RSS reader/watcher

[![NPM](https://nodei.co/npm/rss-watcher.png?downloads=true)](https://www.npmjs.com/package/rss-watcher)

[![apidoc](https://npmdoc.github.io/node-npmdoc-rss-watcher/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-rss-watcher_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-rss-watcher/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-rss-watcher/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-rss-watcher/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "nikezono"
    },
    "bin": {
        "rss-watcher": "./bin/rss-watcher"
    },
    "bugs": {
        "url": "https://github.com/nikezono/node-rss-watcher/issues"
    },
    "dependencies": {
        "async": "~0.9.0",
        "colors": "~0.6.2",
        "commander": "~2.2.0",
        "moment": "~2.7.0",
        "parse-rss": "*",
        "rss-frequency": "*"
    },
    "description": "RSS reader/watcher",
    "devDependencies": {
        "coffee-errors": "^0.8.6",
        "coffee-script": "*",
        "coffeelint": "^1.5.2",
        "grunt": "^0.4.5",
        "grunt-blanket": "0.0.8",
        "grunt-cli": "^0.1.13",
        "grunt-coffeelint": "0.0.10",
        "grunt-contrib-clean": "^0.5.0",
        "grunt-contrib-coffee": "^0.10.1",
        "grunt-contrib-copy": "^0.5.0",
        "grunt-contrib-watch": "^0.6.1",
        "grunt-coveralls": "^0.3.0",
        "grunt-mocha-test": "^0.11.0",
        "grunt-notify": "^0.3.0",
        "mocha-lcov-reporter": "0.0.1",
        "underscore": "^1.6.0"
    },
    "directories": {},
    "dist": {
        "shasum": "f6dfbcc781b5f5eae921e72861b470153e5fde9d",
        "tarball": "https://registry.npmjs.org/rss-watcher/-/rss-watcher-1.3.0.tgz"
    },
    "gitHead": "3623718c268ffbbe292c21200295d9948f9cdee7",
    "homepage": "https://github.com/nikezono/node-rss-watcher",
    "keywords": [
        "rss",
        "atom",
        "reader",
        "watcher",
        "watch",
        "read"
    ],
    "license": "MIT",
    "main": "lib/watcher.js",
    "maintainers": [
        {
            "name": "nikezono",
            "email": "nikezono@gmail.com"
        }
    ],
    "name": "rss-watcher",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/nikezono/node-rss-watcher.git"
    },
    "scripts": {
        "test": "grunt test"
    },
    "version": "1.3.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module rss-watcher](#apidoc.module.rss-watcher)
1.  boolean <span class="apidocSignatureSpan">rss-watcher.</span>usingDomains
1.  [function <span class="apidocSignatureSpan">rss-watcher.</span>EventEmitter ()](#apidoc.element.rss-watcher.EventEmitter)
1.  [function <span class="apidocSignatureSpan">rss-watcher.</span>init ()](#apidoc.element.rss-watcher.init)
1.  [function <span class="apidocSignatureSpan">rss-watcher.</span>listenerCount (emitter, type)](#apidoc.element.rss-watcher.listenerCount)
1.  number <span class="apidocSignatureSpan">rss-watcher.</span>defaultMaxListeners
1.  object <span class="apidocSignatureSpan">rss-watcher.</span>__super__



# <a name="apidoc.module.rss-watcher"></a>[module rss-watcher](#apidoc.module.rss-watcher)

#### <a name="apidoc.element.rss-watcher.EventEmitter"></a>[function <span class="apidocSignatureSpan">rss-watcher.</span>EventEmitter ()](#apidoc.element.rss-watcher.EventEmitter)
- description and source-code
```javascript
function EventEmitter() {
  EventEmitter.init.call(this);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.rss-watcher.init"></a>[function <span class="apidocSignatureSpan">rss-watcher.</span>init ()](#apidoc.element.rss-watcher.init)
- description and source-code
```javascript
init = function () {
  this.domain = null;
  if (EventEmitter.usingDomains) {
    // if there is an active domain, then attach to it.
    domain = domain || require('domain');
    if (domain.active && !(this instanceof domain.Domain)) {
      this.domain = domain.active;
    }
  }

  if (!this._events || this._events === Object.getPrototypeOf(this)._events) {
    this._events = new EventHandlers();
    this._eventsCount = 0;
  }

  this._maxListeners = this._maxListeners || undefined;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.rss-watcher.listenerCount"></a>[function <span class="apidocSignatureSpan">rss-watcher.</span>listenerCount (emitter, type)](#apidoc.element.rss-watcher.listenerCount)
- description and source-code
```javascript
listenerCount = function (emitter, type) {
  if (typeof emitter.listenerCount === 'function') {
    return emitter.listenerCount(type);
  } else {
    return listenerCount.call(emitter, type);
  }
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
