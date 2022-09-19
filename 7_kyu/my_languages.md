## My Language Skills

- You are given a dictionary/hash/object containing some languages and your test results in the given languages. Return the list of languages where your test score is at least 60, in descending order of the results.

```python
{"Java": 10, "Ruby": 80, "Python": 65}    #  ["Ruby", "Python"] 
{"C++": 50, "ASM": 10, "Haskell": 20}     #  []
```

Solution:

```python
def my_languages(results): 
    res = [] 
    for k, v in sorted(results.items(), key=lambda x: x[1], reverse=True):
        if (v>=60):
            res.append(k) 
    return res 
 
print(my_languages({"Hindi": 60, "Dutch" : 93, "Greek": 71}  )) #  ["Dutch", "Greek", "Hindi"] 
```