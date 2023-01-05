## [Beginner Series #3 Sum of Numbers](https://www.codewars.com/kata/55f2b110f61eb01779000053) 

- Given two integers a and b, which can be positive or negative, find the sum of all the integers between and including them and return it. If the two numbers are equal return a or b.

Note: a and b are not ordered!

Samples:

```python
(1, 0) --> 1 (1 + 0 = 1)
(1, 1) --> 1 (1 since both are same)
(-1, 0) --> -1 (-1 + 0 = -1)
(-1, 2) --> 2 (-1 + 0 + 1 + 2 = 2)
```

Solution:

```python
def get_sum(a,b):
    result = 0
    if (a < b):
        for i in range(a,b+1):
            result += i
    elif (a > b):
        for i in range(b,a+1):
            result += i
    else:
        return a
    return result

print(get_sum(0,2)) #3
print(get_sum(2,2)) #2
print(get_sum(0,-1)) #-1
```