# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 5: Lab 5 - Configuring the Wireshark Interface

- Name of the file downloaded from Udemy: udemy-strangescan.pcapng
  - Uploaded both csv and pcapng files to [GitHub](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201%3A%20Lab/Downloadable%20Lab%20Files/Lab%205)
 
Questions for this assignment

1. How many unique IP hosts do we see in this pcap?

- 5868 Unique IP Hosts
- Statistics > Endpoints > IPv4

<p align="center"> <img src="https://i.imgur.com/p3pNuDP.png" height="90%" width="90%" alt=""/>

2. How many packets are in the top IP conversation?

- 32 packets are in the top IP Conversation
- Statisitics > Conversations > IPv4 > Sort by Packets

<p align="center"> <img src="https://i.imgur.com/0rGN3tW.png" height="90%" width="90%" alt=""/>

3. What country is the 62.189.238.32 endpoint communicating from? (Full country name)

- United Kingdom
- Display Filter: ip.addr == 62.189.238.32
- Expand Internet Protocol Version 4 > Expand Source GeoIP

<p align="center"> <img src="https://i.imgur.com/kz0rst6.png" height="90%" width="90%" alt=""/>

4. Can you work out how to filter the hosts coming from Turkey? How many packets do you find after filtering for Turkey? (hint: ip.geoip.country_iso==?)

- 362 Packets
- Display Filter: ip.geoip.src_country_iso == "TR"

<p align="center"> <img src="https://i.imgur.com/pTMRdAQ.png" height="90%" width="90%" alt=""/>

5. Look at packet 1 - what is the IP TTL for this packet?

- TTL = 123

<p align="center"> <img src="https://i.imgur.com/DX0LEZZ.png" height="90%" width="90%" alt=""/>

6. What is the IP Identification number for this packet?

- 256

<p align="center"> <img src="https://i.imgur.com/aRTLeFr.png" height="90%" width="90%" alt=""/>

7. Look at packet 7, which appears to be coming from the same subnet. What is the IP Identification number?

- 256

<p align="center"> <img src="https://i.imgur.com/RkryVzg.png" height="90%" width="90%" alt=""/>

8. Add IP TTL as a column and filter for all packets coming FROM the 212.252.0.0/16 subnet ranges. (Enter OK as the answer)

- Display Filter: ip.src == 212.252.0.0/16  

<p align="center"> <img src="https://i.imgur.com/m7IqEjV.png" height="90%" width="90%" alt=""/>

9. Does the IP TTL change for any of these packets? Y/N

- N

10. Add the IP ID as a column. Does the IP ID change for any of these packets? Y/N

- N

11. Do you think these packets could be spoofed IP's? Y/N

- Y
