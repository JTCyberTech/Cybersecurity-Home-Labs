#  Introduction 

In this room, we will cover the techniques and key points of traffic analysis with Wireshark and detect suspicious activities. Note that this is the third and last room of the Wireshark room trio, and it is suggested to visit the first two rooms stated below to practice and refresh your Wireshark skills before starting this one.

- Wireshark: The Basics
- Wireshark: Packet Operations

In the first two rooms, we have covered how to use Wireshark and do packet-level searches. Now, it is time to investigate and correlate the packet-level information to see the big picture in the network traffic, like detecting anomalies and malicious activities. For a security analyst, it is vital to stop and understand pieces of information spread in packets by applying the analyst's knowledge and tool functionality. This room will cover investigating packet-level details by synthesising the analyst knowledge and  Wireshark functionality for detecting anomalies and odd situations for a given case.

# 

# Nmap Scans

<h3>Nmap Scans</h3>

Nmap is an industry-standard tool for mapping networks, identifying live hosts and discovering the services. As it is one of the most used network scanner tools, a security analyst should identify the network patterns created with it. This section will cover identifying the most common Nmap scan types.

- TCP connect scans
- SYN scans
- UDP scans

It is essential to know how Nmap scans work to spot scan activity on the network. However, it is impossible to understand the scan details without using the correct filters. Below are the base filters to probe Nmap scan behaviour on the network. 

<p align="center"> <img src="https://i.imgur.com/WznNSdY.png" height="90%" width="90%" alt=""/>

<h3>TCP Connect Scans</h3>

TCP Connect Scan in a nutshell:

- Relies on the three-way handshake (needs to finish the handshake process).
- Usually conducted with `nmap -sT` command.
- Used by non-privileged users (only option for a non-root user).
- Usually has a windows size larger than 1024 bytes as the request expects some data due to the nature of the protocol.

<p align="center"> <img src="https://i.imgur.com/KHouP7v.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/Ayr2e1p.png" height="90%" width="90%" alt=""/>

`tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024`

<p align="center"> <img src="https://i.imgur.com/7dfk4E8.png" height="90%" width="90%" alt=""/>

<h3>SYN Scans</h3>

TCP SYN Scan in a nutshell:

- Doesn't rely on the three-way handshake (no need to finish the handshake process).
- Usually conducted with `nmap -sS` command.
- Used by privileged users.
- Usually have a size less than or equal to 1024 bytes as the request is not finished and it doesn't expect to receive data.

<p align="center"> <img src="https://i.imgur.com/jFS62lZ.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/c5mq2bM.png" height="90%" width="90%" alt=""/>

`tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024`

<p align="center"> <img src="https://i.imgur.com/gUFwIHC.png" height="90%" width="90%" alt=""/>

<h3>UDP Scans</h3>

UDP Scan in a nutshell:

- Doesn't require a handshake process
- No prompt for open ports
- ICMP error message for close ports
- Usually conducted with `nmap -sU` command.

<p align="center"> <img src="https://i.imgur.com/mZPogGH.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/1Fk2Pym.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/GHAWj4f.png" height="90%" width="90%" alt=""/>

The given filter shows the UDP scan patterns in a capture file.

`icmp.type==3 and icmp.code==3`

<p align="center"> <img src="https://i.imgur.com/C7C6LIN.png" height="90%" width="90%" alt=""/>

Detecting suspicious activities in chunked files is easy and a great way to learn how to focus on the details.

#

<h3>Questions</h3>

Use the "Desktop/exercise-pcaps/nmap/Exercise.pcapng" file.

Question 1: What is the total number of the "TCP Connect" scans?

`1000`

<p align="center"> <img src="https://i.imgur.com/uWEltaM.png" height="90%" width="90%" alt=""/>

#

Question 2: Which scan type is used to scan the TCP port 80?

`TCP Connect`

#

Question 3: How many "UDP close port" messages are there?

`1083`

<p align="center"> <img src="https://i.imgur.com/EGEbDql.png" height="90%" width="90%" alt=""/>

#

Question 4: Which UDP port in the 55-70 port range is open?

`68`
