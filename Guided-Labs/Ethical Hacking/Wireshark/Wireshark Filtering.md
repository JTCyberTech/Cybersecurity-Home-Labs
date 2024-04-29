# Introduction to Wireshark Filters

## Common Filters 

- IPv4 Address: ipaddr==10.0.0.1
- IPv4 Source: ip.src==10.0.0.1
- IPv4 Range (Subnet): ip.addr==10.0.0.0/24
- TCP Port: tcp.port==80
- TCP SYNs: tcp.flags.syn==1

#

## Operators in Filters

- ==: eq
- !: not
- ||: or
- &&: and
- ">": gt
- "<": lt

#

## Removing with Filters

- !(arp or stp or lldp)

Remove all broadcast

<p align="center"> <img src="https://i.imgur.com/W23oLII.png" height="90%" width="90%" alt=""/>

- Expand: Ethernet II > right click on Destination > Prepare as filter > select
- Add ! in front of the filter: !eth.dst == ff:ff:ff:ff:ff:ff
- Can add more thing you want to filter out: !(eth.dst == ff:ff:ff:ff:ff:ff or arp or stp or lldp)

#

## Saving packet into filtered

If you want to save the packet with the filtered stuff:

- File > Export Specified Packets 

<p align="center"> <img src="https://i.imgur.com/z5diJOe.png" height="90%" width="90%" alt=""/>

- Name > Check the "Displayed" Circle > Save

<p align="center"> <img src="https://i.imgur.com/5k14Aim.png" height="90%" width="90%" alt=""/>

#

## Special Operators

- contains: (exact string) frame contains "google"
- matches: (regex) http.host matches "\.(org|com|net)"
- in {range}: tcp.port in {80 443 8000..8004}
- http.request.method == "GET" or http.request.method == "POST"
  - Short version: http.request.method in {GET,POST}
