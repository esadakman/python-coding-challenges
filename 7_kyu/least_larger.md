## Least Larger

- Given an array of numbers and an index, return either the index of the smallest number that is larger than the element at the given index, or -1 if there is no such index.

Notes:
- Multiple correct answers may be possible. In this case, return any one of them.
- The given index will be inside the given array.
- The given array will, therefore, never be empty.

```python
least_larger( [4, 1, 3, 5, 6], 0 )  # ->  3
least_larger( [4, 1, 3, 5, 6], 4 )  # -> -1
```

Solution:

```python
def least_larger(a, ind):  
    try:
        return a.index(min(i for i in a if i > a[ind]))  
    except ValueError:
        return -1
    
print(least_larger( [4, 1, 3, 5, 6], 0)) # ->  3
print(least_larger( [4, 1, 3, 5, 6], 4)) # ->  -1
print(least_larger( [1, 3, 5, 2, 4], 0)) # ->  3
```