# coffeeify

browserify v2 plugin for coffee-script

mix and match `.coffee` and `.js` files in the same project

**important: when using require('path/to/file.coffee') remember to use .coffee extension - soon to be fixed, [the browserify devs have relented](https://github.com/shtylman/node-browser-resolve/issues/20#issuecomment-18303661)! go [+1 this pr](https://github.com/shtylman/node-browser-resolve/pull/12) until it gets merged :-)**

[![build status](https://secure.travis-ci.org/jnordberg/coffeeify.png)](http://travis-ci.org/jnordberg/coffeeify)

# example

given some files written in a mix of `js` and `coffee`:

foo.coffee:

``` coffee
console.log(require './bar.js')
```

bar.js:

``` js
module.exports = require('./baz.coffee')(5)
```

baz.coffee:

``` js
module.exports = (n) -> n * 111
```

install coffeeify into your app:

```
$ npm install coffeeify
```

when you compile your app, just pass `-t coffeeify` to browserify:

```
$ browserify -t coffeeify foo.coffee > bundle.js
$ node bundle.js
555
```

# install

With [npm](https://npmjs.org) do:

```
npm install coffeeify
```

# license

MIT
