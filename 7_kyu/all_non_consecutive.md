## [Find all non-consecutive numbers](https://www.codewars.com/kata/58f8b35fda19c0c79400020f)

- Your task is to find all the elements of an array that are non consecutive.
- A number is non consecutive if it is not exactly one larger than the previous element in the array. The first element gets a pass and is never considered non consecutive.

- Create a function named `all_non_consecutive`

- E.g., if we have an array `[1,2,3,4,6,7,8,15,16]` then `6` and `15` are non-consecutive.

- You should return the results as an array of objects with two values `i: <the index of the non-consecutive number>` and `n: <the non-consecutive number>`.

E.g., for the above array the result should be:

```python
[
  { i: 4, n: 6 },
  { i: 7, n: 15 },
];
```

- If the whole array is consecutive or has one element then return an empty array.

- The array elements will all be numbers. The numbers will also all be unique and in ascending order. The numbers could be positive and/or negetive and the gap could be larger than one.

#### Solution:

```python
def all_non_consecutive(arr):
    res = []
    for i in range(len(arr)-1):
        if arr[i+1] - 1 != arr[i]:
            res.append({'i': i+1, 'n': arr[i+1]})
    return res

print(all_non_consecutive([1, 2, 3, 4, 6, 7, 8, 10])); # {i: 4, n:6}, {i: 7, n:10}
```
