#  Practical TCP Analysis

## TCP Intro

- Handshake
- How Sequence and acknowledgement number works?
- How data ca be retransmitted?
- How TCP window concept works?

#

## Analyzing DNS

Lesson Downloadable File: [udemy-dns.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

- Domain Name System
- Phone book of internet
- Can get the IPv4 or IPv6 address when you have the Domain Name. Vice versa
- Can tell you about the authoritative name servers
- Can tell you about Canonical names

We will only focus at the majority of what we will be looking at end users and their DNS request and response on Wireshark.

- Looking at DNS for frame packet 1
- We can see 1 Question of the query
  - It's giving us only one query: We want udemy.com and Type A host address.
 
<p align="center"> <img src="https://i.imgur.com/7kLB3p2.png" height="90%" width="90%" alt=""/>

- We can see that packet 1 and 3 have a request and response arrow.
  - Conversation filter UDP on packet 1
 
<p align="center"> <img src="https://i.imgur.com/gPpfYUD.png" height="90%" width="90%" alt=""/>

- Looking at packet 3
- A response packet: 1 Question but 2 answers
  - Two type A IPv4 address
 
<p align="center"> <img src="https://i.imgur.com/lGKeFdQ.png" height="90%" width="90%" alt=""/>

- We can make the response time as a column

<p align="center"> <img src="https://i.imgur.com/QpJXwUd.png" height="90%" width="90%" alt=""/>

- This time column, we can use as display filter to see DNS slow response time
  - Display Filter: dns.time > 0.04
  - Only show response time greater than 0.04
  - We can make it as a button to trouble shoot in the future.

<p align="center"> <img src="https://i.imgur.com/eu3EW8b.png" height="90%" width="90%" alt=""/>

#

## TCP Flags

Lesson Downloadable File: [udemy-lecture59only-tcp-flags.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

Frame Packet 6: SYN

- Conversation Filter > TCP 

<p align="center"> <img src="https://i.imgur.com/hU9UxRA.png" height="90%" width="90%" alt=""/>

- Source Port: Your own port; high number client side ephemeral port.
- Destination Port: The port you want to talk to.
- Stream Index: Assigned by Wireshark, a value to every unique 4/2 pull that sees in the PCAP.
  - 4/2 pull = two IPs and two port numbers
- Conversation Completeness: Did we see a handshake?; Did we see data exchanged?; Did we see an end (FIN or RST)
  - Incomplete because we have data, we had handshake, but no tear down
- TCP Segment Length: how much data is actually encapsulated within this packet.
- Sequence Number: Client sent 516328648 (seq number) over to the server = Initial Sequence Number (ISN).
  - Client will begin counting data starting at ISN, with every byte that is sent, the sequence number will go up by one. (ghost byte)
  - Wireshark wipe the big number and start at 0, but the true number is the ISN.
  - Add one then echo back to you.

 
<p align="center"> <img src="https://i.imgur.com/NsobYH4.png" height="90%" width="90%" alt=""/>

Frame Packet 7: SYN/ACK

- Sequence Number = 3971856359
- Acknowledgement number = 516328649

<p align="center"> <img src="https://i.imgur.com/Gt8pRI0.png" height="90%" width="90%" alt=""/>

Frame Packet 8: ACK

- Sequence Number = 516328649
- Acknowledgement number = 3971856360

<p align="center"> <img src="https://i.imgur.com/sr0mvkD.png" height="90%" width="90%" alt=""/>

Flags: Indicates the type of packet that this is

- For packet 6: Only SYN is set to 1
- For packet 7: have SYN and ACK set to 1
- For packet 8: Only ACK is set to 1
- PUSH set to 1: sending data that I do not want you to wait to process, hurry up and process.
- Reset set to 1: basically saying: "I am done hang up the phone"; tearing down connections
- FIN set to 1: both side graceful shutdown; tearing down connections

<p align="center"> <img src="https://i.imgur.com/QhZjveE.png" height="90%" width="90%" alt=""/>

#

## Analyzing TCP Options

- Window: An advertisement of the amount of data that you can send to me at once unacknowledged. You cannot send more than my window will allow
- Maximum segment size: size that I can recieve, just an advertisement, don't have to equal for the 3 way handshake
- Window scale: Allow to multiply window value to much higher number.
  - TCP restricted to 2 bytes value in its TCP header
  - Telling link partner: I know i am saying it's 64240 but you can multiply this by 256 (True Window)
- SACK permitted: Allow to selectively acknowledge non-contiguous data block in TCP

<p align="center"> <img src="https://i.imgur.com/YRAn24F.png" height="90%" width="90%" alt=""/>

#

## FIN vs Resets

Lesson Downloadable File: [udemy-wiresharkintro.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

- FIN = Graceful shutdown
- Resets = abortive release

Looking at Frame 70: Conversation filter > TCP

- This is a graceful shutdown

<p align="center"> <img src="https://i.imgur.com/44BONb1.png" height="90%" width="90%" alt=""/>

Looking at reset flags:

- Display filter: tcp.flags.reset == 1
- Conversation filter > TCP: frame 671

<p align="center"> <img src="https://i.imgur.com/sV732nJ.png" height="90%" width="90%" alt=""/>

We see that packet 660 send a SYN packet looking for port 80.
- Right away we hear a reset come back from 192.168.56.1, saying nope I am not listening
- If you are being probed or scanned, and those scans are actually making it to your endpoint
  - Common whenever you have a SYN for a port that you are not listening on, you send a reset
- If SYN came to us and it hit a firewall, the firewall will not response with the reset.
  - If you have SYN, SYN, SYN, SYN, SYN, SYN without reset = Might be hitting a firewall
  - If you have SYN, SYN, SYN, SYN, SYN, SYN and get a bunch of reset = talking to a true endpoint
 
<p align="center"> <img src="https://i.imgur.com/PHr9RXh.png" height="90%" width="90%" alt=""/>

Looking at the other reset flags:

- Display filter: tcp.flags.reset == 1
- Conversation filter > TCP: frame 719

We see a 3 way handshake, Station sends a reset.
- Full connect scan: SYN, SYN/ACK, ACK then reset.
- Started a connection but don't want to use it.


<p align="center"> <img src="https://i.imgur.com/gocWjmX.png" height="90%" width="90%" alt=""/>

Tips for reset:

- Client saying it was weird, it just disconnected; Go and hunt for resets.
- Strange, application just went away, tried to start up that VPN client and nothing happened.
- TCP reset are good thing add as a button for quick filter to find the resets.
- Resets are not always bad, sometimes endpoints just use them to shut connection down.
  - Look for: was the connection done, data comes as a response and then reset.
- If there is a lot of them or if people are complaining a lot about sudden disruptions in their application
