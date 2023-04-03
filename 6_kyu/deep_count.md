## [Array Deep Count](https://www.codewars.com/kata/596f72bbe7cd7296d1000029/python)

- You are given an array. Complete the function that returns the number of ALL elements within an array, including any nested arrays.

##### Example

```python
[]                   -->  0
[1, 2, 3]            -->  3
["x", "y", ["z"]]    -->  4
[1, 2, [3, 4, [5]]]  -->  7
```

#### Solution:

```python
def deep_count(a):
    count = len(a)
    for item in a:
        if isinstance(item, list):
            count += deep_count(item)
    return count

print(deep_count([])); # 0
print(deep_count([1, 2, 3])); # 3
print(deep_count([[[[[[[[[]]]]]]]]])); # 8
```