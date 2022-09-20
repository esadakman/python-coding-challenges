## Make the Deadfish Swim 

- Write a simple parser that will parse and run Deadfish.

- Deadfish has 4 commands, each 1 character long:
  - i increments the value (initially 0)
  - d decrements the value
  - s squares the value
  - o outputs the value into the return array
- Invalid characters should be ignored.

##### Example  
```python            
parse("iiisdoso")  ==>  [8, 64]
``` 
Solution:
```python
def parse(data):
    res = []
    current = 0
    for i in data:
        if i == 'i':
            current += 1
        elif i == 'd':
            current -= 1
        elif i == 's':
            current *= current
        elif i == 'o':
            res.append(current)
        else:
            continue
    return res

print(parse("ooo")) #[0, 0, 0]
```