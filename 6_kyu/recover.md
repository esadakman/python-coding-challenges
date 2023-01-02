## [Digit Recovery](https://www.codewars.com/kata/5964d7e633b908e172000046)

- Some letters in the input string are representing a written-out digit. Some of the letters may randomly shuffled. Your task is to recover them all.

Note that:

<ul>
<li>Only consecutive letters can be used. "OTNE" cannot be recovered to 1!</li>
<li>Every letter has to start with an increasing index.. "ONENO" results to 11, because the E can be used two times. Endless loops are not possible!</li>
<li>If there are letters in the string, which don't create a number you can ignore them.</li>
<li>If no digits can be found, return "No digits found"</li>
<li>Take care about the order! "ENOWT" will be recovered to 12 and not to 21.</li>
<li>The input string consists only UpperCase letters</li>
e.g.
</ul>

Samples:

```python
recover("NEO") =>  "1"
recover("ONETWO") => "12"
recover("ONENO") => "11"
recover("TWWTONE") => "21"
recover("ZYX") => "No digits found"
recover("NEOTWONEINEIGHTOWSVEEN") => "12219827"
```

You can use the following preloaded dictionary in your solution:

```python
alph = {"ZERO":0,"ONE":1,"TWO":2,"THREE":3,"FOUR":4,"FIVE":5,"SIX":6,"SEVEN":7,"EIGHT":8,"NINE":9};
```

Solution:

```python
alph = {"ZERO":0,"ONE":1,"TWO":2,"THREE":3,"FOUR":4,"FIVE":5,"SIX":6,"SEVEN":7,"EIGHT":8,"NINE":9}
def recover(st):
    res=str()
    for i in range(len(st)-2):
        for k,t in alph.items():  
            if sorted(st[i:i+len(k)])==sorted(k): res+=str(t)
    return res if res!='' else 'No digits found'


print(recover("ZYX")) # "No digits found"
print(recover("NEOTWONEINEIGHTOWSVEEN")) # "12219827"
```
