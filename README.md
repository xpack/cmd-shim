# @xpack/cmd-shim

Fork of [cmd-shim](https://github.com/npm/cmd-shim), used
by `xpm` to create executable scripts on Windows,
since symlinks are not suitable for this purpose there.

On Unix systems, you should use a symbolic link instead.

[![npm version](https://img.shields.io/npm/v/cmd-shim.svg)](https://www.npmjs.com/package/@xpack/cmd-shim)

## Installation

```console
npm install @xpack/cmd-shim
```

## API

### cmdShim(from, to) -> Promise

Create a cmd shim at `to` for the command line program at `from`.
e.g.

```javascript
var cmdShim = require('@xpack/cmd-shim');
cmdShim(__dirname + '/cli.js', '/usr/bin/command-name').then(() => {
  // shims are created!
})
```

### cmdShim.ifExists(from, to) -> Promise

The same as above, but will just continue if the file does not exist.
