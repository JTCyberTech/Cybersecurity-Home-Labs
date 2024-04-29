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

