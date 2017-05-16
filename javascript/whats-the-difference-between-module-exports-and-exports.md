# What's the Difference Between `module.exports` and `exports` in CommonJS

We know that Node.js uses CommonJS Standard to implement modular JavaScript. Also, we know that we could export something like:

```js
// rocker.js
exports yell = () => console.log("I'm a Rocker Singer!")

// main.js
const rocker = require('./rocker')
rocker.yell() // I'm a Rocker Singer!
```

But we also often see `module.exports` instead of `exports`, so what's the diffenrence?

Here is an eye-opener - `module.exports` is the real deal. `exports` is just `module.exports`'s little helper. Your module returns `module.exports` to the caller ultimately, not `exports`. All `exports` does is collect properties and attach them to `module.exports` IF `module.exports` doesn't have something on it already. If there's something attached to `module.exports` already, everything on `exports` is ignored.

So here is the case: In what cases should we prefer `module.exports` to `exports`?

Your modules can be any legal JavaScript object - boolean, number, date, JSON, string, function, array, and so on. Your module is whatever you set `module.exports` to. If you don't set `module.exports` to anything explicitly, the properties of `exports` and attached to it and returned.

So the short answer is: if you want your module to be of a specific object type, use `module.exports`; if you want your module to be a typical module instance, use `exports`.

Basically Node.js doesn't export the object that `exports` currently references, but exports the properties of what `exports` originally references(`module.exports`).

Great resource: [node-js-exports-vs-module-exports.html](hacksparrow.com/node-js-exports-vs-module-exports.html)