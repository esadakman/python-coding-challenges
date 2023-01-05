## [They're good dogs.](https://www.codewars.com/kata/5965144da82d479517000001) 

- The function weRateDogs(str, rating) takes a string and an integer as the inputs. Within the string is an incorrect rating x/y.
- You will need to change the incorrect rating x/y to the correct rating rating/10. The given string may contain numbers and letters, but no special characters other than /.  

##### Example  

```python            
'This is Max99. She has one ear that is always s1ightly higher than the other 4/10 wonky af' => 11
'This is Max99. She has one ear that is always s1ightly heigher than the other 11/10 wonky af'
```
Solution:

```python
def we_rate_dogs(string, rating):
    num_index = string.index("/") - 1 
    new_str = string[:num_index] + str(rating) + string[num_index + 1:] 
    return new_str

print(we_rate_dogs('This is Tucker. He would like a hug. 3/10 someone hug him', 11)) # ".... 11/10 somenone hug him" 
```