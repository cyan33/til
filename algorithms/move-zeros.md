# Move Zeros

```js
// two pointers
// [0, 3, 5, 0, 12]
function moveZeroes(nums) {
  let zero = 0  // zero is the pointer which points to the left-most 0
  for (let i = 0; i < nums.length; i++) {
    if (nums[i] !== 0) {
      [nums[i], nums[zero]] = [nums[zero], nums[i]]
      zero++
    }
  }
}
```