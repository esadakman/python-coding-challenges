## CamelCase Method

- Write simple .camelCase method (camel_case function in PHP, CamelCase in C# or camelCase in Java) for strings. All words must have their first letter capitalized without spaces.

For instance:

```python
camelcase("hello case") => HelloCase
camelcase("camel case word") => CamelCaseWord
```

Solution 1:

```python 
def camel_case(str):
  return str.title().replace(" ", "")

print(camel_case("test case")) "TestCase"
```
Solution 2:

```python 
def camel_case(str):
  return sub(r"/(?:^\w|[A-Z]|\b\w)/g", " ", str).title().replace(" ", "") if len(str) > 0 else ""  

print(camel_case("test case")) "TestCase"
```