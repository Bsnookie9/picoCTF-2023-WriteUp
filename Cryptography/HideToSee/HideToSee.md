# Overview
- Tags: `picoCTF 2023` `Cryptography`
- `100 points`

# Description
How about some hide and seek heh?
Look at this image `here`.

# Hints
Download the image and try to extract it

# Solution
Download the jpeg file. Based on the hint, we should expect something to be hidden in the image file. Use `steghide` to extract it: `steghide extract -sf atbash.jpg` and there is no passphrase, so just hit ENTER

![hide](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/7edb9afc-4515-49e3-9576-9c57ac96ba84)

Now `cat` the "encrypted.txt" file to find the encoded flag

![hide(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/907f8dd0-1aa6-42ac-b4fb-5aef98ac0c3b)

Since the flag is encoded, with Atbash, use CyberChef to decode the flag

![hide(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/2873be8d-ab64-4e5a-b2bb-d35b6a3cf34f)

Flag: `picoCTF{atbash_crack_1f84d779}`
