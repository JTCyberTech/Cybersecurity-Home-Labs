# Lab 1 - First Nmap Scan

I will do my first scan on [Scanme.nmap.org](http://scanme.nmap.org/) with my Kali Linux VM.

<h2></h2>

- On Kali Linux VM, open up command line and Wireshark.

<p align="center">
<br/>
<img src="https://i.imgur.com/vqautIV.png" height="90%" width="90%" alt=""/>
<br />


- Double click on "eth0" on Wireshark.

<p align="center">
<br/>
<img src="https://i.imgur.com/59wyinO.png" height="90%" width="90%" alt=""/>
<br />

- Check if the corner shark fin is gray.
  - If it's gray then it's capturing packets.

<p align="center">
<br/>
<img src="https://i.imgur.com/0hpOyBn.png" height="90%" width="90%" alt=""/>
<br />

- On Command line: ```nmap scanme.nmap.org``` then Enter.

<p align="center">
<br/>
<img src="https://i.imgur.com/NcCrS0g.png" height="90%" width="90%" alt=""/>
<br />

- Nmap shown that it's done scanning.
  - Click on the red square to stop Wireshark from scanning.

<p align="center">
<br/>
<img src="https://i.imgur.com/oXiLd6r.png" height="90%" width="90%" alt=""/>
<br />

- On Wireshark display filter, type in: ```tcp.flags.syn==1```. Then, Enter.
  - This filters for all of the TCP syns that were sent out.

<p align="center">
<br/>
<img src="https://i.imgur.com/PGhbtsm.png" height="90%" width="90%" alt=""/>
<br />
 
- On Wireshark display filter, type in: ```tcp.flags.syn==1 and tcp.flags.ack==0```. Then, Enter.
  - this filters for all TCP syns that were sent out and filter out all ACK packets.

<p align="center">
<br/>
<img src="https://i.imgur.com/c2CmmFx.png" height="90%" width="90%" alt=""/>
<br />
 
- On Wireshark display filter, type in: ```tcp.port==22```. Then, Enter.
  - The packets shows it has [SYN], [SYN, ACK], [ACK]. Which means it was able to establish connection.
  - [RST, ACK] means we finished the handshake and we sent a reset back to end the TCP connection.

<p align="center">
<br/>
<img src="https://i.imgur.com/H2OEIef.png" height="90%" width="90%" alt=""/>
<br />

- On Wireshark display filter, type in: ```tcp.port==25```. Then, Enter.
  - The packets shows [SYN] was sent then it's being retransmitted and never got a [RST, ACK] back.
  - Possible that Port 25 is beting filtered by a firewall or something.

<p align="center">
<br/>
<img src="https://i.imgur.com/tag80xB.png" height="90%" width="90%" alt=""/>
<br />
 
