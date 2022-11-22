## CamelCase Method

- Write simple .camelCase method (camel_case function in PHP, CamelCase in C# or camelCase in Java) for strings. All words must have their first letter capitalized without spaces.

For instance:

```python
camelcase("hello case") => HelloCase
camelcase("camel case word") => CamelCaseWord
```

Solution:

```python
from re import sub
def camel_case(s):
  s = sub(r"(_|-)+", " ", s).title().replace(" ", "")
  return ''.join([s[0].upper(), s[1:]])

print(camel_case("test case")) "TestCase"
```