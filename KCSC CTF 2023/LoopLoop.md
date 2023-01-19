# CTF Write-Up - Jibberish

## Description

The challenge is a text file called `chall.txt` that contains a string of seemingly random characters. The goal is to make sense of this "jibberish" and find the flag.

## Techniques Used

- Base64 decoding
- String manipulation
- While loop

## Solution

I suspected that the given string in the challenge file might be encoded in Base64, but I was not entirely sure. To confirm my suspicions, I wrote a Python script that reads the contents of the challenge file and decodes the string using the `base64.b64decode()` function. 

Here is the script:

```python
import base64

# Read the challenge file
with open("chall.txt", "r") as f:
    encoded_string = f.read()

# Decode the string
decoded_string = base64.b64decode(encoded_string).decode()

# Print the decoded string
print(decoded_string)
```

After running the script the decoded string still looked like jibberish.

Because of the name of the challange "LoopLoop" I decided to repeat the process of decoding from Base64 several times using a while loop, and also check if the decoded string starts with kcsc before each iteration, and if it does, the loop will stop and print the final decoded string which is the flag. Here is the script:

```python
import base64

# Read the challenge file
with open("chall.txt", "r") as f:
    encoded_string = f.read()

# Decode the string multiple times
while not encoded_string.startswith("kcsc"):
    encoded_string = base64.b64decode(encoded_string).decode()

# Print the final decoded string
print(encoded_string)
```
This script uses the built-in python function `base64.b64decode()` for decoding the base64 encoded string, and the `startswith()` method to check if the decoded string starts with `kcsc` or not, if true it stops the loop and print the flag, if not it continues the loop to decode the string again.

By running this script, I was able to successfully decode the jibberish and find the flag: **`kcsc{b4se64_l00ps_ftw!}`** 

## Conclusion

This challenge required understanding of base64 encoding, string manipulation, and while loops. The script provided was able to find the flag in an efficient manner and make sense of the jibberish.



