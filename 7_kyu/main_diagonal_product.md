## [Product of the main diagonal of a square matrix.](https://www.codewars.com/kata/551204b7509063d9ba000b45)

- Given a list of rows of a square matrix, find the product of the main diagonal.

#### Exapmples

```js
  [[1, 0], [0, 1]] should return 1
  [[1, 2, 3], [4, 5, 6], [7, 8, 9]] should return 45 
```

#### Solution :

```python
def main_diagonal_product(mat):
    product = 1
    for i in range(len(mat)):
        product *= mat[i][i]
    return product

print(main_diagonal_product([[1,0],[0,1]])) # 1
```
