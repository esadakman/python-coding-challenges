## [Find The Parity Outlier](https://www.codewars.com/kata/5526fc09a1bbd946250002dc)

- You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier" `N`.

##### Example

```python
[2, 4, 0, 100, 4, 11, 2602, 36]
Should return: 11 (the only odd number)

[160, 3, 1719, 19, 11, 13, -21]
Should return: 160 (the only even number)
```
 

Solution:

```python
def find_outlier(integers):
    parity = [n % 2 for n in integers]
    return integers[parity.index(1)] if sum(parity) == 1 else integers[parity.index(0)]
    
print(find_outlier([2, 4, 0, 100, 4, 11, 2602, 36])) # 11
print(find_outlier([160, 3, 1719, 19, 11, 13, -21])) # 160
```