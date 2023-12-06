## [Plus - minus - plus - plus - ... - Sum](https://www.codewars.com/kata/5bc463f7797b00b661000118)

#### Description

- Given an array `[x1, x2, ..., xn]` determine whether it is possible to put `+` or `-` between the elements and get an expression equal to sum. Result is boolean

```js
2 <= n <= 22;
0 <= xi <= 20 - 10 <= sum <= 10;
```

#### Example

`arr = [1, 3, 4, 6, 8]`

`sum = -2`

1 + 3 - 4 + 6 - 8 = -2

Result is: `true`

#### Solution:

```python
def is_possible(list, goal):
    if len(list) == 1:
        return list[0] == goal

    return (
        is_possible(list[1:], goal - list[0]) or
        is_possible(list[1:], list[0] - goal)
    )

print(is_possible([1, 3, 4, 6, 8], -2)) # true
print(is_possible([15, 2, 3], 10)) # true
```
