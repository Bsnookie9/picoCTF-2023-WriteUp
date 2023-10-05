# Overview 
- Tags: `picoCTF 2023` `Foreniscs` `pcap`
- `100 points`

# Description
How about some hide and seek heh?
Download this `file` and find the flag.

# Solution
Download the PCAP file. Open the file using Wireshark (packet capture tool). You can do this by going to File...Open...then browse to the location of the pcap file. Once the file is open in Wireshark, you can search for the beginning part of the flag `picoCTF{`. You can do this by going to Edit...Find Packet. Next, switch `Packet list` to `Packet bytes` to get the packet contents (bytes). Now switch `Display filter` to `String`, as you are searching for a string.

![pcap](https://github.com/Bsnookie9/picoCTF-2023-WriteUp/assets/106827110/e9266210-5ed2-43bc-908d-55f16c06feea)

Flag: `picoCTF{P64P_4N4L7S1S_SU55355FUL_4d72dfcc}`
