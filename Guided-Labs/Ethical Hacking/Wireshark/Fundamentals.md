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

#

## Customize Color Schemes

To change any default color schemes:

- Click on View on the top bar menu > Coloring Rules

<p align="center"> <img src="https://i.imgur.com/yyOB331.png" height="90%" width="90%" alt=""/>

To quickly to on or off the coloring schemes:

- Click on this icon on the icon bar menu

<p align="center"> <img src="https://i.imgur.com/pJTo0eT.png" height="90%" width="90%" alt=""/>

#

## Customizing Columns and Profiles

Adding a new Profile:

- Right click at the bottom right of Wireshark > New

<p align="center"> <img src="https://i.imgur.com/O0wHIo3.png" height="90%" width="90%" alt=""/>

Adding Source Port to display columns:

- Right click on the Column tabs > Column Preferences

<p align="center"> <img src="https://i.imgur.com/TqdhtLi.png" height="90%" width="90%" alt=""/>

- Click on "+" > Change the title to "Source Port" > change the Type to "Source Port" > OK

<p align="center"> <img src="https://i.imgur.com/UlmCEVa.png" height="90%" width="90%" alt=""/>

- The source port column will be all the way to the right side/ last column > Drag next to Source

<p align="center"> <img src="https://i.imgur.com/o11mwCo.png" height="90%" width="90%" alt=""/>

# 

Second Way to add column, Adding Destination Column to display column:

- Click to expand Transmission Control Protocol > Right click on "Destination Port" > Apply as column

<p align="center"> <img src="https://i.imgur.com/6IQaaqB.png" height="90%" width="90%" alt=""/>

- Drag Destination Port next to Destination

<p align="center"> <img src="https://i.imgur.com/g4lkFVr.png" height="90%" width="90%" alt=""/>

#

## Adding Expression Button

- Adding Expression will create a filter shortcut button

Making a TCP retransmission filter for checking packet loss:

- Click on the "+" next to the display filter
- Name Label: TCP Retransmissions
- Filter: tcp.analysis.retransmission
- OK

<p align="center"> <img src="https://i.imgur.com/pX7Mjsq.png" height="90%" width="90%" alt=""/>

Can add more shortcut buttons:

<p align="center"> <img src="https://i.imgur.com/14m92tH.png" height="90%" width="90%" alt=""/>

To delete the button:

- Edit > Preferences > Filter Buttons > Click on the one you want to delete and "-"

<p align="center"> <img src="https://i.imgur.com/RixWb5P.png" height="90%" width="90%" alt=""/>

#

## Show Time in more detail

The time column can be set to show a lot more detail:

- Right Click Time column > Edit Column > Change Type: Absolute date, as YYYY-MM-DD, and Time

Result: 

<p align="center"> <img src="https://i.imgur.com/dpHYea7.png" height="90%" width="90%" alt=""/>
