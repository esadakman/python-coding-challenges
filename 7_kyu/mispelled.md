## [Mispelled word](https://www.codewars.com/kata/5892595f190ca40ad0000095/python)

- Create a function mispelled(word1, word2):

##### Example

```python
mispelled('versed', 'xersed'); # returns true
mispelled('versed', 'applb'); # returns false
mispelled('versed', 'v5rsed'); # returns true
mispelled('1versed', 'versed'); # returns true
mispelled('versed', 'versed'); # returns true
```

- It checks if the word2 differs from word1 by at most one character.

- This can include an extra char at the end or the beginning of either of words.

- In the tests that expect `true`, the mispelled word will always differ mostly by one character. If the two words are the same, return `True`.



#### Solution:

```python
def mispelled(word1, word2):
    if word1 == word2:
        return True

    if abs(len(word1) - len(word2)) > 1:
        return False

    count = 0
    i, j = 0, 0
    while i < len(word1) and j < len(word2):
        if word1[i] != word2[j]:
            count += 1
            if len(word1) > len(word2):
                j -= 1
            elif len(word1) < len(word2):
                i -= 1
        i += 1
        j += 1

    return count < 2


print(mispelled('1versed', 'versed')) # True
print(mispelled('aaversed', 'versed')) # False
print(mispelled('versed', 'aversed')) # True
```