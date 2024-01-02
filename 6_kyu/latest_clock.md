## [The latest clock](https://www.codewars.com/kata/58925dcb71f43f30cd00005f)

#### DESCRIPTION:

- Write a function which receives 4 digits and returns the latest time of day that can be built with
  digits.

- The time should be in HH:MM format.

#### Examples:

```python
digits: 1, 9, 8, 3 => result: "19:38"
digits: 9, 1, 2, 5 => result: "21:59" ("19:25" is also a valid time, but 21:59 is later)
```

#### Notes

- Result should be a valid 24-hour time, between 00:00 and 23:59.
- Only inputs which have valid answers are tested.

#### Solution:

```python
import itertools

def latest_clock(a, b, c, d):
    digits = [a, b, c, d]
    max_hour = -1
    max_minute = -1

    # Generate all possible permutations of the digits
    for perm in itertools.permutations(digits):
        hour = perm[0] * 10 + perm[1]
        minute = perm[2] * 10 + perm[3]

        # Check if the time is valid
        if hour < 24 and minute < 60:
            if hour > max_hour or (hour == max_hour and minute > max_minute):
                max_hour = hour
                max_minute = minute

    # Format the result
    formatted_hour = str(max_hour).zfill(2)
    formatted_minute = str(max_minute).zfill(2)
    return f"{formatted_hour}:{formatted_minute}"

print(latest_clock(1, 9, 8, 3))  # "19:38"
print(latest_clock(9, 1, 2, 5))  # "21:59"
print(latest_clock(0, 0, 0, 0))  # "00:00"
```
