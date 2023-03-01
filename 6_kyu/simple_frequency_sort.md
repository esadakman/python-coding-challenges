## [Simple frequency sort](https://www.codewars.com/kata/5a8d2bf60025e9163c0000bc)

- In this kata, you will sort elements in an array by decreasing frequency of elements. If two elements have the same frequency, sort them by increasing value.

#### Examples :

```python
solve([2,3,5,3,7,9,5,3,7]) = [3,3,3,5,5,7,7,2,9]
-- We sort by highest frequency to lowest frequency.
-- If two elements have same frequency, we sort by increasing value.
```

- More examples in test cases.

#### Solution :

```python
def solve(arr):
    counts = {}
    for num in arr:
        counts[num] = counts.get(num, 0) + 1
    return sorted(arr, key=lambda x: (-counts[x], x))

print(solve([1, 2, 3, 0, 5, 0, 1, 6, 8, 8, 6, 9, 1])); # [1,1,1,0,0,6,6,8,8,2,3,5,9]
print(solve([5, 9, 6, 9, 6, 5, 9, 9, 4, 4])); # ,[9,9,9,9,4,4,5,5,6,6]
print(solve([4, 9, 5, 0, 7, 3, 8, 4, 9, 0])); # ,[0,0,4,4,9,9,3,5,7,8]
```