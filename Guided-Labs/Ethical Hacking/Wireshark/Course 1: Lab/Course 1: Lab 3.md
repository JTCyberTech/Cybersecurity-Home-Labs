# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 3: Lab 3 - Creating Display Filters in Wireshark

- Name of the file downloaded from Udemy: udemy-displayfilters.pcapng
  - Uploaded both csv and pcapng files to GitHub: [Lab 3](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201%3A%20Lab/Downloadable%20Lab%20Files/Lab%203)
 
Questions for this assignment

1. How many DNS packets are in the trace file?

- 228 packets
- Display Filter: dns

<p align="center"> <img src="https://i.imgur.com/qx0Wkhy.png" height="90%" width="90%" alt=""/>

2. How many DNS packets contain the word "Udemy"? (Regardless of case)

- 20 Packets
- Display Filter: dns && frame matches "Udemy"
  - Can also be: dns and frame matches "Udemy", dns matches "Udemy"

<p align="center"> <img src="https://i.imgur.com/C9DFHA5.png" height="90%" width="90%" alt=""/>

3. How many HTTP packets are in the pcap?

- 66 packets
- Display Filter: http
  - OCSP = Online Certificate Status Protocol; HTTP is the highest layer protocol for OCSP.

<p align="center"> <img src="https://i.imgur.com/jgIFyow.png" height="90%" width="90%" alt=""/>


4. Set a filter for TCP port 80. How many packets meet that filter?

- 211 packets
- Display Filter: tcp.port == 80


<p align="center"> <img src="https://i.imgur.com/gTfNQUs.png" height="90%" width="90%" alt=""/>


5. How many packets are in the top IP conversation? Set a filter for this conversation.

- In order to find the top IP Conversation:
  - Statistics > Conversations
  - IPv4 > Click on Bytes to sort by largest Conversation
 
- Answer: 406 packets
 
<p align="center"> <img src="https://i.imgur.com/M6MQTP5.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/fDakHnb.png" height="90%" width="90%" alt=""/>

- In order to set a filter for the conversation:
  - Right click on the packet > Apply as Filter > Selected > A <-> B
  - Display Filter: ip.addr==10.0.2.15 && ip.addr==104.16.65.85

<p align="center"> <img src="https://i.imgur.com/NvWjfmb.png" height="90%" width="90%" alt=""/>

6. In the top IP conversation, how many packets have the word "Udemy", regardless of case?

- In order to filter packet with the word Udemy, we have to take the filter from last question: ip.addr==10.0.2.15 && ip.addr==104.16.65.85
  - (ip.addr==10.0.2.15 && ip.addr==104.16.65.85) && frame matches "Udemy"
 
- Answer: 3 packets

<p align="center"> <img src="https://i.imgur.com/8BrBw5S.png" height="90%" width="90%" alt=""/>

7. How many packets have the SYN bit set?

- SYN bit packets = packets that have the flag SYN
  - Display Filter: tcp.flags.syn == 1

- Answer: 146 packets 

<p align="center"> <img src="https://i.imgur.com/Yb6xkGm.png" height="90%" width="90%" alt=""/>

8. How many TCP Resets are in the pcap?

- Display Filter: tcp.flags.reset == 1
- Answer: 9 packets

<p align="center"> <img src="https://i.imgur.com/1H9xgtC.png" height="90%" width="90%" alt=""/>

9. How many TCP SYN/ACKs are in the pcap?

- Display Filter: tcp.flags.syn == 1 && tcp.flags.ack == 1
  - We can also do: tcp.flags == 0x012
- Answer: 73 packets

<p align="center"> <img src="https://i.imgur.com/Jv5ROzm.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/3yoUs0c.png" height="90%" width="90%" alt=""/>

10. Are any SYN/ACKs coming from the 10.0.2.15 station? Y/N?

- Coming from 10.0.2.15 meaning ip.src == 10.0.2.15
  - Display Filter: tcp.flags == 0x012 && ip.src == 10.0.2.15
 
- Answer: No

<p align="center"> <img src="https://i.imgur.com/ZUMiwnY.png" height="90%" width="90%" alt=""/>

