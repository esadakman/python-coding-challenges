## [Alternating between three values](https://www.codewars.com/kata/596776fbb4f24d0d82000141)

- Suppose a variable x can have only three possible different values a, b and c, and you wish to assign to x the value other than its current one, and you wish your code to be independent of the values of a, b and c.

What is the most efficient way to cycle among three values? Write a function f so that it satisfies

```js
  f(a) = b
  f(b) = c
  f(c) = a
```

#### Example:

```python
f( 3, { a:3, b:4, c:5 } ) => 4
```

#### Solution:

```python
def f(x, a, b, c):
    values = [a, b, c]
    index = values.index(x)
    return values[(index + 1) % 3]

a = 3
b = 4
c = 5
print(f(3, a, b, c))  # Output: 4

```
