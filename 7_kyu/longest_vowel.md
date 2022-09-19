## Longest vowel chain

- The vowel substrings in the word codewarriors are o,e,a,io. The longest of these has a length of 2. Given a lowercase string that has alphabetic characters only (both vowels and consonants) and no spaces, return the length of the longest vowel substring. Vowels are any of aeiou.

```python
solve("codewarriors") # 2
solve("suoidea") # 3
solve("ultrarevolutionariees") # 3
```

Solution:

```python
def solve(s): 
    chain, counter = 0,0
    for i in s:
            if i in 'aeiou': 
                counter +=1
                if counter > chain:
                    chain = counter
            else:
                counter = 0
    return chain

print(solve("strengthlessnesses")) # 1 
print(solve("iiihoovaeaaaoougjyaw")) # 8
```