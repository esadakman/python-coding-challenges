## [Mysterious Singularity Numbers](https://www.codewars.com/kata/6409aa6df4a0b773ce29cc3d/python)

#### Task

- The point is that a natural number N (1 <= N <= 10^9) is given. You need to write a function which finds the number of natural numbers not exceeding N and not divided by any of the numbers [2, 3, 5].

#### Example

- Let's take the number 5 as an example:
  - 1 - doesn't divide integer by 2, 3, and 5
  - 2 - divides integer by 2
  - 3 - divides integer by 3
  - 4 - divides integer by 2
  - 5 - divides integer by 5

#### Answer

- Answer: 1
- because only one number doesn't divide integer by any of 2, 3, 5

#### Solution:

```python
def real_numbers(n):
    return n - sum(n // x for x in [2, 3, 5]) + sum(n // x for x in [6, 10, 15]) - (n // 30)

print(real_numbers(75)); # 20
```
