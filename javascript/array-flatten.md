# Array Flatten (Recursion and Iterative)

```js
// recursion
function flattenRe(arr) {
  return arr.reduce((accu, curr) => {
    let next = Array.isArray(curr) ? flattenRe(curr) : curr
    return accu.concat(next)
  }, [])
}

// iterative
function flattenIter(arr) {
  let res = []
  let clone = [...arr]

  while (clone.length) {
    let curr = clone.shift()
    if (Array.isArray(curr)) {
      clone = curr.concat(clone)
    } else {
      res.push(curr)
    }
  }
  return res
}

console.log(flattenRe([1,[[3,4]], [2,3], [[[4], [5]]]]))
console.log(flattenIter([1,[[3,4]], [2,3], [[[4], [5]]]]))
```
