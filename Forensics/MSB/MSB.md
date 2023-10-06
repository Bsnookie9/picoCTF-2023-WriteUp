# Overview
- Tags: `picoCTF 2023` `Forensics` `steganography`
- `200 points`

# Description
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...
Download the image `here`

# Hints
What's causing the 'corruption' of the image?

# Solution
Download the image. If you first open the image, you'll notice that a majority of the image is pixelated, meaning that the 
most significant bit (MSB) has been altered. If it was the least significant bit (LSB), you most likely wouldn’t notice any difference.

![stego](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/9c540f30-614f-416e-90ce-f124810beb79)

We can use stegsolve to extract the hidden data from the image. If you do not have stegsolve downloaded, go to [this website](https://wiki.bi0s.in/steganography/stegsolve/) and follow the install directions.
Open the terminal and type the command `java -jar stegsolve.jar`.

![steg](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/72eae9a4-56d3-441d-9cfb-4ead5e941532)

A small window will open in the top left corner of your window. Press the `O` key, and it will open to a default size window. Select the PNG file and click `Open`.

![steg(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/23465b45-cb36-40a2-81eb-9cfde2303e1c)

Click `Analyse` in the top menu bar, then click `Data Extract`.   
From here, we will check the `7` boxes for Red, Green, and Blue, as these are the most significant values for the image.   
Then click the `Preview` button, and you’ll get the preview text above.  
Scroll towards the top, and you’ll start to see actual plaintext.   
Click the `Save Text` button and name the file.  
Now open that file and search for `pico`. Here, you’ll find the flag.  

![steg(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/c8819b19-d6a8-4ac3-a850-34dc99540232)
