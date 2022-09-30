## Simple Pig Latin

- Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

##### Example

```python
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```

Solution 1:

```python
def pig_it(text):
    return " " .join([i[1:]+i[0]+"ay" if i.isalpha() else i for i in text.split() ]) 

print(pig_it('Pig latin is cool')) # 'igPay atinlay siay oolcay'
print(pig_it('This is my string')) # 'hisTay siay ymay tringsay'
```
Solution 2:

```python
import string 
def pig_it(text):  
    return " " .join([i if i in string.punctuation else i[1:]+i[0]+"ay" for i in text.split() ]) 

print(pig_it('O tempora o mores !')) # 'Oay emporatay oay oresmay !'S
```
