## [Binary to Text (ASCII) Conversion](https://www.codewars.com/kata/5583d268479559400d000064/python)

- Write a function that takes in a binary string and returns the equivalent decoded text (the text is ASCII encoded).

- Each 8 bits on the binary string represent 1 character on the ASCII table.

- The input string will always be a valid binary string.

- Characters can be in the range from "00000000" to "11111111" (inclusive)

- Note: In the case of an empty binary string your function should return an empty string.

#### Solution:

```python
def binary_to_string(binary):
    if not binary:
        return ""
        
    # Split the binary string into 8-bit chunks
    chunks = [binary[i:i+8] for i in range(0, len(binary), 8)]
    
    # Convert each 8-bit chunk into its ASCII equivalent character
    chars = [chr(int(chunk, 2)) for chunk in chunks]
    
    # Join the characters to form the final string
    return "".join(chars)


print(binary_to_string("01100001")) # 'a'
print(
  binary_to_string("01001011010101000100100001011000010000100101100101000101")
) # 'KTHXBYE'


```
