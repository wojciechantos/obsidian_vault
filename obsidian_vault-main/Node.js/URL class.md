[Documentation](https://nodejs.org/api/url.html#url_the_whatwg_url_api)

A URL string is a structured string containing multiple meaningful components. When parsed, a URL object is returned containing properties for each of these components.

The `node:url` module provides two APIs for working with URLs: a legacy API that is Node.js specific, and a newer API that implements the same [WHATWG URL Standard](https://url.spec.whatwg.org/) used by web browsers.

Parsing the URL string using WHATWG API:

```js
const myURL = new URL('https://user:pass@sub.example.com:8080/p/a/t/h?query=string#hash');
```

with legacy API:

```js
const url = require('node:url');

const myURL = url.parse('https://user:pass@sub.example.com:8080/p/a/t/h?query=string#hash');
```

### Constructing a URL from component parts

```js
const myURL = new URL('https://example.org');
myURL.pathname = '/a/b/c';
myURL.search = '?d=e';
myURL.hash = '#fgh';

----------------------------------- // or:

const pathname = '/a/b/c';
const search = '?d=e';
const hash = '#fgh';
const myURL = new URL(`https://example.org${pathname}${search}${hash}`);

// To get the constructed URL string, use the `href` property accessor:

console.log(myURL.href);

```