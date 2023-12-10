## [nth Floyd line](https://www.codewars.com/kata/5b096efeaf15bef812000010)

- The [Floyd's triangle](https://en.wikipedia.org/wiki/Floyd%27s_triangle) is a right-angled triangular array of natural numbers listing them in order, in lines of increasing length, so a Floyds triangle of size 6 looks like:

```js
1
2  3
4  5  6
7  8  9  10
11 12 13 14 15
16 17 18 19 20 21
    ...
```

- In this kata you're given a number, and expected to return the line number it falls in, in the Floyd's triangle

#### Examples:

```js
3 -> 2 (i.e the number `3` falls in line 2 of the triangle)
17 -> 6
22 -> 7
499502 -> 1000
```

#### Constraints

- `1 <= n <= 109`

#### Solution:

```python
def nth_floyd(n):
    i = 1
    while n > i:
        n -= i
        i += 1
    return i

# Example usage:
print(nth_floyd(15))  # Output: 5
print(nth_floyd(26))  # Output: 7
print(nth_floyd(17))  # Output: 6
```
