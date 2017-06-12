# Difference Between `for...in` and `for...of`

From [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of): 

> The for...in loop will iterate over all enumerable **properties** of an object.

> The for...of syntax is specific to **collections**, rather than all objects. It will iterate in this manner over the **elements** of any collection that has a [Symbol.iterator] property.

> The following example shows the difference between a for...of loop and a for...in loop.

```js
Object.prototype.objCustom = function() {}; 
Array.prototype.arrCustom = function() {};

let iterable = [3, 5, 7];
iterable.foo = 'hello';

for (let i in iterable) {
  console.log(i); // logs 0, 1, 2, "foo", "arrCustom", "objCustom"
}

for (let i of iterable) {
  console.log(i); // logs 3, 5, 7
}
```
