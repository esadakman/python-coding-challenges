## Evens times last 

- Given a sequence of integers, return the sum of all the integers that have an even index (odd index in COBOL), multiplied by the integer at the last index.
- Indices in sequence start from 0.
- If the sequence is empty, you should return 0.

```python
([2, 3, 4, 5])  ==> 30
([])  ==> 0
```

Solution:

```python
def even_last(numbers):
    sum = 0
    if len(numbers) == 0:
        return 0
    else:
        for i in range(len(numbers)):
            if i % 2 == 0:
                sum += numbers[i]
    return sum*numbers[-1]

print(even_last([2, 3, 4, 5])) # 30
print(even_last([])) # 0

```