## Find the Greatest Common Devisor and the Least Common Multiple

The quickest way is the Euclid's approach, which in python will be:

### GCD

```python
def gcd(m, n):
    while m % n != 0:
        m, n = n, m % n 
    return n

gcd(20, 6)  # 2
```

### LCM

Approach one, without leveraging gcd:

```python
def lcm(m, n):
    greater = max(m, n)
    while True:
        if (greater % m == 0) and (greater % n == 0):
            return greater
        else:
            greater += 1
```

Another:

```python
def lcm(m, n):
    return (m * n) // gcd(m, n)
```
