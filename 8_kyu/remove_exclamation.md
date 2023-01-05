## [Remove exclamation marks](https://www.codewars.com/kata/57a0885cbb9944e24c00008e)

- Write function RemoveExclamationMarks which removes all exclamation marks from a given string.
- Return the sum of all the scores on the record._

#### Samples:
```python
 Input: str = ("Hello World!") // Output: Hello World
 Input: str = ("Hello World!!!") // Output: Hello World
```

#### Solution:
```python
def remove_exclamation_marks(str):

    return str.replace("!", "")

print(remove_exclamation_marks("Hello World!")) #Hello World
print(remove_exclamation_marks("Hello World!!!!")) #Hello World
```