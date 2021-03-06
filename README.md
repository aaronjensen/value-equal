# value-equal [![npm package][npm-badge]][npm]

[npm-badge]: https://img.shields.io/npm/v/value-equal.svg?style=flat-square
[npm]: https://www.npmjs.org/package/value-equal

[`value-equal`](https://www.npmjs.com/package/value-equal) determines if two JavaScript values are equal using [`Object.prototype.valueOf`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/valueOf).

In many instances when I'm checking for object equality, what I really want to know is if their **values** are equal. This is good for:

- Stuff you keep in `localStorage`
- `window.history.state` values
- Query strings

## Installation

Using [npm](https://www.npmjs.com/):

    $ npm install --save value-equal

Then with a module bundler like [webpack](https://webpack.github.io/), use as you would anything else:

```js
// using an ES6 transpiler, like babel
import valueEqual from 'value-equal'

// not using an ES6 transpiler
var valueEqual = require('value-equal')
```

The UMD build is also available on [unpkg](https://unpkg.com):

```html
<script src="https://unpkg.com/value-equal/umd/value-equal.min.js"></script>
```

You can find the library on `window.valueEqual`.

## Usage

```js
valueEqual(1, 1)                           // true
valueEqual('asdf', 'asdf')                 // true
valueEqual('asdf', new String('asdf'))     // true
valueEqual(true, true)                     // true
valueEqual(true, false)                    // false
valueEqual({ a: 'a' }, { a: 'a' })         // true
valueEqual({ a: 'a' }, { a: 'b' })         // false
valueEqual([ 1, 2, 3 ], [ 1, 2, 3 ])       // true
valueEqual([ 1, 2, 3 ], [ 2, 3, 4 ])       // false
```

That's it. Enjoy!
