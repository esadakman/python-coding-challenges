## [Triangular Treasure](https://www.codewars.com/kata/525e5a1cb735154b320002c8/python)

- Triangular numbers are so called because of the equilateral triangular shape that they occupy when laid out as dots. i.e.

#### Examples:

```python
1st (1)   2nd (3)    3rd (6)
*          **        ***
           *         **
                     *
```

- You need to return the nth triangular number. You should return 0 for out of range values:

#### For example: (Input --> Output)

```python
0 --> 0
2 --> 3
3 --> 6
-10 --> 0
```

#### Solution:

```python
def triangular(n):
    return n * (n + 1) // 2 if n > 0 else 0

print(triangular(0))    # Output: 0
print(triangular(2))    # Output: 3
print(triangular(3))    # Output: 6
print(triangular(-10))  # Output: 0

```
