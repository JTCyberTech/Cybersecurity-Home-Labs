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
  - Total Length = 1500; interface was trying to keep this packet within the maximum transmission unit.
- Expand 
