## Hexadecimal Conversision Using Stack

### Decimal to Binary
```python
def int_to_bin(num):
    stack = []
    result = []

    if num == 0:
        return 0

    while num:
        stack.append(num % 2)
        num //= 2
    
    while len(stack):
        result.append(stack.pop())

    return int("".join(result))
```

### Decimal to Any Base

```python
def int_to_anybase(num, base):
    stack = []
    result = []

    if num == 0:
        return 0

    while num:
        stack.append(num % base)
        num //= base
    
    while len(stack):
        result.append(stack.pop())

    return int("".join(result))
```
