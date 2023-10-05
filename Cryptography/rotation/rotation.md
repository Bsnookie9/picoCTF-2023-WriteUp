# Overview
- Tags: `picoCTF 2023` `Cryptography`
- `100 points`

# Description
You will find the flag after decrypting this file
Download the encrypted flag `here`.

# Hints
Sometimes rotation is right

# Solution
Download the file and use any editor to open the file and grab the encoded flag

![rot](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/e0fc53cf-5488-4421-9edd-817699d164cd)

The name of the challenge gives a hint about a rotation cipher, so use CyberChef to decode the flag. Change the amount of rotations to `-8`

![rot(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/2962e82c-f6ab-440f-9a7a-116f8d3bd189)

Flag: `picoCTF{r0tat1on_d3crypt3d_25d7c61b}`
