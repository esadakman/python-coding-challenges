## [Maximum subarray sum](https://www.codewars.com/kata/54521e9ec8e60bc4de000d6c)

- The maximum sum subarray problem consists in finding the maximum sum of a contiguous subsequence in an array or list of integers:

```python
max_sequence([-2, 1, -3, 4, -1, 2, 1, -5, 4]);
# should be 6: [4, -1, 2, 1]
```

- Easy case is when the list is made up of only positive numbers and the maximum sum is the sum of the whole array. If the list is made up of only negative numbers, return 0 instead.

- Empty list is considered to have zero greatest sum. Note that the empty list or array is also a valid sublist/subarray.

#### Solution:

```python

def max_sequence(arr):
    ans = 0
    sum = 0

    for i in range(len(arr)):
        ans = max(0, ans + arr[i])
        sum = max(sum, ans)

    return sum


print(max_sequence([]))  # 0
print(max_sequence([-2, 1, -3, 4, -1, 2, 1, -5, 4]))  # 6

```
