## [Where my anagrams at?](https://www.codewars.com/kata/523a86aa4230ebb5420001e1)

- What is an anagram? Well, two words are anagrams of each other if they both contain the same letters. For example:

```python
'abba' & 'baab' == true 
'abba' & 'bbaa' == true 
'abba' & 'abbba' == false 
'abba' & 'abca' == false
```
- Write a function that will find all the anagrams of a word from a list. You will be given two inputs a word and an array with words. You should return an array of all the anagrams or an empty array if there are none. For example:

##### Example  
```python  
anagrams('abba', ['aabb', 'abcd', 'bbaa', 'dada']) => ['aabb', 'bbaa']  
anagrams('laser', ['lazing', 'lazy',  'lacer']) => []  
``` 
 
##### Solution:
```python
def anagrams(word, words):  
    return list(i for i in words if sorted(word) == sorted(i)) 

print(anagrams('abba', ['aabb', 'abcd', 'bbaa', 'dada'])) # ['aabb', 'bbaa']
print(anagrams('racer', ['crazer', 'carer', 'racar', 'caers', 'racer'])) # ['carer', 'racer']
``` 