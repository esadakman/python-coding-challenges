## [String ends with?](https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d/train/python)

- Complete the solution so that it returns true if the first argument(string) passed in ends with the 2nd argument (also a string).

#### Examples:

```Python
solution('abc', 'bc') // returns true
solution('abc', 'd') // returns false
```

#### Solution:

```python
def solution(text, ending):
    return text.endswith(ending)

print(solution("samurai", "ai"))
print(solution("sumo","omo"))
print(solution("samurai", "ra"))
```
