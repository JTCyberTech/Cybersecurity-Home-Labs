# Wireshark Fundamentals

## Capture: Enabling Promiscous Mode

- By enabling promiscous mode, the adapter will capture all taffic that it sees, not only traffic that is addressed to it.
- Common best practice to enable Promiscous mode.

Step 1: Click on Capture on the top menu bar.

<p align="center"> <img src="https://i.imgur.com/n4OdRDw.png" height="90%" width="90%" alt=""/>

Step 2: Click on Options 

<p align="center"> <img src="https://i.imgur.com/KWkUiRk.png" height="90%" width="90%" alt=""/>

Step 3: Check the box for "Enable prmiscuous mode on all interfaces" > Start

<p align="center"> <img src="https://i.imgur.com/xEw7CHK.png" height="90%" width="90%" alt=""/>

#

## Display Filter

- Allows filter the packets bontained in your capture and display only one that match your filter to the screen.
- The display filter criteria needs to be fill into this field.

<p align="center"> <img src="https://i.imgur.com/mxXHdZV.png" height="90%" width="90%" alt=""/>

Common Filter:

- Filter on specific IPv4 Address (Send from or to this IP address): ip.addr==x.x.x.x
- Filter on specific IPv4 Address send from this IP address: ip.src==x.x.x.x
- Filter for a specific IPv4 subnet: ip.addr==x.x.x.x/x
- Filter specific TCP port: tcp.port==x; source port: tcp.srcport==x
- Filter specific UDP port: udp.port==x; source port: udp.srcport==x
- Filter specific Protocol: http; udp; tcp; bootp (DHCP)
- Filter tcp retransmissions: tcp.analysis.retransmission
- Filter tcp STN flags: tcp.flags.syn==1

Combine filters with AND operator

- Filter 1 = ip.addr==10.0.0.10; Filter 2 = tcp.port==80
- Display must have filter 1 and filter 2
  - ip.addr==10.0.0.10&&tcp.port==80

Combine filter with OR operator

- Filter 1 = ip.addr==10.0.0.10; Filter 2 = dns
- Display can have either filter 1 or filter 2
  - ip.addr==10.0.0.10||dns
