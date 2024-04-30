# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 4: Lab 4 - Analyzing a Packet From Multiple Capture Points

- Name of the file downloaded from Udemy: **udemy-client-slowfiledownload.pcapng** and **udemy-server-slowfiledownload.pcapng**
  - Uploaded both csv and pcapng files to GitHub: [Lab 4](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201%3A%20Lab/Downloadable%20Lab%20Files/Lab%204)
 
Questions for this assignment

1. Focus on packet number two and answer the following questions. What is the destination MAC address? (Use format xx:xx:xx:xx:xx:xx)

- 00:00:0c:0c:00:0e

<p align="center"> <img src="https://i.imgur.com/pkyfBfT.png" height="90%" width="90%" alt=""/>


2. What is the source MAC in this packet?

- 00:0c:29:65:3b:25

<p align="center"> <img src="https://i.imgur.com/njS4gXj.png" height="90%" width="90%" alt=""/>

3. What is the IP identification number? (Use format xxxxxx with no commas)

- 0x7e73 (32371)

<p align="center"> <img src="https://i.imgur.com/dP4Rf3A.png" height="90%" width="90%" alt=""/>

4. What is the IP Time To Live?

- 128

<p align="center"> <img src="https://i.imgur.com/SwZUZQ6.png" height="90%" width="90%" alt=""/>

5. What is the Source IP?

- 192.168.1.10

<p align="center"> <img src="https://i.imgur.com/yqTJJlQ.png" height="90%" width="90%" alt=""/>

6. Now change pcaps to the server side. Open udemy-server-slowfiledownload.pcapng. Which packet corresponds to the packet we were analyzing on the client side? What is the frame number?

- Frame 11
- Same TCP port number: 49844
- Same Identification number: 0x7e73 (32371)

<p align="center"> <img src="https://i.imgur.com/EkpUWvT.png" height="90%" width="90%" alt=""/>


7. Focus on this frame. What is the source MAC?

- 00:00:0c:0c:00:0e

<p align="center"> <img src="https://i.imgur.com/wTMDdoS.png" height="90%" width="90%" alt=""/>

8. What is the destination MAC?

- 00:06:5b:00:02:ff

<p align="center"> <img src="https://i.imgur.com/s8XApwq.png" height="90%" width="90%" alt=""/>


9. What is the IP ID?

- 0x7e73 (32371)

<p align="center"> <img src="https://i.imgur.com/WgfqfCq.png" height="90%" width="90%" alt=""/>

10. What is the IP TTL?

- 127

<p align="center"> <img src="https://i.imgur.com/rEJB2ub.png" height="90%" width="90%" alt=""/>

11. How many routers did this packet go through?

- 1 router; since TTL is 127. 128 - 127 = 1

12. Was there a NAT (Network Address Translation) along the path? Y/N

- No, because the Source Address and Destination Address did not change.

<p align="center"> <img src="https://i.imgur.com/jsm06UI.png" height="90%" width="90%" alt=""/>
