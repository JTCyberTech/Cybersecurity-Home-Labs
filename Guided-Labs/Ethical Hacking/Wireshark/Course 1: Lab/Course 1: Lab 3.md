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


7. How many packets have the SYN bit set?


8. How many TCP Resets are in the pcap?


9. How many TCP SYN/ACKs are in the pcap?


10. Are any SYN/ACKs coming from the 10.0.2.15 station? Y/N?

