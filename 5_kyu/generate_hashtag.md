## The Hashtag Generator 

- The marketing team is spending way too much time typing in hashtags.
Let's help them with our own Hashtag Generator!

Here's the deal:
- It must start with a hashtag (#).
- All words must have their first letter capitalized.
- If the final result is longer than 140 chars it must return false.
- If the input or the result is an empty string it must return false.
```python
" Hello there thanks for trying my Kata"  =>  "#HelloThereThanksForTryingMyKata"
""                                        =>  false
```

Solution:

```python
def generate_hashtag(s):
    s = ' '.join(word[0].upper() + word[1:] for word in s.lower().split()).replace(" ", "")
    s = '#' + s[:] 
    return s if len(s)in range(2,140) else False

print(generate_hashtag('Do We have A Hashtag')) # #DoWeHaveAHashtag 
print(generate_hashtag('CodeWars is nice')) # #CodewarsIsNice 
```