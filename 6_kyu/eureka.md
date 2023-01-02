## [Take a Number And Sum Its Digits Raised To The Consecutive Powers And ....¡Eureka!!](https://www.codewars.com/kata/5626b561280a42ecc50000d1)

- The number 89 is the first integer with more than one digit that fulfills the property partially introduced in the title of this kata. What's the use of saying "Eureka"? Because this sum gives the same number. 
    - In effect: 89 = 8^1 + 9^2

- We need a function to collect these numbers, that may receive two integers a, b that defines the range [a, b] (inclusive) and outputs a list of the sorted numbers in the range that fulfills the property described above.

- Let's see some cases (input -> output):
##### Example  
```python            
1, 10 -> [1, 2, 3, 4, 5, 6, 7, 8, 9] 
1, 100 -> [1, 2, 3, 4, 5, 6, 7, 8, 9, 89]
``` 
Solution:
```python
def sum_dig_pow(a, b):
    eureka = []
    # print(*enumerate(range(a, b + 1)))
    for num in range(a, b + 1):
        sum_num = sum(int(j) ** (index + 1) for index, j in enumerate(str(num)))
        if sum_num == num:
            eureka.append(num)
    return eureka      

print(sum_dig_pow(10, 100)) # [89]
```