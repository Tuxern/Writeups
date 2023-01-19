# CTF Write-Up - LoopLoop

## Description

The challenge is a text file called chall.txt which contains the string "xyz"

## Techniques Used

- Base64 decoding
- Repetition of decoding

## Solution

I suspected that the given string "xyz" might be encoded in Base64, so I tried to decode it using cyberchef's "from base64" function. 
However, the result was another string that still looked like Base64 encoded. 

After looking at the title of the challenge "LoopLoop", I decided to repeat the process of decoding from Base64 several times.
After doing this a couple of times, the flag was revealed: 