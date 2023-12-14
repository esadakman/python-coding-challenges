## [The 'spiraling' box](https://www.codewars.com/kata/63b84f54693cb10065687ae5)

#### Task

Given two positive integers m (width) and n (height), fill a two-dimensional list (or array) of size m-by-n in the following way:

- (1) All the elements in the first and last row and column are 1.

- (2) All the elements in the second and second-last row and column are 2, excluding the elements from step 1.

- (3) All the elements in the third and third-last row and column are 3, excluding the elements from the previous steps.

- And so on ...

#### Examples

Given m = 5, n = 8, your function should return

```js
[
  [1, 1, 1, 1, 1],
  [1, 2, 2, 2, 1],
  [1, 2, 3, 2, 1],
  [1, 2, 3, 2, 1],
  [1, 2, 3, 2, 1],
  [1, 2, 3, 2, 1],
  [1, 2, 2, 2, 1],
  [1, 1, 1, 1, 1],
];
```

- Given m = 10, n = 9, your function should return

```js
[
  [1, 1, 1, 1, 1, 1, 1, 1, 1, 1],
  [1, 2, 2, 2, 2, 2, 2, 2, 2, 1],
  [1, 2, 3, 3, 3, 3, 3, 3, 2, 1],
  [1, 2, 3, 4, 4, 4, 4, 3, 2, 1],
  [1, 2, 3, 4, 5, 5, 4, 3, 2, 1],
  [1, 2, 3, 4, 4, 4, 4, 3, 2, 1],
  [1, 2, 3, 3, 3, 3, 3, 3, 2, 1],
  [1, 2, 2, 2, 2, 2, 2, 2, 2, 1],
  [1, 1, 1, 1, 1, 1, 1, 1, 1, 1],
];
```

Solution:

```python
def create_box(m, n):
    return [[min(i, j, n-1-i, m-1-j) + 1 for j in range(m)] for i in range(n)]

print(createBox(5, 8)); 
print(createBox(10, 9));
```
