# Decimal to Binary

## The Quickest Way

```js
function decimalToBinary(x) {
  return parseInt(x.toString(2))  // 8 -> 1000
}

function binaryToDecimal(x) {
  return parseInt(x, 2) // 2 is the base
}
```
