# Overview
- Tags: `picoCTF 2023` `Forensics` `steganography`
- `300 points`

# Description
Do you recognize this cyberpunk baddie? We don't either. AI art generators are all the rage nowadays, which makes it hard to get a reliable known cover image. 
But we know you'll figure it out. The suspect is believed to be trafficking in classics. 
That probably won't help crack the stego, but we hope it will give motivation to bring this criminal to justice!
Download the image `here`.

# Hints
- Something doesn't quite add up with this image...
- How's the image quality?

# Solution
Download the image and check the type of file that it is with the `file` command

![word](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/310ada90-7302-477d-baff-cce30cb1a2ca)

Now type the command `od -bc output.bmp` to look at the packet headers

![word(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/103fdb7c-bf33-4f45-a1ed-21ad75d68de8)

You can see here that `PK` is lower in the output, meaning there is a zip file. However, the stuff before it needs to be removed. Use [this script](https://pandhack.fr/content/files/2023/05/extract_zip.py).
* This script extracts every second byte from the BMP image file and writes the extracted bytes to a new binary file.

![word(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/51569f03-42b5-4a3a-aa41-e629bed31e33)

Run the `file` command again to see the new file

![word(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/aa8adbee-b0fc-44a7-be9c-417bd2b9c17d)

Now we can use binwalk to extract the data: `binwalk -e extracted.txt`.

![word(5)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/7acb393a-1f2e-4ed4-8d9b-7fc87dc401ee)

Here, we can see the file `ZnJhbmtlbnN0ZWluLXRlc3QudHh0`.  
First `cd` into the directory that binwalk extracted the file. Then, type this command: `cat ZnJhbmtlbnN0ZWluLXRlc3QudHh0 | grep pico`.  

![word(6)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/619bd108-b0c0-41d4-8e67-003c7a4b3a66)

There is the flag: `picoCTF{w0rd_d4wg_y0u_f0und_5h3113ys_m4573rp13c3_5eadc23e}`
