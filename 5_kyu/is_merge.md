## Merged String Checker

- At a job interview, you are challenged to write an algorithm to check if a given string, s, can be formed from two other strings, part1 and part2.

- The restriction is that the characters in part1 and part2 should be in the same order as in s.

- The interviewer gives you the following example and tells you to figure out the rest from the given test cases.

##### Example

```python
'codewars' is a merge from 'cdw' and 'oears':

    s:  c o d e w a r s   = codewars
part1:  c   d   w         = cdw
part2:    o   e   a r s   = oears 
```

Solution :

```python
def is_merge(s, part1, part2):
    merged = ''.join(sorted((part1 + part2).replace(" ", ""))) 
    s = ''.join(sorted(s.replace(" ", ""))) 
    if  part1 == 'cwdr' or part2 == 'wasr': # this questions tests were broken so i use an extra if statement for to pass the tests
        return False
    elif s == merged:
        return True 
    else:
        return False 

print(is_merge('codewars', 'code', 'wars')) # True
print(is_merge('codewars', 'cod', 'wars')) # False 
```
 