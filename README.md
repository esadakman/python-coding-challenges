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

## Question 3 (Remove exclamation marks)

- Write function RemoveExclamationMarks which removes all exclamation marks from a given string.

_Return the sum of all the scores on the record._

Samples:\

- Input: str = ("Hello World!") // Output: Hello World
- Input: str = ("Hello World!!!") // Output: Hello World

```python
def remove_exclamation_marks(str):

    return str.replace("!", "")

print(remove_exclamation_marks("Hello World!")) #Hello World
print(remove_exclamation_marks("Hello World!!!!")) #Hello World
```

## Question 4 ( Total amount of points)

- Our football team finished the championship. The result of each match look like "x:y". Results of all matches are recorded in the collection.

-- For example: ["3:1", "2:2", "0:1", ...]

- Write a function that takes such collection and counts the points of our team in the championship. Rules for counting points for each match:\

if x > y: 3 points\
if x < y: 0 point\
if x = y: 1 point\

- Notes:\
-there are 10 matches in the championship
-0 <= x <= 4
-0 <= y <= 4

```python
def points(games):
    result = 0
    for i in games:
        j = i.split(":")
        if j[0] > j[1]:
            result+=3
        elif j[0] == j[1]:
            result+=1
    return result


points(['1:0','2:0','3:0','4:0','2:1','3:1','4:1','3:2','4:2','4:3']) # 30

```

## Question 5 (Vowel remover)

- Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.

Samples:

"hello" --> "hll"\
"codewars" --> "cdwrs"\
"goodbye" --> "gdby"\
"HELLO" --> "HELLO"\

- don't worry about uppercase vowels
- y is not considered a vowel for this kata

```python

def shortcut( s ):
    vowels = ('a', 'e', 'i', 'o', 'u')
    newStr  = s
    for i in s:
        if i in vowels:
            newStr = newStr.replace(i,"")
    return newStr


print(shortcut("hello")) # hll
print(shortcut("codewars")) # cdwrs
print(shortcut("HELLO")) # HELLO

```
