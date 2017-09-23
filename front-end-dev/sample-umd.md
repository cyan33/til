Thanks [@loatheb](https://github.com/loatheb) to his insight into helping me out of this issue.

Say you write a module like this:

```js
const hello = () => console.log('Hello world!');

module.exports = hello;
```

After you publish this package to npm, this can be consumed by Node.js developers and client side developers who have webpack installed:

```
npm install hello
```

```js
// Node.js consumption
const hello = require('hello');
```
or

```js
// webpack(es6)
import hello from 'hello';
```

However, a lot of users are still also using `AMD`, or they just installed the js file directly and insert the code through a `<script>` tag in the html file.

So if your module is intended to fit all those scenarios, you could do this:

```js
if (typeof exports === 'object') {
  // node
  module.exports = hello;
} else if (typeof define === 'function' && define.amd) {
  // amd
  define(function() { return root.hello = hello; })
} else {
  // script tag
  root.hello = hello;
}
```

**Note** root is the mixin, which is the reference to `window`(browser) or `global`(node):
```js
;(function(root) {
  // module content goes inside the function
})(typeof window === 'object' ? window : global)
```
