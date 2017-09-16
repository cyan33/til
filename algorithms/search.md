# Common Search Algorithms in Python

## The Sequential Search

```python
# O(N)
def seqential_search(arr, target):
    i = 0
    while i < len(arr):
        if arr[i] == target:
            return i
        i += 1
    return -1
```

slightly improved version for a sorted array, but still sequential search:

```python
# O(N)
def sequential_search(arr, target):
    i = 0
    while i < len(arr):
        if arr[i] > target:
            return -1
        elif arr[i] == target:
            return i
        i += 1
    return -1
```

## Binary Search

```python
# O(logN)
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    while left < right:
        mid = left + (right - left) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] > target:
            right = mid - 1
        else:
            left = mid + 1
    return -1
```
