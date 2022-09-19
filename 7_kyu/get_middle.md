## Get the Middle Character

- You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.

```python
get_middle("test") should return "es"
get_middle("testing") should return "t"
get_middle("middle") should return "dd"
get_middle("A") should return "A"
```

Solution:

```python
def get_middle(s):
    middle = len(s)/2
    if (float(middle) == int(middle)):
        return (s[int(middle)-1:int(middle)+1])
    else:
        return (s[int(middle)])

print(get_middle("test")) # "es" 
print(get_middle("A")) # "A"
```