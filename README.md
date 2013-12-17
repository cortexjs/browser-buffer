browser-buffer
===============

A port of buffer module for cortex from [node.js](http://nodejs.org/). This is
a fork of [native-buffer-browserify](https://github.com/feross/native-buffer-browserify).

[![testling badge](https://ci.testling.com/cortexjs/browser-buffer.png)](https://ci.testling.com/cortexjs/browser-buffer)

It will also be loaded if you use the global `Buffer` variable.

## Features

- Backed by `ArrayBuffer` (not `Object`, so it's fast)
- Preserves Node API exactly
- Faster pretty much across the board (see perf results below)
- `.slice()` returns instances of the same type
- Square-bracket `buf[4]` notation works!
- Does not modify any browser prototypes.
- All tests from the original `buffer-browserify` project pass.
- Requires browsers to have `Uint8Array` and `DataView` support (all modern
  browsers, IE10+, shim for older browsers included)

## How does it work?

The `Buffer` constructor returns instances of `Uint8Array` that are augmented with function properties for all the Buffer API functions. We use `Uint8Array` so that square bracket notation works as expected -- it returns a single octet.

By augmenting the instances, we can avoid modifying the Uint8Array prototype.




## MIT License

Copyright (C) 2013 [Feross Aboukhadijeh](http://feross.org), Romain Beauxis, and other contributors.
