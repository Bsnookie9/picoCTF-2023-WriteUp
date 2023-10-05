# Overview
- Tags: `picoCTF 2023` `Cryptography`
- `100 points`

# Description
How about we take you on an adventure on exploring certificate signing requests
Take a look at this CSR file `here`.

# Hints
Download the certificate signing request and try to read it.

# Solution
Download the certificate signing request (CSR) and then `cat` the file to view its contents

![read](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/fcaafb51-a110-420a-b1da-f8b712960e37)

The CSR contains Base64, so use CyberChef to decode the text and find the hidden flag

![read(2)](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/207d8bbb-8854-439f-b2a5-8dcc3c577951)

Flag: `picoCTF{read_mycert_a7163be8}`
