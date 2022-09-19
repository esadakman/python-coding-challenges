## Vowel remover

- Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.
Samples:
```python
"hello" --> "hll"\
"codewars" --> "cdwrs"\
"goodbye" --> "gdby"\
"HELLO" --> "HELLO"
```

- don't worry about uppercase vowels
- y is not considered a vowel for this kata

Solution:

```python

def shortcut( s ):
    vowels = ('a', 'e', 'i', 'o', 'u')
    newStr  = s
    for i in s:
        if i in vowels:
            newStr = newStr.replace(i,"")
    return newStr

print(shortcut("hello")) # hll 
print(shortcut("HELLO")) # HELLO
```