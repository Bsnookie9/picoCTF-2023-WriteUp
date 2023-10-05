# Overview
- Tags: `picoCTF 2023` `General Skills` `man`
- `100 points`

# Description
There's an interesting script in the user's home directory
Additional details will be available after launching your challenge instance.

# Solution
First, SSH into the server

![use](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/af8598eb-1245-436c-bfe7-2fe745ff587f)

`ls` to list any files, directories, etc.

![use(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/ed9cb66d-852d-4dfd-afc3-9c5b2d602c6e)

There's a file called `useless`, so run the script `./useless`

![use(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/4317cd16-6f10-4578-ae94-e7f81b6baf61)

It outputs "Read the code first", so `cat` the file. _Alternatively, you can use `nano` or another editor_

![use(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/514f739a-9164-45a3-9516-3a83dc125aa5)

The code mentions reading the manual, so open the manual using the `man` command

![use(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/3a75ca71-07aa-496f-9095-778f353f8436)

Here the flag can be found: `picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6194}`
