#  Practical UDP Analysis

## UDP Intro

- Connectionless Protocol
- Unreliable Delivery
- Throw it out there and hope that it gets there type delivery
- 8 bytes

#

## The UDP Header Explained

Lesson Downloadable File: [udemy-dhcp.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

UDP Header: Source Port - 2 bytes, Destination Port - 2 bytes, Length, Checksum

DHCP is four packets: DORA
- Discover
- Offer
- Request
- ACK

Packet 1: Where does this packet going to at layer 2
- Broadcast: sending to everybody
- Discover: because we don't have IP address yet, we are discovering who is our DHCP server is.
- Only knows the Client MAC Address

<p align="center"> <img src="https://i.imgur.com/Y5qegzF.png" height="90%" width="90%" alt=""/>

Packet 2: Comes back from the DHCP Server
- Offer: DHCP offered things to me
- Your Client IP Address: 192.168.0.10
- Designed to be relayed
- Have the Renewal time, Rebinding time, Lease time

<p align="center"> <img src="https://i.imgur.com/gf95vHm.png" height="90%" width="90%" alt=""/>

Packet 3: Send it to everybody again
- Request: Telling everyone that you are requesting IP Address of 192.168.0.10
- Request List: Requesting subnet mask, router, domain name server, NTP servers

<p align="center"> <img src="https://i.imgur.com/WJXkFxB.png" height="90%" width="90%" alt=""/>

Packet 4: Acknowledged
- ACK: Server answer back with same IP Address
- Give out same: Renewal time, Rebinding time, Lease time, Subnet mask
- Did not give: DNS address, routerm NTP servers: might need to check out this problem.

<p align="center"> <img src="https://i.imgur.com/5YDPc6H.png" height="90%" width="90%" alt=""/>

#

## Troubleshooting VoIP and Video Streams

Lesson Downloadable File: [udemy-voip.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

VoIP first has to establish the connection or has to create the call.
- Once the call is created, then flips to streaming protocol - RTP
- SIP or session Initiation protocol is how the call gets established.

RTP is bidirectional: to check jitter on RTP
- Display Filter: ip.src == 192.168.5.10 && rtp
  - Packets going from 192.168.5.10 to 192.168.5.11
- Look at the Delta value: Want the value to be close to .020
- Can also add Sequence number as column by expanding Real-Time Transport Protocol
  - If sequence number is skipped then there is a jitter.
- Expand Internet Protocol Version 4 > Expand Differentiated Service Field
  - Can see it's Expedited Forwarding, prioritized traffic
 
<p align="center"> <img src="https://i.imgur.com/ysVGOMW.png" height="90%" width="90%" alt=""/>

Now let's look at the packets going from 192.168.5.11 to 192.168.5.10
- Display Filter: ip.src == 192.168.5.11 && rtp
- There is a lot more jitter everywhere
- Differentiated Service Codepoint is default; not prioritized traffic

<p align="center"> <img src="https://i.imgur.com/5bQVZMa.png" height="90%" width="90%" alt=""/>

