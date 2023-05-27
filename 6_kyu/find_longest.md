## [The longest bracket substring in the string](https://www.codewars.com/kata/584c3e45710dca21be000088)

- Given a string str consisting of some number of "(" and ")" characters, your task is to find the longest substring in str such that all "(" in the substring are closed by a matching ")". The result is the length of that substring.

#### For example:

```python
"()()(" => 4
Because "()()" is the longest substring, which has a length of 4
```

#### Note:

- All inputs are valid.
- If no such substring found, return 0.
- Please pay attention to the performance of code. ;-)
- In the performance test(100000 brackets str x 100 testcases), the time consuming of each test case should be within 35ms. This means, your code should run as fast as a rocket ;-)

#### Some Examples

```python
find_longest("()()("); // returns 4
find_longest("(()())"); // returns 6
find_longest("())(()))"); // returns 4
find_longest("))(("); // returns 0
```

#### Solution:

```python
def find_longest(s):
    stack = []  # Stack to store indices of opening brackets '('
    lengths = []  # List to store lengths of valid substrings
    base = -1  # base index of valid substrings

    for i in range(len(s)):
        if s[i] == "(":
            stack.append(i)
        elif s[i] == ")":
            if stack:
                stack.pop()
                if stack:
                    lengths.append(i - stack[-1])
                else:
                    lengths.append(i - base)
            else:
                base = i

    return max([0] + lengths)


print(find_longest("()()("))  # prints 4
print(find_longest("(()())"))  # prints 6
print(find_longest("())(()))"))  # prints 4
print(find_longest("))(("))  # prints 0

```
