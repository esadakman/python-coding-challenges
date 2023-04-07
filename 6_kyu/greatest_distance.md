## [Greatest Position Distance Between Matching Array Values](https://www.codewars.com/kata/5442e4fc7fc447653a0000d5/python)

- The goal of this Kata is to return the greatest distance of index positions between matching number values in an array or 0 if there are no matching values.

- Example: In an array with the values [0, 2, 1, 2, 4, 1] the greatest index distance is between the matching '1' values at index 2 and 5. Executing greatestDistance against this array would return 3. (i.e. 5 - 2)

Here's the previous example in test form:

#### Example:

```python
test.assert_equals(greatest_distance([0, 2, 1, 2, 4, 1]), 3)
```

#### Solution:

```python
def greatest_distance(data):
    res = []
    for i in range(len(data)):
        for j in range(len(data)):
            if data[i] == data[j]:
                res.append(abs(i-j))
    return max(res)

print(greatest_distance([9, 7, 1, 2, 3, 7, 0, -1, -2])) # 4
print(greatest_distance([0, 7, 0, 2, 3, 7, 0, -1, -2])) # 6
print(greatest_distance([1, 2, 3, 4])) # 0
print(greatest_distance([1, 2, 3, 4, 5, 3])) # 3
```
