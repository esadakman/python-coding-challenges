## [Remove the parentheses](https://www.codewars.com/kata/5f7c38eb54307c002a2b8cc8/python)

- In this kata you are given a string for example:

```js
"example(unwanted thing)example"
```

- Your task is to remove everything inside the parentheses as well as the parentheses themselves.

- The example above would return:

```python
"exampleexample"
```

#### Notes
- Other than parentheses only letters and spaces can occur in the string. Don't worry about other brackets like `"[]"` and `"{}"` as these will never appear.
- There can be multiple parentheses.`
- The parentheses can be nested.

#### Solution:
```python
def remove_parentheses(s):
    stack = []
    result = ""

    for c in s:
        if c == "(":
            stack.append(c)
        elif c == ")":
            stack.pop()
        elif not stack:
            result += c

    return result

print(remove_parentheses("example (unwanted thing) example")); # "example  example"
print(remove_parentheses("a (bc d)e")); # "a e"
print(remove_parentheses("ello example (words(more words) here) something")); # "hello example  something"
```