## [Character Counter and Bars Graph](https://www.codewars.com/kata/5826773bfad36332bf0002f9)

#### Description

1. Given some text, count each alphabetic character's occurrence in it, regardless of the case.

2. Let's suppose you have to use an old terminal window to represent the occurrencies of each character in a text-based horizontal bar graph. The terminal has a maximum width, provided as parameter (max_units_on_screen), and you have to abide by it.

For example, if the maximum width is 80, your longest bar in the graph will be scaled to this size and all the others have to be represented and scaled proportionally to this size. Every unit of the bar will be represented by the character #. See examples below for typical output format.

3. The bars of the graph have to be sorted by number of occurrencies (from biggest to lowest, before getting scaled), then by alphabetic order of the letter (from a to z). Approximation of decimal numbers will happen on the lowest integer (for example: 57.1, 57.2, 57.68, 57.999 will all get reduced to 57 )

#### Example 1:

Input:

```js
count_and_print_graph("just a short text", 4);
```

Output

```js
t:####
s:##
a:#
e:#
h:#
j:#
o:#
r:#
u:#
x:#
```

#### Example 2:

Input:

```js
count_and_print_graph("just a short text", 23);
```

Output

```js
t:#######################
s:###########
a:#####
e:#####
h:#####
j:#####
o:#####
r:#####
u:#####
x:#####
```

#### Solution:

```python
def count_and_print_graph(text, max_units_on_screen):
    char_count = {}

    # Count occurrences of each character in the text
    for char in text:
        char = char.lower()
        if char.isalpha():
            char_count[char] = char_count.get(char, 0) + 1

    # Sort characters by frequency and then alphabetically
    sorted_chars = sorted(char_count.keys(), key=lambda x: (-char_count[x], x))

    # Calculate the scaling factor for the bars
    max_count = char_count[sorted_chars[0]]
    scale = max_units_on_screen / max_count

    # Generate the bar graph
    result = [f"{char}:{'#' * int(char_count[char] * scale)}" for char in sorted_chars]

    return '\n'.join(result)

# Example usage:
print(count_and_print_graph("aaazzzzRRrTTTtrr", 5))
# Output: "r:#####\nt:####\nz:####\na:###"

print(count_and_print_graph("aaazzzzRRrTTTtrr", 10))
# Output: "r:##########\nt:########\n
```
