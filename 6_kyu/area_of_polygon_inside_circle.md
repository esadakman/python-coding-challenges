## [Calculate the area of a regular n sides polygon inside a circle of radius r](https://www.codewars.com/kata/5a58ca28e626c55ae000018a/python)

-Write the following function:

`function areaOfPolygonInsideCircle(circleRadius, numberOfSides)`

- It should calculate the area of a regular polygon of `numberOfSides`, `number-of-sides`, or `number_of_sides`sides inside a circle of radius `circleRadius`, `circle-radius`, or `circle_radius` which passes through all the vertices of the polygon (such circle is called circumscribed circle or circumcircle). The answer should be a number rounded to 3 decimal places.

#### Samples:

```python
area_of_polygon_inside_circle(3, 3) # returns 11.691

area_of_polygon_inside_circle(5.8, 7) # returns 92.053

area_of_polygon_inside_circle(4, 5) # returns 38.042
```

Note: if you need to use Pi in your code, use the native value of your language unless stated otherwise.

#### Solution:

```python
import math

def area_of_polygon_inside_circle(circle_radius, number_of_sides):
    area = ((circle_radius ** 2 * number_of_sides) / 2) * math.sin((2 * math.pi) / number_of_sides)
    return round(area, 3)

print(area_of_polygon_inside_circle(2, 4)); # returns 8
print(area_of_polygon_inside_circle(2.5, 5)); # returns 14.86
```
