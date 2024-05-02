# Top 5 Things to Look For When Troubleshooting with Wireshark

## 1. Slow Application Response Time

Lesson Downloadable File: [udemy-wasitnetwork.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

Looking at Open web

- First thing to look at is the Delta time
  - The Network Trip time: amount of time between client and server and back
- Second thing to look at is how long does it take for an application to begin responding after a handshake
  - Can see this by expanding Hypertext Transfer Protocol: Time Since Request to response
  - Example: Packet 11
  - Display filter: http.time = the amount of response time or how long it took for a web server to respond
 
<p align="center"> <img src="https://i.imgur.com/lvUP3FP.png" height="90%" width="90%" alt=""/>

We can use that filter to see if there is ever a response after a request longer than two seconds.
- Display filter: http.time > 2

<p align="center"> <img src="https://i.imgur.com/I1REIG2.png" height="90%" width="90%" alt=""/>


Lesson Downloadable File: [udemy-displayfilters.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

To look at secure web; encrypted with TLS

- Look at packet 15: Conversation filter > TCP
  - We can see conversation between client (10.0.2.15) and server (104.16.65.85) going over TLS.

<p align="center"> <img src="https://i.imgur.com/I1REIG2.png" height="90%" width="90%" alt=""/>

- We want to look at the delta times.
- 0.02 to 0.03 is probably network round trip time (packet 16, 20, 30)
- Packet 34 is server responding back to client.

<p align="center"> <img src="https://i.imgur.com/MSO1OZk.png" height="90%" width="90%" alt=""/>

Sorting the delta times

- Be careful blaming the client for slowness.
  - Packet 1658 can be client was not interacting with server. (Prompt: Enter password).
 
<p align="center"> <img src="https://i.imgur.com/WL9znvf.png" height="90%" width="90%" alt=""/>

Keep an eye using delta time to look for the amount of response time you get from servers.
- You want to see from the server and see a very long response times.

We can add a column:
- Expand Transmission Control Protocol > Expand Timestamps > Add "Time since previous frame in this TCP Stream" to column.
- This shows the time between previous packet from this one.

<p align="center"> <img src="https://i.imgur.com/FaEQjpe.png" height="90%" width="90%" alt=""/>

With this column, we can see:
- 23 seconds is the longest time between 2 packets in this whole entire packet.
  - But it's from clients side delays.
 
<p align="center"> <img src="https://i.imgur.com/Qh3HigY.png" height="90%" width="90%" alt=""/>

Using display filter to find server side
- Display filter: !ip.src==10.0.2.15
- Sort by Time since previous frame in this TCP stream
- We might want to investigate this

<p align="center"> <img src="https://i.imgur.com/TPDDaO5.png" height="90%" width="90%" alt=""/>

#

## 2. High Network Latency

Lesson Downloadable File: [udemy-lecture59only-tcp-flags.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

High network latency = A lot of latency between the two endpoints

- Looking at packet 6: Conversation filter > TCP
  - Example of slow file download.
- First thing to do when checking out handshake:
  - Look at network round trip time: delta time for SYN/ACK; packet 7
  - 40 millisecond, see how often do we see the 40 millisecond. (Once is okay, but 1000x is human noticeble delay)
 
<p align="center"> <img src="https://i.imgur.com/XzyU0Az.png" height="90%" width="90%" alt=""/>

SMB is very chatty application
- A lot of turns: clients doing a close, get info, create request, find request.
- Every time it sends a request, it has to wait for network round trip time.

To measure beginning to TCP segment length is larger:
- Segment length larger = begin file transfer.
- Right click on packet 6 > Set/Unset Time Reference
  - Start a stopwatch on first packet; packet 6.

<p align="center"> <img src="https://i.imgur.com/57reMdR.png" height="90%" width="90%" alt=""/>

Segment length is larger at packet 90.
- Waited 3.6 second to begin file transfer.

<p align="center"> <img src="https://i.imgur.com/eZHmwXP.png" height="90%" width="90%" alt=""/>

When working with SMB, there is a lot of latency
- Not network's fault
- How often is the application experiencing that latency.

#

## 3. Network Packet Loss

Lesson Downloadable File: [udemy-lecture59only-tcp-flags.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

- Packet loss kills applications
- When something is lost, things need to be retransmitted.

Looking at packet 1023

- Expand Transmission Control Protocol > Expand SEQ/ACK Analysis
  - Expand everything inside
- Shows all expert information: Previous segment not captured.
  - Apply this to the display filter: "tcp.analysis.lost_segment"
 
<p align="center"> <img src="https://i.imgur.com/X7RGbxD.png" height="90%" width="90%" alt=""/>

We see that there are 4 packets that has "TCP Previous segment not captured"; packet loss.
- Can see pattern, what is the distance or gap in sequence number, when I see this flag.
- 2 things to cause packet loss: congestion or link level errors

<p align="center"> <img src="https://i.imgur.com/zfPMUeQ.png" height="90%" width="90%" alt=""/>

#

## 4. Slow File Transfers - TCP Window Problems

Lesson Downloadable File: [udemy-displayfilters.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

Problem at the TCP layer
