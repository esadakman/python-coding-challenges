## [Stop gninnipS My sdroW!](https://www.codewars.com/kata/5264d2b162488dc400000001)

- Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed. 
- Strings passed in will consist of only letters and spaces. 
- Spaces will be included only when more than one word is present.

Examples:

```python
spin_words( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" 
spin_words( "This is a test") => returns "This is a test" 
spin_words( "This is another test" )=> returns "This is rehtona test"
```
Solution 1:

```python
def spin_words(sentence):
    results = []
    for x in sentence.split(" "): 
        if len(x) >= 5: 
            results.append(x[::-1])
        else:
            results.append(x)
    return " ".join(results)

print(spin_words("Hey fellow warriors"))  # "Hey wollef sroirraw"
```
Solution 2:

```python
def spin_words(sentence):
    return " ".join([x[::-1] if len(x) >= 5 else x for x in sentence.split(" ")])

print(spin_words("This is another tes"))  # "This is rehtona test"
```