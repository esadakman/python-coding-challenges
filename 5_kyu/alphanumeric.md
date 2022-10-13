## Not very secure

- In this example you have to validate if a user input string is alphanumeric. The given string is not nil/null/NULL/None, so you don't have to check that.

- The string has the following conditions to be alphanumeric:
    - At least one character ("" is not valid)
    - Allowed characters are uppercase / lowercase latin letters and digits from 0 to 9
    - No whitespaces / underscore

Solution:
```python
def alphanumeric(password):
    return " " not in password and len([i for i in password if i.isdigit() or i.isalpha()]) == len(password) and len(password) > 0

print(alphanumeric("hello world_")) # False 
print(alphanumeric("PassW0rd" )) # True 
``` 