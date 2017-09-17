# Sorting Algorithms in Python

## Bubble Sort(O(n**2))

```python
def bubble_sort(nums):
    for passnum in range(len(nums) - 1, 0, -1):
        for i in range(passnum):
            if nums[i] > nums[i + 1]:
                nums[i + 1], nums[i] = nums[i], nums[i + 1]
```

However, if the array is already sorted, we still have to go through `n-1` passes, in each of which we have to compare `passnum - 1` times. This is costly. So here is the improved version of the bubble sort. If the array is already sorted, or the sub array is sorted, it will stop before hand.

```python
def short_bubble_sort(nums):
    passnum = len(nums) - 1
    exchanges = True
    while passnum > 0 and exchanges:
        exchanges = False
        for i in range(passnum):
            if nums[i] > nums[i + 1]:
                exchanges = True
                nums[i], nums[i + 1] = nums[i + 1], nums[i]
        passnum -= 1
```

## Selection Sort(O(n**2))

The selection sort improves on bubble sort in a way that it only does one time exchange every pass.

```python
def selection_sort(nums):
    for passnum in range(len(nums) - 1, 0, -1):
        max_position = 0
        for i in range(1, passnum + 1):
            # find the index of the max number from the remaining array
            if nums[i] > nums[max_position]:
                max_position = i
        # exchange the position of the max value and the last value of the array
        nums[passnum], nums[max_position] = nums[max_position], nums[passnum]
```

## Insertion Sort(O(n**2))

```python
def insertion_sort(nums):
    for i in range(1, len(nums)):
        currValue = nums[i]
        position = i

        # calculate the right position to insert current value
        while position > 0 and nums[position - 1] > currValue:
            # right shift if it's bigger than currValue
            nums[position] = nums[position - 1]
            position -= 1
        nums[position] = currValue
```

## Shell Sort()

## Merge Sort(O(nlogn))

The core is the **Divide and Conquer(D&C) algorithm**
```python
def merge_sort(nums):
    if len(nums) > 1:
        # split
        mid = len(nums) // 2
        lefthalf = nums[:mid]
        righthalf = nums[mid:]

        # recursion
        # sort the sub array
        merge_sort(lefthalf)
        merge_sort(righthalf)

        i = 0
        j = 0
        k = 0

        # merge the lefthalf and righthalf
        while i < len(lefthalf) and j < len(righthalf):
            if lefthalf[i] < righthalf[j]:
                nums[k] = lefthalf[i]
                i += 1
            else:
                nums[k] = righthalf[j]
                j += 1
            k += 1

        # in case lefthalf has not been consumed completely
        while i < len(lefthalf):
            nums[k] = lefthalf[i]
            i += 1
            k += 1

        # same reason for righthalf
        while j < len(righthalf):
            nums[k] = righthalf[j]
            j += 1
            k += 1
```

## Quick Sort(O(nlogn)~O(n**2))

```python
def quick_sort(nums):
    if len(nums) > 1:
        pivot = nums[0]

        less = []
        equal = []
        greater = []

        for n in nums:
            if n < pivot:
                less.append(n)
            elif n > pivot:
                greater.append(n)
            else:
                equal.append(n)

        return quick_sort(less) + equal + quick_sort(greater)
    else:
        return nums
```

