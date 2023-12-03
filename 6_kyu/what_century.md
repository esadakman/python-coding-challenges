## [What century is it?](https://www.codewars.com/kata/55dc4520094bbaf50e0000cb)

- Return the century of the input year. The input will always be a 4 digit string, so there is no need for validation.

```js
"1999" --> "20th"
"2011" --> "21st"
"2154" --> "22nd"
"2259" --> "23rd"
"1124" --> "12th"
"2000" --> "20th"
```

#### Solution:

```python
def what_century(year):
    year = int(year)
    century_num = (year - 1) // 100 + 1
    suffix = "th" if 10 <= century_num % 100 <= 20 else {1: "st", 2: "nd", 3: "rd"}.get(century_num % 10, "th")
    return f"{century_num}{suffix}"

print(what_century("1999"))  # "20th"
print(what_century("2011"))  # "21st"
print(what_century("2154"))  # "22nd"
```
