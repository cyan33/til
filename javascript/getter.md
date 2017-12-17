# Properties Getters

The `get` syntax binds an object property to a function that will be called when that property is looked up.

The following sample code snippets are from [MDN | getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)

```js
var obj = {
  log: ['example','test'],
  get latest() {
    if (this.log.length == 0) return undefined;
    return this.log[this.log.length - 1];
  }
}
console.log(obj.latest); // "test".
```

And the property itself could also be computed

```js
var expr = 'foo';

var obj = {
  get [expr]() { return 'bar'; }
};

console.log(obj.foo); // "bar"
```

To delete a property / getter:

```js
delete obj.latest;
```
