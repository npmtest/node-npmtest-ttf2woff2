# npmtest-ttf2woff2

#### basic test coverage for  [ttf2woff2 (v2.0.3)](https://github.com/nfroidure/ttf2woff2)  [![npm package](https://img.shields.io/npm/v/npmtest-ttf2woff2.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-ttf2woff2) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-ttf2woff2.svg)](https://travis-ci.org/npmtest/node-npmtest-ttf2woff2)

#### Convert TTF files to WOFF2 ones.

[![NPM](https://nodei.co/npm/ttf2woff2.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/ttf2woff2)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-ttf2woff2/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-ttf2woff2/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-ttf2woff2/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-ttf2woff2/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-ttf2woff2/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-ttf2woff2/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-ttf2woff2/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-ttf2woff2/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-ttf2woff2/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-ttf2woff2/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-ttf2woff2/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-ttf2woff2/build/test-report.html](https://npmtest.github.io/node-npmtest-ttf2woff2/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-ttf2woff2/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-ttf2woff2/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-ttf2woff2/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-ttf2woff2/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-ttf2woff2/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-ttf2woff2/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-ttf2woff2/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-ttf2woff2/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "ttf2woff2",
    "version": "2.0.3",
    "description": "Convert TTF files to WOFF2 ones.",
    "main": "src/index.js",
    "browser": "jssrc/index.js",
    "engines": {
        "node": ">=0.12"
    },
    "directories": {
        "test": "tests"
    },
    "scripts": {
        "test": "mocha tests/*.mocha.js",
        "coveralls": "istanbul cover _mocha --report lcovonly -- tests/*.mocha.js -R spec -t 5000 && cat ./coverage/lcov.info | coveralls && rm -rf ./coverage",
        "cover": "istanbul cover --report html _mocha -- tests/*.mocha.js -R spec -t 5000",
        "cli": "env NPM_RUN_CLI=1",
        "configure": "node-gyp configure",
        "lint": "eslint src/*.js tests/*.src jssrc/index.js",
        "preversion": "npm run lint && npm test",
        "make": "node-gyp build",
        "emcc": "miniquery -p \"targets.#.sources.#\" ./binding.gyp | grep -v \"csrc/addon.cc\" | xargs emcc --bind -o jssrc/ttf2woff2.js -O3 --memory-init-file 0 -s \"TOTAL_MEMORY=536870912\" -s \"ALLOW_MEMORY_GROWTH=1\" --post-js jssrc/post.js csrc/fallback.cc",
        "emcc-debug": "miniquery -p \"targets.#.sources.#\" ./binding.gyp | grep -v \"csrc/addon.cc\" | xargs emcc --bind -o jssrc/ttf2woff2.js -s \"ALLOW_MEMORY_GROWTH=1\" -s \"ASSERTIONS=1\" --post-js jssrc/post.js csrc/fallback.cc",
        "install": "(node-gyp rebuild > builderror.log) || (exit 0)"
    },
    "repository": {
        "type": "git",
        "url": "git@github.com:nfroidure/ttf2woff2.git"
    },
    "keywords": [
        "ttf",
        "woff2",
        "fonts"
    ],
    "author": "Nicolas Froidure",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/nfroidure/ttf2woff2/issues"
    },
    "homepage": "https://github.com/nfroidure/ttf2woff2",
    "dependencies": {
        "bindings": "^1.2.1",
        "bufferstreams": "^1.1.0",
        "nan": "^2.1.0",
        "node-gyp": "^3.0.3"
    },
    "devDependencies": {
        "coveralls": "^2.11.4",
        "eslint": "^1.4.1",
        "eslint-config-simplifield": "^1.1.0",
        "istanbul": "^0.3.19",
        "miniquery": "^1.1.1",
        "mocha": "^2.3.2",
        "mocha-lcov-reporter": "^0.0.2"
    },
    "preferGlobal": "true",
    "bin": {
        "ttf2woff2": "bin/ttf2woff2.js"
    },
    "gypfile": true
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
