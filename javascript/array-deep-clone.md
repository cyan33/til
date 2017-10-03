# Array Deep Clone

I accidently found that all of the common methods of cloning an array is only shallow copy, which means it goes only one level deep, and clone the reference of each element.

These methods include:

* `[].concat[a]`
* `[...a]`
* `a.slice(0)`

The bug issue looks like this:

```js
var a = [[1,2,3],[4,5,6]]
var b = [...a]

b[0][1] = 99  // this also makes a[0][1] equals to 99
```

So I did some research and found this best method I think:

```js
Array.prototype.clone = () => {
  return this.map(el => {
    return Array.isArray(el) ? el.clone() : el
  })
}
```
