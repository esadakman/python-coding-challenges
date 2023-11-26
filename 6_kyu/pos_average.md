## [Positions Average](https://www.codewars.com/kata/59f4a0acbee84576800000af)

- Suppose you have 4 numbers: `0, 9, 6, 4 and 3` strings composed with them:

```js
s1 = "6900690040";
s2 = "4690606946";
s3 = "9990494604";
```

- Compare `s1` and `s2` to see how many positions they have in common: `0` at index `3`, `6` at index `4`, `4` at index 8 : 3 common positions out of ten.

- Compare `s1` and `s3` to see how many positions they have in common: `9` at index `1`, `0` at index `3`, `9` at index 5 : 3 common positions out of ten.

- Compare `s2` and `s3`. We find 2 common positions out of ten.

So for the 3 strings we have 8 common positions out of 30 ie 0.2666... or 26.666...%

Given `n` substrings (n >= 2) in a string `s` our function `pos_average` will calculate the average percentage of positions that are the same between the `(n * (n-1)) / 2` sets of substrings taken amongst the given `n` substrings. It can happen that some substrings are duplicate but since their ranks are not the same in `s` they are considered as different substrings.

The function returns the percentage formatted as a float with 10 decimals but the result is tested at 1e.-9 (see function assertFuzzy in the tests).

##### Example:

- Given string s = "444996, 699990, 666690, 096904, 600644, 640646, 606469, 409694, 666094, 606490" composing a set of n = 10 substrings (hence 45 combinations), `pos_average` returns `29.2592592593`.

In a set the `n` substrings will have the same length ( > 0 ).

##### Notes

- You can see other examples in the "Sample tests".

#### Solution:

```python
def common_positions(s1, s2):
    return sum(1 for c1, c2 in zip(s1, s2) if c1 == c2)

def pos_average(s):
    substrings = s.split(', ')
    n = len(substrings)
    total_percentage = 0.0
    pair_count = 0

    for i in range(n):
        for j in range(i + 1, n):
            common = common_positions(substrings[i], substrings[j])
            total_percentage += (common / len(substrings[i])) * 100
            pair_count += 1

    return round(total_percentage / pair_count, 10) if pair_count != 0 else 0.0

s = "444996, 699990, 666690, 096904, 600644, 640646, 606469, 409694, 666094, 606490"
print(pos_average(s)) # 29.2592592593
```