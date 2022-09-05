# python-coding-challenges

## Question 1 (Baseball Game)

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
ops = ["5", "-2", "4", "C", "D", "9", "+", "+"]
print(baseball(ops)) # 27
```

## Question 2 (Fake Binary)

- Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

Note: input will never be an empty string

Solution:

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

```python
 Input: str = ("Hello World!") // Output: Hello World
 Input: str = ("Hello World!!!") // Output: Hello World
```

Solution:

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

Solution:

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

```python
"hello" --> "hll"\
"codewars" --> "cdwrs"\
"goodbye" --> "gdby"\
"HELLO" --> "HELLO"
```

- don't worry about uppercase vowels
- y is not considered a vowel for this kata

Solution:

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

## Question 6 (Beginner Series #3 Sum of Numbers )

- Given two integers a and b, which can be positive or negative, find the sum of all the integers between and including them and return it. If the two numbers are equal return a or b.

Note: a and b are not ordered!

Samples:

```python
(1, 0) --> 1 (1 + 0 = 1)
(1, 1) --> 1 (1 since both are same)
(-1, 0) --> -1 (-1 + 0 = -1)
(-1, 2) --> 2 (-1 + 0 + 1 + 2 = 2)
```

Solution:

```python
def get_sum(a,b):
    result = 0
    if (a < b):
        for i in range(a,b+1):
            result += i
    elif (a > b):
        for i in range(b,a+1):
            result += i
    else:
        return a
    return result

print(get_sum(0,2)) #3
print(get_sum(2,2)) #2
print(get_sum(0,-1)) #-1

