# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 5: Lab 5 - Is it the Client, Network, or Server? Can You Isolate the Problem?

- Name of the file downloaded from Udemy: udemy-wasitnetwork.pcapng
  - Uploaded both csv and pcapng files to [GitHub](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201%3A%20Lab/Downloadable%20Lab%20Files/Lab%206)
 
Questions for this assignment

1. This pcap was taken physically on the client PC. What is the network roundtrip time between the client and server? Round to the nearest millisecond. Only enter the number of milliseconds.

- 97 milliseconds

<p align="center"> <img src="https://i.imgur.com/3RJjXN6.png" height="90%" width="90%" alt=""/>


2. The client sends a request to the server in packet 4 and 5. Did the server receive these packets? What is the relative ACK number that the server returns in the next packet?

- Yes the server recieve these packets
- Relative ACK number that the server returns in the next packet = 1496

<p align="center"> <img src="https://i.imgur.com/Olf0mcP.png" height="90%" width="90%" alt=""/>

3. What happens next? Who sends the keep alive? Client or Server?

- Client sends the keep alive to server at packet 7 and 9. Finally at packet 11 the server sends the data that client requested.

<p align="center"> <img src="https://i.imgur.com/ggVCG6Q.png" height="90%" width="90%" alt=""/>

4. How long does it take to send this packet (in full seconds)?

- 45 Seconds

<p align="center"> <img src="https://i.imgur.com/9pazgB3.png" height="90%" width="90%" alt=""/>

5. Does the server TCP stack respond? Y/N

- Yes

6. How long before another keep-alive is sent (in full seconds)?

- 45 seconds

<p align="center"> <img src="https://i.imgur.com/nuofyJj.png" height="90%" width="90%" alt=""/>

7. Has the application responded yet at this point? Y/N

- No

8. At last, how long does it take the application to respond to the request? What is the application response time in full seconds? (Round to the nearest second)

- 109 seconds

<p align="center"> <img src="https://i.imgur.com/wdtEO1P.png" height="90%" width="90%" alt=""/>
  
9. Is this problem due to the client, network, or server?

- Server delay
