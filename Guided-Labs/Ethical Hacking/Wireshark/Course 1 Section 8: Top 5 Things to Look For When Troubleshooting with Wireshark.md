# Top 5 Things to Look For When Troubleshooting with Wireshark

## 1. Slow Application Response Time

Lesson Downloadable File: [udemy-wasitnetwork.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

- First thing to look at is the Delta time
  - The Network Trip time: amount of time between client and server and back
- Second thing to look at is how long does it take for an application to begin responding
  - Can see this by expanding Hypertext Transfer Protocol: Time Since Request
  - Example: Packet 11
  - Display filter: http.time = the amount of response time or how long it took for a web server to respond
 
<p align="center"> <img src="https://i.imgur.com/lvUP3FP.png" height="90%" width="90%" alt=""/>

We can use that filter to see if there is ever a response after a request longer than two seconds.

<p align="center"> <img src="https://i.imgur.com/I1REIG2.png" height="90%" width="90%" alt=""/>


Lesson Downloadable File: [udemy-wasitnetwork.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

