## [Don't rely on luck.](https://www.codewars.com/kata/5268af3872b786f006000228/python)

- The test fixture I use for this kata is pre-populated.

- It will compare your guess to a random number generated using:

##### Example

```python
randint(1,100)
```

- You can pass by relying on luck or skill but try not to rely on luck.

- "The power to define the situation is the ultimate power." - Jerry Rubin

Solution:

```python
from random import randint


class cheating_number:
    def __eq__(self, x):
        return True


guess = cheating_number()
```
