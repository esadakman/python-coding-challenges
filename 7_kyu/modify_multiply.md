## [Multiply Word in String](https://www.codewars.com/kata/5ace2d9f307eb29430000092)

- You are to write a function that takes a string as its first parameter. This string will be a string of words.

- You are expected to then use the second parameter, which will be an integer, to find the corresponding word in the given string. The first word would be represented by 0.

- Once you have the located string you are finally going to multiply by it the third provided parameter, which will also be an integer. You are additionally required to add a hyphen in between each word.

```python
modify_multiply ("This is a string",3,5) 
=> "string-string-string-string-string"
```
- Since the 3rd word is 'string'(starting from 0 remember) and the third paramater indicates that it should be repeated 5 times.

Solution:

```python
def modify_multiply(st, loc, num):
    words=st.split(" ")
    return ((words[loc]+"-")*num)[:-1] 

print(modify_multiply("This is a string",3 ,5)) # "string-string-string-string-string"
 
```