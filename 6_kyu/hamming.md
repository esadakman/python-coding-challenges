## [Hamming Distance](https://www.codewars.com/kata/5410c0e6a0e736cf5b000e69/python)

- The Hamming Distance is a measure of similarity between two strings of equal length. Complete the function so that it returns the number of positions where the input strings do not match.

#### Samples:

```python
a = "I like turtles"
b = "I like turkeys"
Result: 3

a = "Hello World"
b = "Hello World"
Result: 0

a = "espresso"
b = "Expresso"
Result: 2
``` 

- You can assume that the two input strings are of equal length.

#### Solution:

```python
def hamming(a, b):
    counter = 0
    for i in range(len(a)):
        if a[i] != b[i]:
            counter += 1 
    return counter 


print(hamming("a man a plan a canal", "a man a plan sobanal"))  # 3
print(hamming("Hello World", "Hello World"))  # 0
print(hamming("old father, old artificer", "of my soul the uncreated "))  # 24
```
