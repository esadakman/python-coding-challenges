## The maximum sum value of ranges -- Simple version 

Description:

##### Example  
```python            
Given arr = [1,-2,3,4,-5,-4,3,2,1], 
       range = [[1,3],[0,4],[6,8]]
 should return 6
 
 calculation process:
 range[1,3] = arr[1]+arr[2]+arr[3] = 5
 range[0,4] = arr[0]+arr[1]+arr[2]+arr[3]+arr[4] = 1
 range[6,8] = arr[6]+arr[7]+arr[8] = 6
 So the maximum sum value is 6
``` 
- Note:
    - arr/$a always has at least 5 elements;
    - range/$range/ranges always has at least 1 element;
    - All inputs are valid;
    - This is a simple version, if you want some challenge, please try the challenge version.

Solution 1:
```python

def max_sum(arr,ranges):  
    res = sum(arr[(ranges[0][0]):(ranges[0][1]+1)])
    for i,j in ranges: 
        if sum(arr[i:j+1]) > res:
            res = sum(arr[i:j+1]) 
    return res
  
print(max_sum([1,-2,3,4,-5,-4,3,2,1],[[1,3],[0,4],[6,8]])) # 6
print(max_sum([1,-2,3,4,-5,-4,3,2,1],[[1,3]])) # 5
```
Solution 2:
```python
def max_sum(arr,ranges): 
    res = []
    for i,j in ranges: 
        res.append(sum(arr[i:j+1]))
    return max(res)

print(max_sum([1,-2,3,4,-5,-4,3,2,1],[[1,4],[2,5]])) # 0
print(max_sum([11,-22,31,34,-45,-46,35,32,21], [[1,4],[0,3],[6,8],[0,8]])) # 88
```


 