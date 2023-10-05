# Overview 
- Tags: `picoCTF 2023` `Forensics`
- `200 points`

# Description
Someone might have hidden the password in the trace file.
Find the key to unlock this `file`. `This tracefile` might be good to analyze.

# Hints
Download the pcap and look for the password or flag.
Don't try to use a password cracking tool, there are easier ways here.

# Solution
Download the zip file and the trace file. Use Wireshark to analyze the trace file. Going through the ethernet packets, 
you’ll see the message on the side saying: `is this the flag`, `could the flag have been split`, and `try checking the other file`.

Go to packet 48

![find](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/04eac244-d45a-468b-bbdf-be7af74a0ba6)

Here we see Base64 text. This is most likely the encoded password. Copy the text and use CyberChef to decode it. 
It doesn't decode properly so try adding two A's to the beginning (refers back to the comment `could the flag have been split`)

![find(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/3ba80e2c-38c5-496d-acde-b051bb47ae8d)

Remember, Hint #2 mentions not needing a password cracking tool. This is possibly the password itself. Try using it to unzip the `flag.zip` file.

![find(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/c59633cd-7a30-477c-9494-47ed7ebdc88c)

It worked! Now `ls` to find the unzipped file `flag` and `cat` the file to get the flag.

![find(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/fee0c470-d3c8-4523-9567-ced275291abb)

Flag: `picoCTF{R34DING_LOKd_fil56_succ3ss_cbf2ebf6}`