```

## Question 7 (Categorize New Member )

- The Western Suburbs Croquet Club has two categories of membership, Senior and Open. They would like your help with an application form that will tell prospective members which category they will be placed.

- To be a senior, a member must be at least 55 years old and have a handicap greater than 7. In this croquet club, handicaps range from -2 to +26; the better the player the lower the handicap.

Input
&nbsp; Input will consist of a list of pairs. Each pair contains information for a single potential member. Information consists of an integer for the person's age and an integer for the person's handicap.

Output
&nbsp; Output will consist of a list of string values (in Haskell and C: Open or Senior) stating whether the respective member is to be placed in the senior or open category.

Samples:

```python
input =  [[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]
output = ["Open", "Open", "Senior", "Open", "Open", "Senior"]
```

Solution:

```python
def open_or_senior(data):
    result = []
    for i in data:
        if (i[0] >= 55 and i[1] > 7 ):
            result.append("Senior")
        else:
            result.append("Open")

    return result # ['Open', 'Senior', 'Open', 'Senior']

```

## Question 8 (Combine objects )

- Your task is to write a function that takes two or more objects and returns a new object which combines all the input objects.

- All input object properties will have only numeric values. Objects are combined together so that the values of matching keys are added together.

Samples:

```python
objA = { 'a': 10, 'b': 20, 'c': 30 }
objB = { 'a': 3, 'c': 6, 'd': 3 }
combine(objA, objB) # Returns { a: 13, b: 20, c: 36, d: 3 }
```

The combine function should be a good citizen, so should not mutate the input objects.

Solution:

```python
def combine(*args):
    combined= {}
    for i in args:
        for j,k in i.items():
            if j in combined:
                combined[j] += k
            else:
                combined[j] = k
    return combined


objA = { 'a': 10, 'b': 20, 'c': 30 }
objB = { 'a': 3, 'c': 6, 'd': 3 }
print(combine(objA, objB)) # Returns { a: 13, b: 20, c: 36, d: 3 }


```

## Question 9 (Find Duplicates )

- Given an array, find the duplicates in that array, and return a new array of those duplicates. The elements of the returned array should appear in the order when they first appeared as duplicates.

Note: numbers and their corresponding string representations should not be treated as duplicates (i.e., "1" != 1).

Samples:

```python
[1, 2, 4, 4, 3, 3, 1, 5, 3, "5"]  ==>  [4, 3, 1]
[0, 1, 2, 3, 4, 5]                ==>  []
```

Solution:

```python
def duplicates(array):
    dupli = []
    arr = []
    for i in array:
        if i in arr:
            if i not in dupli:
                dupli.append(i)
        else:
            arr.append(i)
    return dup 

print(duplicates([1, 2, 4, 4, 3, 3, 1, 5, 3, '5'])) # [4, 3, 1]
print(duplicates([0, 1, 2, 3, 4, 5])) # []


```

## Question 10 (Evens times last )

- Given a sequence of integers, return the sum of all the integers that have an even index (odd index in COBOL), multiplied by the integer at the last index.

Indices in sequence start from 0.

If the sequence is empty, you should return 0.

```python
([2, 3, 4, 5])  ==> 30
([])  ==> 0
```

Solution:

```python
def even_last(numbers):
    sum = 0
    if len(numbers) == 0:
        return 0
    else:
        for i in range(len(numbers)):
            if i % 2 == 0:
                sum += numbers[i]
    return sum*numbers[-1]

print(even_last([2, 3, 4, 5])) # 30
print(even_last([])) # 0

```

## Question 11 (Find the divisors!)

- Create a function named divisors/Divisors that takes an integer n > 1 and returns an array with all of the integer's divisors(except for 1 and the number itself), from smallest to largest. If the number is prime return the string '(integer) is prime'.

```python
divisors(12); #should return [2,3,4,6]
divisors(25); #should return [5]
divisors(13); #should return "13 is prime"
```

Solution:

```python
def divisors(integer):
    divs = [i for i in range(2,integer) if integer % i == 0]
    return divs if len(divs) > 0 else "{} is prime".format(integer)

print(divisors(12)) # [2,3,4,6]
print(divisors(25)) # [5]
print(divisors(13)) # "13 is prime"

```

## Question 12 (Flatten)

- Write a function that flattens an Array of Array objects into a flat Array. Your function must only do one level of flattening.

```python
flatten [1,2,3] # => [1,2,3]
flatten [[1,2,3],["a","b","c"],[1,2,3]]  # => [1,2,3,"a","b","c",1,2,3]
flatten [[[1,2,3]]] # => [[1,2,3]]
```

Solution:

```python
def flatten(lst):
    flattened  = []
    for i in lst:
        if type(i) == list:
           flattened .extend(i)
        else:
           flattened .append(i)
    return flattened 

print(flatten([1,2,3]))  # => [1,2,3]
print(flatten([[1,2,3],["a","b","c"],[1,2,3]]))  # => [1,2,3,"a","b","c",1,2,3]
print(flatten( [[[1,2,3]]])) # => [[1,2,3]]

```

## Question 13 (Get the Middle Character)

- You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.

```python
get_middle("test") should return "es"
get_middle("testing") should return "t"
get_middle("middle") should return "dd"
get_middle("A") should return "A"
```

Solution:

```python
def get_middle(s):
    middle = len(s)/2
    if (float(middle) == int(middle)):
        return (s[int(middle)-1:int(middle)+1])
    else:
        return (s[int(middle)])

print(get_middle("test")) # "es"
print(get_middle("testing")) # "t"
print(get_middle("middle")) # "dd"
print(get_middle("A")) # "A"
```

## Question 14 (Highest and Lowes)

- In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

```python
high_and_low("1 2 3 4 5")  # return "5 1"
high_and_low("1 2 -3 4 5") # return "5 -3"
high_and_low("1 9 3 4 -5") # return "9 -5"
```

Solution:

```python
def high_and_low(numbers):  
    num = [int(x) for x in numbers.split(' ')]
    return "{} {}".format(max(num), min(num)) 

print(high_and_low("1 2 3 4 5") ) # return "5 1"
print(high_and_low("1 2 -3 4 5"))  # return "5 -3"
print(high_and_low("1 9 3 4 -5") ) # return "9 -5" 
```

## Question 15 (Indexed capitalization)

- Given a string and an array of integers representing indices, capitalize all letters at the given indices.

```python
capitalize("abcdef",[1,2,5]) = "aBCdeF"
capitalize("abcdef",[1,2,5,100]) = "aBCdeF". There is no index 100.
```

- The input will be a lowercase string with no spaces and an array of digits.

Solution:

```python
def capitalize(s, ind):
    letters = list(s)
    length = len(s)
    for i in ind:
        if i < length:
            letters[i] = letters[i].upper()
    return ''.join(letters)


print(capitalize("abcdef",[1,2,5])) # "aBCdeF"
print(capitalize("abcdef",[1,2,5,100])) # "aBCdeF". There is no index 100.
```

## Question 16 (Least Larger)

- Given an array of numbers and an index, return either the index of the smallest number that is larger than the element at the given index, or -1 if there is no such index ( or, where applicable, Nothing or a similarly empty value ).
Notes:
- Multiple correct answers may be possible. In this case, return any one of them.
- The given index will be inside the given array.
- The given array will, therefore, never be empty.

```python
least_larger( [4, 1, 3, 5, 6], 0 )  # ->  3
least_larger( [4, 1, 3, 5, 6], 4 )  # -> -1
```
 

Solution:

```python
def least_larger(a, ind):  
    try:
        return a.index(min(i for i in a if i > a[ind]))  
    except ValueError:
        return -1
    
print(least_larger( [4, 1, 3, 5, 6], 0)) # ->  3
print(least_larger( [4, 1, 3, 5, 6], 4)) # ->  -1
print(least_larger( [1, 3, 5, 2, 4], 0)) # ->  3
```

## Question 17 (Longest vowel chain)

- The vowel substrings in the word codewarriors are o,e,a,io. The longest of these has a length of 2. Given a lowercase string that has alphabetic characters only (both vowels and consonants) and no spaces, return the length of the longest vowel substring. Vowels are any of aeiou.

```python
solve("codewarriors") # 2
solve("suoidea") # 3
solve("ultrarevolutionariees") # 3
```

Solution:

```python
def solve(s): 
    reset, counter = 0,0
    for i in s:
            if i in 'aeiou': 
                counter +=1
                if counter > reset:
                    reset = counter
            else:
                counter = 0
    return reset

print(solve("strengthlessnesses")) # 1
print(solve("cuboideonavicuare")) # 2
print(solve("chrononhotonthuooaos")) # 5
print(solve("iiihoovaeaaaoougjyaw")) # 8
```

## Question 18 (My Language Skills)

- You are given a dictionary/hash/object containing some languages and your test results in the given languages. Return the list of languages where your test score is at least 60, in descending order of the results.

```python
{"Java": 10, "Ruby": 80, "Python": 65}    #  ["Ruby", "Python"]
{"Hindi": 60, "Dutch" : 93, "Greek": 71}  #  ["Dutch", "Greek", "Hindi"]
{"C++": 50, "ASM": 10, "Haskell": 20}     #  []
```

Solution:

```python
def my_languages(results): 
    res = [] 
    for k, v in sorted(results.items(), key=lambda x: x[1], reverse=True):
        if (v>=60):
            res.append(k) 
    return res 

print(my_languages({"Java": 10, "Ruby": 80, "Python": 65} )) #  ["Ruby", "Python"]
print(my_languages({"Hindi": 60, "Dutch" : 93, "Greek": 71}  )) #  ["Dutch", "Greek", "Hindi"]
print(my_languages({"C++": 50, "ASM": 10, "Haskell": 20}     )) #  []
```

## Question 19 (Parts of a list)

Write a function partlist that gives all the ways to divide a list (an array) of at least two elements into two non-empty parts.

- Each two non empty parts will be in a pair (or an array for languages without tuples or a structin C - C: see Examples test Cases - )
- Each part will be in a string
- Elements of a pair must be in the same order as in the original array.

```python
print(partlist(["I", "wish", "I", "hadn't", "come"])) #  [("I", "wish I hadn't come"), ("I wish", "I hadn't come"), ("I wish I", "hadn't come"), ("I wish I hadn't", "come")]) 
```

Solution:

```python
def partlist(arr):
    tuples = []
    for i in range(len(arr)):
        a = ' '.join(arr[:i])
        b = ' '.join(arr[i:])
        tuples.append((a,b)) 
        
    return tuples[1:]

print(partlist(["cdIw", "tzIy", "xDu", "rThG"])) # [("cdIw", "tzIy xDu rThG"), ("cdIw tzIy", "xDu rThG"), ("cdIw tzIy xDu", "rThG")] 
print(partlist(["vJQ", "anj", "mQDq", "sOZ"])) # [("vJQ", "anj mQDq sOZ"), ("vJQ anj", "mQDq sOZ"), ("vJQ anj mQDq", "sOZ")]
```
