# Practical IP Analysis

## Digging Deeper into the IP ID

Adding Identification number to column is useful

- Expand Internet Protocol Version 4
- Right click Identification > Apply as column

<p align="center"> <img src="https://i.imgur.com/GRUV1VC.png" height="90%" width="90%" alt=""/>

With the Identification number, we can see the order of the packets

- Packet 2 with 0x7e73 (32371) > packet 4 with 0x7e74 (32372) > packet 5 with 0x7e75 (32373) > ..

- Packet 3 with 0x2971 (10609) > packet 6 with 0x2972 (10610) > packet 8 with 0x2973 (10611) > ..

<p align="center"> <img src="https://i.imgur.com/UPfkkTk.png" height="90%" width="90%" alt=""/>

This isn't always the case, IP ID can jump around randomly and not in order.

#

## How to Use TTL Field

TTL is the number of hops or routers apart from each other. 

- Using Ping on command line to ping google.com, we can capture the TTL.

<p align="center"> <img src="https://i.imgur.com/G0MQyud.png" height="90%" width="90%" alt=""/>

- Can learn network latency, network round trip time
- Get an idea of TTL of how far away a station is to capture point.
  - Can get an idea of how much network was between these two device.
- Since starting value of TTL is 64, 128, 255
  - Started at 128 but arrive at 115. Meaning it went thru 13 routers and then Wireshark captured.
 
#

## How IP Fragmentation Works

Lesson Downloadable File: [udemy-ping-fragmentation.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

The ICMP packets are captured using command line interface: ping 192.168.4.1  -s 1600
- Send a ping that's 1600 bytes long to ping 192.168.4.1

<p align="center"> <img src="https://i.imgur.com/Z7VckIs.png" height="90%" width="90%" alt=""/>


Open the udemy-ping-fragmentation.pcapng on Wireshark: Looking at the first packet

- Expand Internet Protocol Version 4
  - Total Length = 1500; interface was trying to keep this packet within the maximum transmission unit, which doesn't allow to send 1600 bytes in one go.
  - 20 of 1500 bytes are IP header itself
- Expand Flags
  - More fragments is set: Meaning this packet is not on its own.
  - Fragment Offset: starts at 0
 
<p align="center"> <img src="https://i.imgur.com/HuLRJEG.png" height="90%" width="90%" alt=""/>

Looking at the Second packet

- More fragments is Not Set
- Fragment Offset is 1480:
  - The first packet started from 0 to 1479 bytes
  - The second packet started from 1480 to 1600 bytes
 
<p align="center"> <img src="https://i.imgur.com/bvBv8Ub.png" height="90%" width="90%" alt=""/>

Looking at the IP ID:
- Both packets have the same IP ID, Chopped up packets have the same IP ID

<p align="center"> <img src="https://i.imgur.com/bvBv8Ub.png" height="90%" width="90%" alt=""/>

Fragmentation happens when sending an IP packet that is larger than the MTU on an interface can handle.
- Chop it up: first fragment goes out, second one comes out with that offset setting.
- So the end point knows where to glue the data on toward the end and resassemble that packet again at the end.

#

## IP Flags

Don't fragment bit - Not Set:
- The endpoint is telling the network, you can fragment it

Don't fragment bit - Set:
- Tells the network, do not mess with this packet; do not break it up.

<p align="center"> <img src="https://i.imgur.com/X4TKtn8.png" height="90%" width="90%" alt=""/>

If the packet is larger than MTU and Don't fragment bit is Set:
- Router is going to drop that packet, send back an ICMP message to original sender saying the Don't fragment bit is set.

#

## Investigating Suspect Scan Activity

Lesson Downloadable File: [udemy-ip_frag_nmap_scan.pcapng](https://github.com/jefftsui1/Cybersecurity-Home-Labs/tree/main/Guided-Labs/Ethical%20Hacking/Wireshark/Course%201:%20Lab/Downloadable%20Lab%20Files/Lesson%20Downloadable%20Files)

- Packets 4, 5, 6: Fragmented with 8 bytes each in the payload.
  - Packet 4: 0 - 7
  - Packet 5: 8 - 15
  - Packet 6: 16 - 23

<p align="center"> <img src="https://i.imgur.com/4wFSGUX.png" height="90%" width="90%" alt=""/>
<p align="center"> <img src="https://i.imgur.com/400CozM.png" height="90%" width="90%" alt=""/>
<p align="center"> <img src="https://i.imgur.com/pKwp1iz.png" height="90%" width="90%" alt=""/>

- The final packet, 6 shows as the complete packet: glue all 3 packets together and show the TCP header

<p align="center"> <img src="https://i.imgur.com/JhdAR6N.png" height="90%" width="90%" alt=""/>

This might be how an attacker tries to enumerate the system/ sneak by IDS or firewall by fragmenting data.
- Sometimes the system doesn't check for fragments or allow fragments to slip by.
- Good for investigating if this kind of behavior is shown.
