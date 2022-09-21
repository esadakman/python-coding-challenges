## Handshake problem

- Johnny is a farmer and he annually holds a beet farmers convention "Drop the beet".

- Every year he takes photos of farmers handshaking. Johnny knows that no two farmers handshake more than once. He also knows that some of the possible handshake combinations may not happen.

- However, Johnny would like to know the minimal amount of people that participated this year just by counting all the handshakes.

- Help Johnny by writing a function, that takes the amount of handshakes and returns the minimal amount of people needed to perform these handshakes (a pair of farmers handshake only once).
 

Solution:
```python
def get_participants(handshakes):
    counter = 1
    h = 0 
    if (handshakes == 0):
        return 0
    else:
        while h < handshakes:
            counter += 1
            h += counter - 1
        return counter 
 
print(get_participants(1)) # 2
print(get_participants(5)) # 4
print(get_participants(10)) # 5
```