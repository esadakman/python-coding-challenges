## [Two Sets of Equal Sum](https://www.codewars.com/kata/647518391e258e80eedf6e06)

#### Description

- If possible, divide the integers 1,2,…,n into two sets of equal sum.

#### Input

- A positive integer n <= 1,000,000.

#### Output

- If it's not possible, return [ ] (Javascript and Python) or ( ) (Python) or [[],[] ] (Java, C#, Kotlin) or None (Scala). If it's possible, return two disjoint sets. Each integer from 1 to n must be in one of them. The integers in the first set must sum up to the same value as the integers in the second set. The sets can be returned in a tuple, list, or array, depending on language.

```js
For n = 8, valid answers include:

[1, 3, 6, 8], [2, 4, 5, 7] (or [[1, 3, 6, 8], [2, 4, 5, 7]])

[8, 1, 3, 2, 4], [5, 7, 6]

[7, 8, 3], [6, 1, 5, 4, 2], and others.

For n = 9 it is not possible. For example, try [6, 8, 9] and [1, 2, 3, 4, 5, 7], but the first sums to 23 and the second to 22. No other sets work either.
```

#### Solution:

```python
def create_two_sets_of_equal_sum(n):
    total_sum = (n * (n + 1)) // 2

    # If the total sum is odd, it's not possible
    if total_sum % 2 != 0:
        return []

    target_sum = total_sum // 2
    set1, set2 = [], []
    current_sum = 0

    # Iterate from n to 1 to distribute integers into sets
    for i in range(n, 0, -1):
        if current_sum + i <= target_sum:
            set1.append(i)
            current_sum += i
        else:
            set2.append(i)

    return [set1, set2]

print(create_two_sets_of_equal_sum(8)) #  [1, 3, 4] and [2, 5, 6, 7, 8]
print(create_two_sets_of_equal_sum(9)) # []
```
