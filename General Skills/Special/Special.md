# Overview
- Tags: `picoCTF 2023` `General Skills` `bash` `ssh`
- `300 points`

# Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.
Additional details will be available after launching your challenge instance.

# Hints
Experiment with different shell syntax

# Solution
First, SSH into the server

![sp](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/cec6ed56-d193-4b12-b052-09343c342fa3)

Here you can start trying different commands like `ls`, `pwd`, `grep`, etc. 

![sp(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/93fd5753-965c-4f26-8a8b-8e21fa2715fc)

You'll see the special program is capitalizing and spell-checking the commands instead of completing them. 

Even trying `/`, `~`, and `bash` does not return what would be expected

![sp(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/ee6bcbcf-36d5-42ed-8834-806e7b2de7ab)

Try different syntax such as `" "` so the program will recognize the commands. For example `"pwd"` prints the working directory

![sp(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/fdd3aa6d-dd58-46f4-bf01-9142bd24108d)

`"grep"` outputs the expected usage statement of other expected arguments

![sp(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/ede4a5f3-e1df-4f14-83a6-99f902ee6843)

Try bringing up the help menu for grep using the command `"grep" -help`

![sp(6)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/dfdfdd9e-837b-4f06-aca7-2b6b78a82daa)

This doesn't work, so try both statements with quotes `"grep" -"help"`

![sp(7)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/d35fc436-2720-4831-910a-3131a591176e)

This works by showing the usages and possible arguments with the `grep` command. Now try using `grep` recursively: `"grep" -"recursive"`. A recursive grep is a tool in the bash shell that searches for text in multiple files, including files in subdirectories. Since we're searching for the flag `picoCTF`, we can quickly find the file it rests in

![sp(7)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/e3e2518c-5b4d-4380-848e-6643746a89ed)

The flag rests inside the `blargh/flag.txt` file





