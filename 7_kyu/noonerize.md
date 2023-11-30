## [Noonerize Me](https://www.codewars.com/kata/56dbed3a13c2f61ae3000bcd)


- Spoonerize... with numbers... numberize?... numboonerize?... noonerize? ...anyway! If you don't yet know what a spoonerism is and haven't yet tried my spoonerism kata, please do check it out first.

- You will create a function which takes an array of two positive integers, spoonerizes them, and returns the positive difference between them as a single number or 0 if the numbers are equal:

```js
[123, 456] = 423 - 156 = 267
```
- Your code must test that all array items are numbers and return "invalid array" if it finds that either item is not a number. The provided array will always contain 2 elements.

- When the inputs are valid, they will always be integers, no floats will be passed. However, you must take into account that the numbers will be of varying magnitude, between and within test cases.

#### Solution:

```python
def noonerize(numbers):
    if not all(isinstance(num, int) for num in numbers):
        return "invalid array"

    num1, num2 = map(str, numbers)
    return abs(int(num2[0] + num1[1:]) - int(num1[0] + num2[1:]))

print(noonerize([12, 34]))  # 18
print(noonerize([357, 579]))  # 12
print(noonerize([1000000, 9999999]))  # 7000001
print(noonerize(["not", "numbers"]))  # "invalid array"
```
