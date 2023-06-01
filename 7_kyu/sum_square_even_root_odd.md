## [Sum - Square Even, Root Odd](https://www.codewars.com/kata/5a4b16435f08299c7000274f/javascript)

- Complete the function that takes a list of numbers (nums), as the only argument to the function. Take each number in the list and square it if it is even, or square root the number if it is odd. Take this new list and return the sum of it, rounded to two decimal places.

- The list will never be empty and will only contain values that are greater than or equal to zero.

Good luck!

#### Solution:

```python
import math
def sum_square_even_root_odd(nums):
    total = 0
    for num in nums:
        if num % 2 == 0:
            total += num ** 2
        else:
            total += math.sqrt(num)
    return round(total, 2)  

print(sum_square_even_root_odd([4, 5, 7, 8, 1, 2, 3, 0])) # 91.61
print(sum_square_even_root_odd([1, 14, 9, 8, 17, 21])) # 272.71
```
