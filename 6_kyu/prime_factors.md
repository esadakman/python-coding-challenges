## [Prime Factors](https://www.codewars.com/kata/542f3d5fd002f86efc00081a/python)

#### Prime Factors

- Inspired by one of Uncle Bob's TDD Kata

- Write a function that generates factors for a given number.

- The function takes an integer as parameter and returns a list of integers (ObjC: array of NSNumbers representing integers). That list contains the prime factors in numerical sequence.

#### Examples:

```js
1  ==>  []
3  ==>  [3]
8  ==>  [2, 2, 2]
9  ==>  [3, 3]
12 ==>  [2, 2, 3]
```

#### Solution:

```python
def prime_factors(n):
    factors = []
    divisor = 2

    while n > 1:
        if n % divisor == 0:
            factors.append(divisor)
            n = n / divisor
        else:
            divisor += 1

    return factors

print(prime_factors(1))   # Output: []
print(prime_factors(3))   # Output: [3]
print(prime_factors(8))   # Output: [2, 2, 2]
print(prime_factors(9))   # Output: [3, 3]
print(prime_factors(12))  # Output: [2, 2, 3]

```
