# Overview
- Tags: `picoCTF 2023` `Forensics` `email`
- `100 points`

# Description
Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam.
Can you help us identify whose mail server the email actually originated from?
Download the email file `here`. Flag: picoCTF{FirstnameLastname}

# Hints
whois can be helpful on IP addresses also, not only domain names.

# Solution
Download the .eml file and open it using either a browser or a specific mail application, such as Thunderbird.

![who](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/a4f53b3d-1cbe-43f8-8028-0e41ea47fff6)

Since I'm using Thunderbird, I clicked on the top right button `More` and clicked `View Contents`. If using a browser, do the same thing by clicking `view contents`. Then scroll down until you find the section that states:  `Received: from mail.onionmail.org`. 

![who(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/95464744-9946-4f3a-83e5-4f2cff3ae36b)

Here we can see the client's IP address. This, however, is not their real IP address as it is hidden through onionmail's servers. 
To find the real identity of this scammer, we can do a reverse lookup using the `whois` command (the hint also mentions this instead of doing a reverse domain lookup).
Type the command `whois 173.249.33.206`.

![who(3)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/808cbf32-0850-483f-b418-0ab3afbae60a)

We then will get the results of the scammer's real identity: `Wilhelm Zwalina`.

![who(4)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/fa16cef1-9293-446b-845d-568222cde634)

Flag: `picoCTF{WilhelmZwalina}`
