## Highest and Lowest

- In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

```python
high_and_low("1 2 3 4 5")  # return "5 1"
high_and_low("1 2 -3 4 5") # return "5 -3"
high_and_low("1 9 3 4 -5") # return "9 -5"
```

Solution:

```python
def high_and_low(numbers):
    num = [int(x) for x in numbers.split(' ')]
    return "{} {}".format(max(num), min(num))
 
print(high_and_low("1 9 3 4 -5") ) # return "9 -5"
```