## [Replace letters](https://www.codewars.com/kata/5a4331b18f27f2b31f000085)

##### In input string `word` (1 word):

- replace the vowel with the nearest left consonant.
- replace the consonant with the nearest right vowel.

P.S. To complete this task imagine the alphabet is a circle (connect the first and last element of the array in the mind). For example, 'a' replace with 'z', 'y' with 'a', etc.(see below)

#### For example:

```js
'codewars' => 'enedazuu'
'cat' => 'ezu'
'abcdtuvwxyz' => 'zeeeutaaaaa'
```

##### It is preloaded:

```python
const alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
const consonants = ['b','c','d','f','g','h','j','k','l','m','n','p','q','r','s','t','v','w','x','y','z'];
const vowels = ['a','e','i','o','u'];
```

##### P.S. You work with lowercase letters only.

#### Solution:

```python
def replace_letters(word):
    char_map = {
        'a': 'z', 'b': 'e', 'c': 'e', 'd': 'e', 'e': 'd', 'f': 'i', 'g': 'i', 'h': 'i', 'i': 'h',
        'j': 'o', 'k': 'o', 'l': 'o', 'm': 'o', 'n': 'o', 'o': 'n', 'p': 'u', 'q': 'u', 'r': 'u',
        's': 'u', 't': 'u', 'u': 't', 'v': 'a', 'w': 'a', 'x': 'a', 'y': 'a', 'z': 'a'
    }

    return ''.join(char_map.get(char, char) for char in word)
print(replace_letters('codewars'))  # Output: enedazuu
print(replace_letters('cat'))  # Output: ezu
print(replace_letters('abcdtuvwxyz'))  # Output: zeeeutaaaaa

```
