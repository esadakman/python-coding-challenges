## Find the unique number

- There is an array with some numbers. All numbers are equal except for one. Try to find it!

##### Example  
```python            
find_uniq([ 1, 1, 1, 2, 1, 1 ]) == 2
find_uniq([ 0, 0, 0.55, 0, 0 ]) == 0.55
``` 
- It’s guaranteed that array contains at least 3 numbers.

- The tests contain some very huge arrays, so think about performance.

Solution:
```python
def find_uniq(arr):
    for n in set(arr):
        if arr.count(n) == 1:
            return n 

print(find_uniq([ 1, 1, 1, 2, 1, 1 ])) # 2
print(find_uniq([ 3, 10, 3, 3, 3 ])) # 10
```