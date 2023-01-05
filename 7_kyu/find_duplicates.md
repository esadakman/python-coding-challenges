## [Find Duplicates](https://www.codewars.com/kata/5558cc216a7a231ac9000022)

- Given an array, find the duplicates in that array, and return a new array of those duplicates. The elements of the returned array should appear in the order when they first appeared as duplicates.

Note: numbers and their corresponding string representations should not be treated as duplicates (i.e., "1" != 1).

Samples:

```python
[1, 2, 4, 4, 3, 3, 1, 5, 3, "5"]  ==>  [4, 3, 1]
[0, 1, 2, 3, 4, 5]                ==>  []
```

Solution:

```python
def duplicates(array):
    dupli = []
    arr = []
    for i in array:
        if i in arr:
            if i not in dupli:
                dupli.append(i)
        else:
            arr.append(i)
    return dup

print(duplicates([1, 2, 4, 4, 3, 3, 1, 5, 3, '5'])) # [4, 3, 1]
print(duplicates([0, 1, 2, 3, 4, 5])) # []
```