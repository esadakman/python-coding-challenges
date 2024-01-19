## [Sum of Cubes](https://www.codewars.com/kata/59a8570b570190d313000037)

#### DESCRIPTION:

- Write a function that takes a positive integer n, sums all the cubed values from 1 to n (inclusive), and returns that sum.

- Assume that the input n will always be a positive integer.

##### Examples: (Input --> output)

```js
2 --> 9 (sum of the cubes of 1 and 2 is 1 + 8)
3 --> 36 (sum of the cubes of 1, 2, and 3 is 1 + 8 + 27)

```

#### Solution:

```python
def sum_cubes(n):
    return sum((i + 1) ** 3 for i in range(n))

print(sum_cubes(2))  # 9
print(sum_cubes(3))  # 36
```
