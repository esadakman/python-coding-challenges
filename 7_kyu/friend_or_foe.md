## [Friend or Foe?](https://www.codewars.com/kata/55b42574ff091733d900002f)

- Make a program that filters a list of strings and returns a list with only your friends name in it.

- If a name has exactly 4 letters in it, you can be sure that it has to be a friend of yours! Otherwise, you can be sure he's not...

- Ex: Input = ["Ryan", "Kieran", "Jason", "Yous"], Output = ["Ryan", "Yous"]

```js
friend ["Ryan", "Kieran", "Mark"] `shouldBe` ["Ryan", "Mark"]
```

- Note: keep the original order of the names in the output.

#### Solution:

```python
def friend_or_foe(friends):
    return [name for name in friends if len(name) == 4]

print(friend_or_foe(["Ryan", "Kieran", "Mark"])) #  ["Ryan", "Mark"] 
print(friend_or_foe(["Ryan", "Jimmy", "123", "4", "Cool Man"])) # ["Ryan"]
print(friend_or_foe(["Jimm", "Cari", "aret", "truehdnviegkwgvke", "sixtyiscooooool"])) # ["Jimm", "Cari", "aret"]
```
