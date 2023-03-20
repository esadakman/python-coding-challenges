## [Remove String Spaces](https://www.codewars.com/kata/57eae20f5500ad98e50002c5/python)

- Write a function that removes the spaces from the string, then return the resultant string.

#### Examples:

```python
Input -> Output
"8 j 8   mBliB8g  imjB8B8  jl  B" -> "8j8mBliB8gimjB8B8jlB"
"8 8 Bi fk8h B 8 BB8B B B  B888 c hl8 BhB fd" -> "88Bifk8hB8BB8BBBB888chl8BhBfd"
"8aaaaa dddd r     " -> "8aaaaaddddr"
```

#### Solution:

```python
def no_space(x):
    return x.replace(" ", "") 

print(no_space('8 j 8   mBliB8g  imjB8B8  jl  B')); # '8j8mBliB8gimjB8B8jlB'
print(no_space('8aaaaa dddd r     ')); # "8aaaaaddddr"
```