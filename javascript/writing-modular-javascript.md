# Writing Modular JavaScript

More than a year ago, I was tring to figure out what modular JavaScript really means. 

I read about [Writing Modular JavaScript With AMD, CommonJS & ES Harmony](https://addyosmani.com/writing-modular-js/) by Addy Osmani. But it turned out that the new concepts like `CommonJS`, `AMD`, `ES6 Module` were too overwhelming that when they all came at the same time, I was only able to have a vague understanding about those concepts. I know CommonJS is used in Node env, AMD is for async, and for a long time we are gonna be using ES6 Module, that's all.

But seems like it doesn't matter to me not knowing what are the underlying stuff behind those concepts. I have been using ES6 Modules, and it fits both me and my team well.

But lately when I dived into the world Node, I finally got hang of what CommonJS truly is. And with the understanding of CJS and ES6 Module, I quickly grasped the basics of AMD, which really helps me finally get some sense of what Modular means.

I'm gonna make this short and paste a lot of reference link for you to explore yourself.  

## CommonJS

We don't have module standard at front-end at first, but we do in Node environment, which is CommonJS.

The simpliest example could be(suppose these two files are in the same folder):

```js
// in person.js
exports.yellName = function(name) {
  console.log('Hi my name is' + name.toUpperCase() + '!!');
} 
```
and

```js
// in main.js
const path = require('path')  // require native or 3rd party dependencies
const person = require('./person')  // require modules that we write ourselves

person.yellName('Chang')  // Hi my name is CHANG!!
```

You may also notice that other than `exports`, there is also `module.exports`. About the **difference**, the short answer is:

> Quick Summary: both exports and module.exports point to the same object, unless you reassign one. And in the end module.exports is returned. So if you reassigned exports to a function then dont expect a function since exports itself isn't going to be returned. However if you had assigned function like this exports.func = function... then resulting thing would have func property with function as a value. Because you added the property to the object that exports was pointing to.. – Muhammad Umer

And refer to this great resource if you feel still confused:

[Node.js Module – exports vs module.exports](http://www.hacksparrow.com/node-js-exports-vs-module-exports.html)

Another thing to note is that CJS is synchronous loading, which doesn't support callback or dynamically loading.

## ES6 Modules

Then after a long time, we have the standardized module pattern in front-end, which is brought by the new version of ECMAScript 2015. As a front-end developer, this could possibly be the part that you are most familiar with. So I'm just gonna skip this part, refer to these links if you want to learn more:

[import | MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/import)
[export | MDN](https://developer.mozilla.org/en/docs/web/javascript/reference/statements/export)
[ES6 Modules](http://exploringjs.com/es6/ch_modules.html)
[ECMAScript 6 Modules: the Final Syntax](http://2ality.com/2014/09/es6-modules-final.html)

## AMD Modules

CommonJS is used in Node, and it's synchronous. But that doesn't necessarily apply to what we expect the module should be in front-end. Because in front-end we may want a slightly different pattern of modularity. So then we have AMD, which stands for `Asynchronous Module Definition`, which is obviously, asynchronous. The main difference is that AMD uses a wrapper called `define`. And rather than attach stuff to `exports` or `module.exports`, in AMD, the module is what we return in the callback of `define`.

And note that `RequireJS` is a popular implementation of AMD in front-end world.

Refer to [this](https://addyosmani.com/writing-modular-js/) for some examples of AMD.

## ES6 Module

Then after a long time, we have the standardized module pattern in front-end, which is brought by the new version of ECMAScript 2015, aka, ES6. Using webpack, we could take good advantage of `import` and `export`.

Forgive me I'm gonna skip this part...
 
