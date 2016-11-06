# hast-util-to-parse5 [![Build Status][travis-badge]][travis] [![Coverage Status][codecov-badge]][codecov]

Transform [HAST][] to [Parse5’s AST][ast].

Why not use an adapter? Because it’s more code weight to use adapters,
and much more fragile.

## Installation

[npm][npm-install]:

```bash
npm install hast-util-to-parse5
```

## Usage

Dependencies:

```javascript
var toParse5 = require('hast-util-to-parse5');
```

Fixture:

```javascript
var ast = toParse5({
  type: 'element',
  tagName: 'h1',
  properties: {},
  children: [{type: 'text', value: 'World!'}]
});
```

Yields:

```js
{ nodeName: 'h1',
  tagName: 'h1',
  attrs: [],
  namespaceURI: 'http://www.w3.org/1999/xhtml',
  childNodes: [ { nodeName: '#text', value: 'World!', parentNode: [Circular] } ] }
```

## API

### `toParse5(node)`

Transform a [HAST Node][node] to an `ASTNode` according to the default
Parse5 adapter.

## License

[MIT][license] © [Titus Wormer][author]

<!-- Definitions -->

[travis-badge]: https://img.shields.io/travis/wooorm/hast-util-to-parse5.svg

[travis]: https://travis-ci.org/wooorm/hast-util-to-parse5

[codecov-badge]: https://img.shields.io/codecov/c/github/wooorm/hast-util-to-parse5.svg

[codecov]: https://codecov.io/github/wooorm/hast-util-to-parse5

[npm-install]: https://docs.npmjs.com/cli/install

[license]: LICENSE

[author]: http://wooorm.com

[hast]: https://github.com/wooorm/hast

[ast]: https://github.com/inikulin/parse5/wiki/Documentation

[node]: https://github.com/wooorm/hast#ast