## [Reverse every other word in the string](https://www.codewars.com/kata/58d76854024c72c3e20000de)
- Reverse every other word in a given string, then return the string. Throw away any leading or trailing whitespace, while ensuring there is exactly one space between each word. Punctuation marks should be treated as if they are a part of the word in this kata.

Solution 1:
```python 
def reverse_alternate(string):  
    return ' '.join(word[::-1] if i % 2 != 0 else word for i, word in enumerate(string.split()))

print(reverse_alternate("Did it work?")) # "Did ti work?"
print(reverse_alternate("I really hope it works this time...")) # "I yllaer hope ti works siht time..." 

```
Solution 2:

```python 
def reverse_alternate(string):
    string = string.split()
    res = []
    for i in range(len(string)):
        if (i+1) % 2 == 0:
            res.append(string[i][::-1])
        else :
            res.append(string[i])
    return " ".join(res)
 
print(reverse_alternate("Reverse this string, please!")) # "Reverse siht string, !esaelp"
print(reverse_alternate("Have a beer")) # "Have a beer"
```
 