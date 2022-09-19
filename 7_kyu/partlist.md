## Parts of a list

Write a function partlist that gives all the ways to divide a list (an array) of at least two elements into two non-empty parts.

- Each two non empty parts will be in a pair  
- Each part will be in a string
- Elements of a pair must be in the same order as in the original array.

```python
print(partlist(["I", "wish", "I", "hadn't", "come"])) 
#  [("I", "wish I hadn't come"), ("I wish", "I hadn't come"), ("I wish I", "hadn't come"), ("I wish I hadn't", "come")]) 
```

Solution:

```python
def partlist(arr):
    tuples = []
    for i in range(len(arr)):
        a = ' '.join(arr[:i])
        b = ' '.join(arr[i:])
        tuples.append((a,b)) 
        
    return tuples[1:]

print(partlist(["cdIw", "tzIy", "xDu", "rThG"])) 
# [("cdIw", "tzIy xDu rThG"), ("cdIw tzIy", "xDu rThG"), ("cdIw tzIy xDu", "rThG")] 
print(partlist(["vJQ", "anj", "mQDq", "sOZ"])) 
# [("vJQ", "anj mQDq sOZ"), ("vJQ anj", "mQDq sOZ"), ("vJQ anj mQDq", "sOZ")]
```