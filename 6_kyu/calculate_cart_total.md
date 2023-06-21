## [Tolkien's Book Cart](https://www.codewars.com/kata/59a2666349ae65ea69000051)

- Tolkein's publisher wishes to implement an online store for the "Lord of the Rings" and "The Hobbit" books. Each book costs $10. However, if 2 titles are purchased, a 5% discount will be received, i.e. purchasing "Fellowship of the Ring" and "Two Towers" will cost $19. If 3 different titles are purchased, a 10% discount will be received. The purchase of all 4 different titles will receive a 20% discount. An additional single title will be full-price.

- The encoding of an order will be in the form of strings in an array. For example: `[“F”, “T”, “R”, “H”, “H”]` is the encoding of 2 copies of "The Hobbit" and a single copy of each of the titles in the "Lord of the Rings" trilogy.

- The expected output is a number. E.g. 42 is the expected output for the example above. The output should be the cheapest total cost. For example - if the book order is `["F", "T", "H", "F", "T", "R"]`, valid total costs include `(3*10 discounted by 10%)` + `(3*10 discounted by 10%)` and `(4*10 discounted by 20%)` + `(2*10 discounted by 5%)`. The cheapest total cost is 51.

#### Solution:

```python
def get_cost(unique):
    lookup = [0, 10, 19, 27, 32, 46, 54, 59]
    cost = 0
    while unique > 7:
        cost += 32
        unique -= 4
    return cost + lookup[unique]

def calculate_cart_total(cart):
    counts = {}
    for item in cart:
        counts[item] = counts.get(item, 0) + 1
    result = 0
    while len(counts) > 1:
        result += get_cost(len(counts))
        keys = list(counts.keys())
        for key in keys:
            if counts[key] == 1:
                del counts[key]
            else:
                counts[key] -= 1
    for key, value in counts.items():
        result += value * 10
    return result


print(calculateCartTotal(['book1', 'book2', 'book2', 'book3', 'book3', 'book3', 'book4', 'book4', 'book4', 'book4'])) # Output: 66 (20% discount on 4 books, 10% discount on 3 books)
print(calculateCartTotal( ['book1', 'book1', 'book1', 'book2', 'book3'])) # Output: 33 (10% discount on 3 books)
```
