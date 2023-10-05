# Overview
- Tags: `picoCTF 2023` `General Skills` `vim`
- `100 points`

# Description
Can you read files in the root file?
Additional details will be available after launching your challenge instance.

# Solution
First, SSH into the server `ssh -p {port #} picoplayer@saturn.picoctf.net` and enter the password

Run the command `sudo -l` to find out what commands you have as the user

![permissions](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/9894566a-a929-469c-9391-69c0c437455b)

You can use the vi editor, so as a root user, you can run vi on any file

Create a file where you can write the script in command mode to give yourself root access `vi root`

Now hit the ESC key and type `:!/bin/bash`. Now you have root access

![permissions(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/9d8a42bd-9033-42e1-aadf-d9fda4d13d56)

Run `ls -l` commands and change directories `cd` until you find the `challenge/` directory which is in the `/` directory

![permissions(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/58b0a254-9e47-4622-ae4f-fa1aec866ca9)

You’ll find a file called `metadata.json`. 

![permissions(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/5b8a0fbe-747e-4a34-825a-a86bc2898b25)

Run the vi command to view the file contents: `vi metadata.json`

![permissions(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/d937c7cf-09cd-436b-a241-03702a37d90b)

There is the flag: `picoCTF{uS1ing_v1m_3dit0r_1cee9dcb}`
