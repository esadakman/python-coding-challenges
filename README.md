# python-coding-challenges

## Question 1 (Baseball Game)

- You are keeping score for a baseball game with strange rules. The game consist of several rounds, where the scores of past rounds may affect future rounds' scores.
- At the beginning of the game, you start with an empty record. You are given a list of strings `ops`, where `ops[i]` is the ith operation you must apply to the record and is one of the following:

- **An integer x** - Record a new score of x,
- **"+"** - Record a new score that is the sum of the previous scores. It is guaranteed there will always be two previous scores.
- **"D"** - Record a new score that is double the previous score. It is guaranteed there will always be a previous score.
- **"C"** - Invalidate the pevious score, removing it from the record. It is guaranteed there will always be a previous score.

_Return the sum of all the scores on the record._

Samples:\

- Input: ops = ["5", "2", "C", "D", "+"] // Output: 30
- Input: ops = ["5", "-2", "4", "C", "D", "9", "+", "+"] // Output: 27

```python
def baseball(ops) :
    arr = []

    for i in ops:
        if i == "+" :
            arr.append(arr[-1] + arr[-2])
        elif i == "D":
            arr.append(2 * arr[-1])
        elif i == "C":
            arr.pop()
        else:
            arr.append(int(i))

    return sum(arr)

ops = ["5", "2", "C", "D", "+"]
print(baseball(ops)) # 30
ops = ["5", "-2", "4", "C", "D", "9", "+", "+"]
print(baseball(ops)) # 27
```

## Question 2 (Fake Binary)

- Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

Note: input will never be an empty string

```python
def fake_bin(num_str):
    binary = ""

    for i in num_str:
        if int(i) < 5:
            binary += "0"
        else:
            binary += "1"

    return binary

```
