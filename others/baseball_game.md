## Baseball Game

- You are keeping score for a baseball game with strange rules. The game consist of several rounds, where the scores of past rounds may affect future rounds' scores.
- At the beginning of the game, you start with an empty record. You are given a list of strings `ops`, where `ops[i]` is the ith operation you must apply to the record and is one of the following:

- **An integer x** - Record a new score of x,
- **"+"** - Record a new score that is the sum of the previous scores. It is guaranteed there will always be two previous scores.
- **"D"** - Record a new score that is double the previous score. It is guaranteed there will always be a previous score.
- **"C"** - Invalidate the pevious score, removing it from the record. It is guaranteed there will always be a previous score.

_Return the sum of all the scores on the record._

Samples:

```python
 Input: ops = ["5", "2", "C", "D", "+"] // Output: 30
 Input: ops = ["5", "-2", "4", "C", "D", "9", "+", "+"] // Output: 27
```

Solution:

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
```
