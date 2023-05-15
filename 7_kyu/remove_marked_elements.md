## [Remove All The Marked Elements of a List](https://www.codewars.com/kata/563089b9b7be03472d00002b/train/python)

##### Story

- Define a method/function that removes from a given array of integers all the values contained in a second array.

#### Examples (input -> output):

```python
* [1, 1, 2, 3, 1, 2, 3, 4], [1, 3] -> [2, 2, 4]
* [1, 1, 2, 3, 1, 2, 3, 4, 4, 3, 5, 6, 7, 2, 8], [1, 3, 4, 2] -> [5, 6, 7, 8]
* [8, 2, 7, 2, 3, 4, 6, 5, 4, 4, 1, 2, 3], [2, 4, 3] -> [8, 7, 6, 5, 1]
```

##### Notes

- If no button is currently active, return Nothing.
- If the list is empty, return Nothing.

#### Solution:

```python
class List:
    def remove_(self, integer_list, values_list):
        return [i for i in integer_list if i not in values_list]

lst = List()
print(lst.remove_([1, 1, 2, 3, 1, 2, 3, 4], [1, 3]))  # [2, 2, 4]
print(lst.remove_([1, 1, 2, 3, 1, 2, 3, 4, 4, 3, 5, 6, 7, 2, 8], [1, 3, 4, 2]))  # [5, 6, 7, 8]
print(lst.remove_([8, 2, 7, 2, 3, 4, 6, 5, 4, 4, 1, 2, 3], [2, 4, 3]))  # [8, 7, 6, 5, 1]
```