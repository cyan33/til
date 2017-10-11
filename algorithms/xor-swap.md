# XOR Swap Values

Three ways to swap values are:

```py
a, b = b, a
```
,

```py
temp = a
a = b
b = temp
```

and using XOR swap algorithm:

```py
a = a ^ b
b = b ^ a
a = a ^ b
```

Check out the detailed algorithm and explanation here:
https://en.wikipedia.org/wiki/XOR_swap_algorithm
