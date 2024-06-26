## [Volume of the Largest Cube that Fits Inside a Given Cylinder](https://www.codewars.com/kata/581e09652228a337c20001ac/python)

- Find the volume of the largest cube that will fit inside a cylinder of given height h and radius r.

Don't round your result. The result needs to be within 0.01 error margin of the expected result.

HINT: There are two cases to consider. Will it be the cylinder's height or the cylinder's radius that determines the maximum size of your cube? An if/else statement might be useful here.

#### Two Examples:

```python
1. for height  3, radius 7 => should return  27.0
2. for height 11, radius 5 => should return 353.55
```

#### Solution:

```python
import math

def cube_volume(h, r):
    max_side_by_diagonal = (2 * r) / math.sqrt(2)

    # If the height of the cylinder is greater than or equal to the maximum side length determined by the diagonal
    if h >= max_side_by_diagonal:
        # Cube's side length is determined by the maximum side length by diagonal fit
        return max_side_by_diagonal ** 3
    else:
        # If the height is the limiting factor, use the height for the side length of the cube
        return h ** 3

# Test cases
print(cube_volume(3, 7))  # 27.0
print(cube_volume(11, 5)) # 353.55
print(cube_volume(6, 4))  # 181.019

```
