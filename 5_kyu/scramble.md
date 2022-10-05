## Scramblies

- Complete the function scramble(str1, str2) that returns true if a portion of str1 characters can be rearranged to match str2, otherwise returns false.

Notes:

- Only lower case letters will be used (a-z). No punctuation or digits will be included.
- Performance needs to be considered.

Examples:
```js
scramble('rkqodlw', 'world') ==> True 
scramble('katas', 'steak') ==> False
```
Solutions:
```python
def scramble(s1, s2):
    for i in set(s2):
        if s1.count(i) < s2.count(i):
            return False
    return True
print(scramble('cedewaraaossoqqyt', 'codewars')); # true  
print(scramble('katas', 'steak')) # False
```