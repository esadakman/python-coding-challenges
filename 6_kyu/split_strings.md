## Split Strings 
- Complete the solution so that it splits the string into pairs of two characters. If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('_').

- Your task is to return the number of zero sequences if the given array is zero-plentiful, oherwise 0.
##### Example  
```python            
* 'abc' =>  ['ab', 'c_']
* 'abcdef' => ['ab', 'cd', 'ef']
``` 
Solution:
```python
import re
def solution(arr): 
    arr = arr+'_' if len(arr)%2 != 0 else arr 
    return re.findall('..?', arr)
  
print(solution(("asdfadsf"))) # ['as', 'df', 'ad', 'sf']
print(solution(("asdfads"))) # ['as', 'df', 'ad', 's_'] 
print(solution(("x"))) # 2 ['x_]
```