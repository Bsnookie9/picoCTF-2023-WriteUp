# Overview
- Tags: `picoCTF 2023` `Forensics` `steganography`
- `100 points`

# Description
Every file gets a flag.
The SOC analyst saw one image being sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye `here`.

# Solution
Download the image file (.png). `Steganography` is the practice of concealing messages or information within other nonsecret text or data. Therefore, this `flag.png` file has a hidden file containing the flag.

![flag](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/54a551ec-c8a8-4fdd-9427-46995ebdb4e3)

We can't use `steghide` to extract information, and steghide doesn't work with PNG files. We can use `binwalk`. Binwalk is a tool for searching binary files, like images and audio files, for embedded hidden files and data. Type the command `binwalk -e flag.png`.

![hide](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/a6a33802-2d96-49f5-9f01-ab8df2efe508)

We can see there is a hidden directory called `secret/` and a file called `flag.png`. We can `ls` to find the folder that binwalk extracted the data and `cd` into the directory which is `_flag.png.extracted`.

![hide(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/68802090-7ff1-48cb-af92-310288058d68)

`ls` to find the `secret/` directory and `cd` into it. `ls` to find the `flag.png` file.

![hide(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/36189998-999d-4197-af69-a391d07017be)

Now we can use the tool `feh` which is a Linux Image Viewer. Type the command `feh flag.png`.

![hide(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/f1cd2054-59b7-4b08-8775-06e0026b6910)

There will be a FEH window that opens with the file showing the flag.

![hide(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/232a76d3-0aec-406a-bc25-7e573610c93e)
