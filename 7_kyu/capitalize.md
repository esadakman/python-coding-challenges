## [Indexed capitalization](https://www.codewars.com/kata/59cfc09a86a6fdf6df0000f1)

- Given a string and an array of integers representing indices, capitalize all letters at the given indices.

```python
capitalize("abcdef",[1,2,5]) = "aBCdeF"
capitalize("abcdef",[1,2,5,100]) = "aBCdeF". There is no index 100.
```

- The input will be a lowercase string with no spaces and an array of digits.

Solution:

```python
def capitalize(s, ind):
    letters = list(s)
    length = len(s)
    for i in ind:
        if i < length:
            letters[i] = letters[i].upper()
    return ''.join(letters)


print(capitalize("abcdef",[1,2,5])) # "aBCdeF"
print(capitalize("abcdef",[1,2,5,100])) # "aBCdeF". There is no index 100.
```