## [Sum Factorial](https:#www.codewars.com/kata/56b0f6243196b9d42d000034/python)

- Factorials are often used in probability and are used as an introductory problem for looping constructs. In this kata you will be summing together multiple factorials.

- Here are a few examples of factorials:

#### Samples:

```python
4 Factorial = 4! = 4 * 3 * 2 * 1 = 24

6 Factorial = 6! = 6 * 5 * 4 * 3 * 2 * 1 = 720
```

- In this kata you will be given a list of values that you must first find the factorial, and then return their sum.

- For example if you are passed the list `[4, 6]` the equivalent mathematical expression would be `4! + 6!` which would equal `744`.

##### Good Luck!

Note: Assume that all values in the list are positive integer values > 0 and each value in the list is unique.

#### Solution:

```python
def sum_factorial(lst):
    result = 0
    for num in lst:
        product = 1
        for i in range(num, 1, -1):
            product *= i
        result += product
    return result


print(sum_factorial([4,6])) # 744
print(sum_factorial([5,4,1])) # 145
```