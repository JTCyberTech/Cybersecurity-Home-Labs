# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 1: Lab 1 - Hands-On with Wireshark

- Name of the file downloaded from Udemy: udemy-wiresharkintro.pcapng
  - Uploaded both csv and pcapng files to GitHub

Questions for this assignment

1. How many packets were captured in this trace file?

- 2186 packets

<p align="center"> <img src="https://i.imgur.com/MSBzfRi.png" height="90%" width="90%" alt=""/>

2. What protocol does packet number 8 contain? (The highest-layer protocol)

- HTTP

<p align="center"> <img src="https://i.imgur.com/1H2weFC.png" height="90%" width="90%" alt=""/>

3. If you just installed Wireshark for the first time, what is the name of the profile you are using? (bottom right corner)

- Default

<p align="center"> <img src="https://i.imgur.com/rV76SEB.png" height="90%" width="90%" alt=""/>

4. Look at packet number one - what is the source IP address in this packet?

- Source IP Address: 192.168.56.102

<p align="center"> <img src="https://i.imgur.com/0Y5ZbPI.png" height="90%" width="90%" alt=""/>

5. What is the source TCP port in this same packet?

- Source TCP port: 39294

<p align="center"> <img src="https://i.imgur.com/nSouJ7s.png" height="90%" width="90%" alt=""/>

6. What TCP flag is set in this packet?

- TCP flag: SYN

<p align="center"> <img src="https://i.imgur.com/Xx2xawn.png" height="90%" width="90%" alt=""/>

7. What is the frame number of the next packet in this TCP conversation?

- Next packet of this TCP Conversation: Packet 6
- Second step of three way handshake: SYN, ACK

<p align="center"> <img src="https://i.imgur.com/2LG1C4K.png" height="90%" width="90%" alt=""/>

8. Can you set a filter for this TCP conversation? How many packets do you get?

- Right click Packet 1 > Conversation Filter > TCP
- Look at the bottom and see how many packets are in the "displayed".
- Packets: 51

<p align="center"> <img src="https://i.imgur.com/kW10nCU.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/FEvRU0h.png" height="90%" width="90%" alt=""/>
