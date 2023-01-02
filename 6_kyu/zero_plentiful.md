## [Zero-plentiful Array](https://www.codewars.com/kata/59e270da7997cba3d3000041)
- An array is called zero-plentiful if it contains multiple zeros, and every sequence of zeros is at least 4 items long.
- Your task is to return the number of zero sequences if the given array is zero-plentiful, oherwise 0.
##### Example  
```python            
[0, 0, 0, 0, 0, 1]  -->  1 # 1 group of 5 zeros (>= 4), thus the result is 1 
[0, 0, 0, 0, 1, 0]  -->  0  # 1 group of 4 zeros and 1 group of 1 zero (< 4)
``` 
Solution:
```python
def zero_plentiful(arr): 
    result,chain = 0,0
    for x in arr:
        if x == 0:
            chain += 1
        if x != 0:
            if chain < 4 and chain >= 1:
                return 0
            if chain > 3:
                result += 1
            chain = 0
    if chain > 3:
        result += 1
    if chain < 4 and chain >= 1:
        return 0
    return result
  
print(zero_plentiful([0, 0, 0, 0, 1, 0, 0, 0, 0])) # 2
```