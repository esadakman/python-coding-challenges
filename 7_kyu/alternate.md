## [Length and two values.](https://www.codewars.com/kata/62a611067274990047f431a8/train/python)

##### Story

- Given an integer n and two other values, build an array of size n filled with these two values alternating.

#### Examples (input -> output):

```js
5, true, false     -->  [true, false, true, false, true]
10, "blue", "red"  -->  ["blue", "red", "blue", "red", "blue", "red", "blue", "red", "blue", "red"]
0, "one", "two"    -->  []
```

#### Solution:

```js
def alternate(n, first_value, second_value):
    return [first_value if i % 2 == 0 else second_value for i in range(n)]

print(alternate(5, True, False))     # [True, False, True, False, True]
print(alternate(10, "blue", "red"))  # ["blue", "red", "blue", "red", "blue", "red", "blue", "red", "blue", "red"]
print(alternate(0, "one", "two"))    # []
```
