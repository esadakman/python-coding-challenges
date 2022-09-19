## Find the missing letter

- Write a method that takes an array of consecutive (increasing) letters as input and that returns the missing letter in the array.

- You will always get an valid array. And it will be always exactly one letter be missing. The length of the array will always be at least 2.
The array will always contain letters in only one case.
##### Example  
```python            
["a","b","c","d","f"] -> "e"
["O","Q","R","S"] -> "P"
``` 
Solution:
```python
def find_missing_letter(chars): 
    for x,y in zip(chars,chars[1:]):
        if ((ord(x)+1) != (ord(y))) :
            return chr(ord(x)+1)

print(sum_dig_pow(10, 100)) # [89]
```