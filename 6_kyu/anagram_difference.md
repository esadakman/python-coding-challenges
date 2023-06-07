## [Anagram difference](https://www.codewars.com/kata/5b1b27c8f60e99a467000041)

##### Given two words, how many letters do you have to remove from them to make them anagrams?

#### Example

- First word : c od e w ar s (4 letters removed)
- Second word : ha c k er r a nk (6 letters removed)
- Result : <b>10<b>

#### Hints

- A word is an anagram of another word if they have the same letters (usually in a different order).
- Do not worry about case. All inputs will be lowercase.

#### Solution:

```python
from collections import Counter

def anagram_difference(w1, w2):
    count1 = Counter(w1)
    count2 = Counter(w2)
    removal_count = sum((count1 - count2).values()) + sum((count2 - count1).values())
    return removal_count

# Example usage:
w1 = "code wars"
w2 = "hacker rank"
difference = anagram_difference(w1, w2)
print(difference)  # Output: 10
```
