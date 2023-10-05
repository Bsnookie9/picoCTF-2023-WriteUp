# Overview
- Tags: `picoCTF 2023` `General Skills` `bash` `ssh`
- `400 points`

# Description
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.
Additional details will be available after launching your challenge instance.

# Hints
What programs do you have access to?

# Solution
First, SSH into the server

![sp](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/be4f4b82-1fd0-481f-984e-12c114dfa6b3)

Since the spell-check was removed from the previous "special" program, you can type commands without `""`. Using the hint that was given, we need to know what commands we can use. Typing `compgen -c` will find available commands. _Alternatively you can double-tap the tab button_

![sp(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/63c64430-9152-455e-87ee-ec55d0e32f71)

Since `ls` is not a usable command, you must find another way to list the contents of the directory or find other directories available. I found that typing `cd` and then double-tapping the tab buttons works like `ls`

![sp(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/6e2d9f70-7e97-4655-bacc-0f82952a1356)

Here we can see that there are two files and three directories available. `Compgen` already showed us that the `cat` command is not available but we can try using `echo "$(<filename)"`

![sp(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/fdf3ec1d-2c6e-4bb4-8a42-a581f3af9f96)

The files don't contain anything useful, so `cd` to the other directories (with a double tab tap) and do the same echo command. The `abra/` directory contains nothing useful either. Switch to the `ala/` directory.

![sp(6)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/d18dcd25-cb8d-44fe-b058-4ffa5491e952)

Here there are two files: `kazam.txt` and `mode.txt`. Try the same echo command on the `kazam.txt` file: `echo “$(<kazam.txt)”`

![sp(7)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/f6ff1607-b0ca-4b33-806b-72bf8427e03a)

You've found the flag!
