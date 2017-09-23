# Find All Divisors
```python
import math
def findAllDivisors(num):
    divisors = set([1])
    for i in range(2, int(math.sqrt(num)) + 1):
        if num % 2 == 0:
            divisors.add(i)
            divisors.add(num // i)
    return divisors
```
