## [Difference of 2](https://www.codewars.com/kata/5a58ca28e626c55ae000018a/javascript)

- The objective is to return all pairs of integers from a given array of integers that have a difference of 2.

- The result array should be sorted in ascending order of values.

- Assume there are no duplicate integers in the array. The order of the integers in the input array should not matter.

#### Samples:

```python
[1, 2, 3, 4]  should return [[1, 3], [2, 4]]
[4, 1, 2, 3]  should also return [[1, 3], [2, 4]]
[1, 23, 3, 4, 7] should return [[1, 3]]
[4, 3, 1, 5, 6] should return [[1, 3], [3, 5], [4, 6]]
```

#### Solution:

```python
def twos_difference(lst):
    return sorted([(x, x + 2) for x in lst if (x + 2) in lst])

print(twosDifference([1, 2, 3, 4])); # [[1,3],[2,4]]
print(twosDifference([1, 3, 4, 6])); # [[1,3],[4,6]]
```