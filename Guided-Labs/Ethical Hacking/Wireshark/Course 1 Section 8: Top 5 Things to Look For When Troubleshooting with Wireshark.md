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

Click on the jump to packet icon on the icon bar > Go to packet 1234.

<p align="center"> <img src="https://i.imgur.com/QOOkauu.png" height="90%" width="90%" alt=""/>

On packet 1234: Conversation filter > TCP
- Expand Transmission Control Protocol > Add Calculated Window size as column.

<p align="center"> <img src="https://i.imgur.com/ky4Np6B.png" height="90%" width="90%" alt=""/>

On packet 1600:
- TCP Window Full: the server has filled the client window.

On packet 1599:
- 11680, amount of space that client has in its buffer.

On packet 1600:
- Server says alright 11680 here you go. Filled the buffer, can't send anymore.

On packet 1601: 
- Client come back and says I got room for 2920.

On packet 1602: 
- Server sends 2920 in 1 packet (probably send in 2 packets by segmenting into 1460s)

On packet 1603:
- Client come back and say I am full; ZeroWindow. Telling server it can't send anything else.
- The application is not scooping the data out fast enough or TCP is not able to push it to the application.

On packet 1605:
- .8 second later, window update where the client says: okay application. Here is a new window, just cleared out some data, now i have enough space to receive more data.

<p align="center"> <img src="https://i.imgur.com/LcjoT3J.png" height="90%" width="90%" alt=""/>

This is not a network, application, or server problem at all.
- This is a client problem: Client ran out of a TCP window.
  - TCP buffer started pooling data. More data was coming in and it started pooling until client had to stop it with ZeroWindow, no more space for server to send more data.

Large file transfers:
- Moving data from one point to another: important that each TCP endpoint is able to keep up with the ingress traffic
  - You will be able to see that by keeping an eye on window size.
- Make sure to catch the TCP handshakes: possible that this window size is actually multiplied to much higher value.
- Keep eyes out for low TCP recieve windows.


#

## 5. Network/Application Disconnects - TCP Resets

Lesson Downloadable File: [udemy-63-connectivityproblems.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

Connectivity Problems: Reset problems
- Where a client can't connect to a server.
- Open VPN an can't VPN to another device.
- Mid-stream and my application just drops.

There is a lot of reset on the pcap.

Let's look at Packet 18: Conversation filter > TCP
- SYN > RST/ ACK > RST / ACK > RST / ACK then it works fine.

<p align="center"> <img src="https://i.imgur.com/MFAHm65.png" height="90%" width="90%" alt=""/>

Why does it do that?
- Port is down on a server or firewall blocking it: will never work.
- Wonder where is the resets coming from? - Coming from endpoints or somewhere closer?

We will look at all the reset flags:
- Display Filter: tcp.flags.reset == 1
- Look at the source IP sending resets back to clients
  - A lot of different IPs: This tells us it can't be that all websites are resets at the similar time.
 
<p align="center"> <img src="https://i.imgur.com/Nd8NFxK.png" height="90%" width="90%" alt=""/>

Let's look back at the first SYN.
- Packet 18: Conversation Filter > TCP
- Look at the reset packet 19.
  - See how far away is this coming from: IP TTL
  - Expand Internet Protocol Version 4 > Add Time to Live as Column.
 
<p align="center"> <img src="https://i.imgur.com/E1EW1ok.png" height="90%" width="90%" alt=""/>

Inspecting TTL:
- Packet 18: SYN with 128 TTL goes out; 64 TTL = unrouted
- Packet 19: 64 hop count for reset; 128 TTL = unrouted
- Packet 108: 128 TTL = unrouted
- Packet 109: 64 TTL = unrouted
- Packet 179: 128 TTL = unrouted
- Packet 183: 244 TTL = 11 hops away.

<p align="center"> <img src="https://i.imgur.com/OqsluiS.png" height="90%" width="90%" alt=""/>

The resets are coming from unrouted devices.
- MAC address matters:
- Packet 19: Expand Ethernet II > Look at MAC Addresses: True sender of the reset.
  - Sonic Wall Firewall.
- SYN (18) > Firewall resets (19) > SYN (108) > Firewall resets (109) > SYN (179) > no problem

<p align="center"> <img src="https://i.imgur.com/3rKsCKC.png" height="90%" width="90%" alt=""/>

Story:

Looked at the Sonic Wall Firewall; found out that the company had grown much larger than the firewall can handle.
- Outgrew the capabilities of the Firewall
- Turn out there is a setting on the firewall: number of connections per user; gave a ceiling to the number of TCP connections that each user was able to have
  - Set to 100.
- Once you burned up your 100 TCP connections and you tried to start a new one, the firewall would reset you.
- So maybe one of your old connection would time out and you would get some space in your count.
- So eventually you will be able to send out SYN then establish the connection.

Tips:
- Pay attention to resets and see where are they coming from.
- Look at TTLs on your resets:
  - Possible that is sending that reset back to you; could be a middleware box, proxy, load balancer, firewall.
