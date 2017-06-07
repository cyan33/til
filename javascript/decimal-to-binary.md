# Decimal to Binary

## The Quickest Way (Using the Native API)

```js
function decimalToBinary(x) {
  return parseInt(x.toString(2))  // 8 -> 1000
}

function binaryToDecimal(x) {
  return parseInt(x, 2) // 2 is the base
}
```

## The Normal Way

```js
function toBinary(num, base) {
  var stack = [],
      converted = ""

  while (num > 0) {
    stack.push(num % base)  // push the remainder into the stack
    num = Math.floor(num /= base) // reset the num to the quotient
  }
  
  // we could also do: return parseInt(stack.reverse().join())
  // but here we use the stack data structure
  while(stack.length > 0) {
    converted += stack.pop()
  }
  return parseInt(converted)
}

toBinary(9, 2)  // 1001
```