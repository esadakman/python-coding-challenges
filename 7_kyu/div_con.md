## [Divide and Conquer](https://www.codewars.com/kata/57eaec5608fed543d6000021/python)

- Given a mixed array of number and string representations of integers, add up the non-string integers and subtract the total of the string integers.

- Return as a number.


Solution:

```python
def div_con(x):
    total_sum = 0
    string_sum = 0
    for elem in x:
        if isinstance(elem, str) and elem.isnumeric():
            string_sum += int(elem)
        elif isinstance(elem, (int, float)):
            total_sum += elem
    return total_sum - string_sum

print(divCon([9, 3, '7', '3'])) # 2
print(divCon(['5', '0', 9, 3, 2, 1, '9', 6, 7])) # 14
print(divCon(['3', 6, 6, 0, '5', 8, 5, '6', 2,'0'])) # 13
```