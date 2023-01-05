## [Over The Road](https://www.codewars.com/kata/5f0ed36164f2bc00283aed07) 

- You've just moved into a perfectly straight street with exactly n identical houses on either side of the road. Naturally, you would like to find out the house number of the people on the other side of the street. The street looks something like this:

```python
Street                     
1|   |6                      
3|   |4                      
5|   |2                       
  you                                     
```
Evens increase on the right; odds decrease on the left. House numbers start at 1 and increase without gaps. When n = 3, 1 is opposite 6, 3 opposite 4, and 5 opposite 2.  
##### Example (address, n --> output)   

- Given your house number address and length of street n, give the house number on the opposite side of the street.    

```python            
1, 3 --> 6      |    3, 3 --> 4     |   2, 3 --> 5      |    3, 5 --> 8
```
Solution:

```python
def over_the_road(address, n):
    return n*2 - (address -1 )
   
print(over_the_road(3, 5)) # 8
```