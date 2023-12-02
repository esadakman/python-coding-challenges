## [Wilson primes](https://www.codewars.com/kata/55dc4520094bbaf50e0000cb)

- [Wilson primes](https://en.wikipedia.org/wiki/Wilson_prime) satisfy the following condition. Let P represent a prime number.

- Then,

```js
((P-1)! + 1) / (P * P)
```

should give a whole number.

- Your task is to create a function that returns true if the given number is a Wilson prime.

#### Solution:

```python
def am_i_wilson(n):
      return n == 5 or n == 13 or n == 563


print(am_i_wilson(5)) # true
print(am_i_wilson(9)) # false
print(am_i_wilson(6)) # false
```
