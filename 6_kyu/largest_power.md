## [Largest Value of a Power Less Than a Number](https://www.codewars.com/kata/5e860c16c7826f002dc60ebb/python)

#### Task

- You are given a positive integer `(n)`, and your task is to find the largest number less than `n`, which can be written in the form `a**b`, where `a` can be any non-negative integer and `b` is an integer greater than or equal to `2`. Try not to make the code time out :)

The input range is from `1` to `1,000,000`.

#### Return

- Return your answer in the form `(x, y)` or (`[x, y]`, depending on the language ), where `x` is the value of `a**b`, and `y` is the number of occurrences of `a**b`. By the way ** means ^ or power, so 2 ** 4 = 16. If you are given a number less than or equal to `4`, that is not `1`, return `(1, -1)`, because there is an infinite number of values for it: `1**2, 1**3, 1**4, ...`.
  If you are given `1`, return `(0, -1)`.

#### Example :

```python
 3  -->  (1, -1)  # because it's less than 4
 6  -->  (4, 1)   # because the largest such number below 6 is 4,
                  # and there is only one way to write it: 2**2
65  -->  (64, 3)  # because there are three occurrences of 64: 2**6, 4**3, 8**2
90  -->  (81, 2)  # because the largest such number below 90 is 81,
                  # and there are two ways of getting it: 3**4, 9**2
```

#### Solution:

```python
def largest_power(n):
    if n == 1:
        return (0, -1)
    if n <= 4:
        return (1, -1)

    powers = []
    for i in range(2, int(n**0.5) + 1):
        for j in range(2, n):
            power = i ** j
            if power < n:
                powers.append(power)
            else:
                break

    max_power = max(powers)
    count = powers.count(max_power)
    return (max_power, count)

print(largest_power(3))   # Output: (1, -1)
print(largest_power(6))   # Output: (4, 1)
print(largest_power(65))  # Output: (64, 3)
print(largest_power(90))  # Output: (81, 2)
```
