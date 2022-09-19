
## Flatten

- Write a function that flattens an Array of Array objects into a flat Array. Your function must only do one level of flattening.

```python
flatten [1,2,3] # => [1,2,3] 
flatten [[[1,2,3]]] # => [[1,2,3]]
```

Solution:

```python
def flatten(lst):
    flattened  = []
    for i in lst:
        if type(i) == list:
           flattened .extend(i)
        else:
           flattened .append(i)
    return flattened

print(flatten([1,2,3]))  # => [1,2,3]
print(flatten([[1,2,3],["a","b","c"],[1,2,3]]))  # => [1,2,3,"a","b","c",1,2,3] 
```