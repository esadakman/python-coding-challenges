## [Character with longest consecutive repetition](https://www.codewars.com/kata/586d6cefbcc21eed7a001155)

- For a given string `s` find the character `c` (or `C`) with longest consecutive repetition and return:

```python
[c, l];
```

- where `l` (or `L`) is the length of the repetition. If there are two or more characters with the same `l` return the first in order of appearance.

- For empty string return:

```python
["", 0];
```

In <b>JavaScript:</b> If you use `Array.sort` in your solution, you might experience issues with the random tests as `Array.sort` is not stable in the Node.js version used by CodeWars. This is not a kata issue.

##### Task

- In this simple Kata your task is to create a function that turns a string into a Mexican Wave. You will be passed a string and you must return that string in an array where an uppercase letter is a person standing up.

#### Solution :

```python 
def longest_repetition(chars):
    if len(chars) == 0:
        return ("",0)
    else:
        res = ""
        for i in range(len(chars)):
            if i == 0:
                res = chars[i]
            elif res[-1] == chars[i]:
                res = res + chars[i]
            else:
                res = res + " " + chars[i]
        res = sorted(res.split(" "), reverse=True, key=len)    
        return (*set(res[0]),len(res[0]))

print(longest_repetition("aaaabb")); # ["a",4]
print(longest_repetition("bbbaaabaaaa")); # ["a",4]
print(longest_repetition("cbdeuuu900")); # ["u",3]
print(longest_repetition("")); # ["",0]
```