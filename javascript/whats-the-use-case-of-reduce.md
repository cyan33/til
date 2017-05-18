# What's the Use Cases of Reduce

I've long been confused about the function `Array.prototype.reduce`. Because I don't use it often in my development work flow. But from time to time, I see people taking advantage of it to implement some fancy stuff. So this time I tried considerable time in it and finally figured out the what, why and how. And at last, I will give you a relatively complicated problem which could be solved using `reduce`.

## Use Cases(What and Why)

Let's first go through quickly what is the typical use cases of `reduce`:

The answer is short: Every time you want to take into ACCUMULATION into consideration and you want a single value as your result.

An example: there is an array `[1, 2, 3, 4, 5]`, and you want to calculate the sum of it. Here it's very much different from `forEach`. `forEach` loops through every single element in the array, but loses its memory of the previous calculation result, or what are the former element. But here you want to add every next element to the sum of the previous elements, which is, the ACCUMULATION as I talked about earlier.

## How

Then let's look at MDN explanation about `reduce` to know how to use it in a proper way.

> The reduce() method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.

Here we skip the syntax part of `reduce`, refer to this about that: [Array.Prototype.reduce | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=example)

If you are not familiar with `reduce`, make sure you finish reading **EVERY SINGLE WORD AND EXAMPLE** of the MDN document first.

## Quiz

Now that you get familiar with `reduce`, let's work this out:

```js
const add = (a, b) => a + b;
const square = a => a * a;
const plusOne = a => a + 1;

const addSquareAndPlusOne = composite(add, square, plusOne);
addSquareAndPlusOne(1, 2) // ==> 10
```

solution:
```js
const composite = (...args) => {
  // [add, square, plusOne]
  return (...arguments) => {
    // [1, 2]
    return args.reduce((accu, curr) => {
      return curr(typeof accu === 'function' ? accu.apply(accu, arguments) : accu)
    })
  }
}
```

Thanks for @loatheb for this awesome solution!
