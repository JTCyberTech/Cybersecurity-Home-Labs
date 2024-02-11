# Network Devices

## Hub

Multi port repeater
- Traffic going in one port and repeat it to every other port.
- OSI Layer 1.

Everything connected to hub is operating at half duplex.
- You can either send or receive information from the hub, cant do both at the same time.

Becomes less efficient as network traffic increases.

10 MB/s or 100 MB/s


#

## Bridge

Imagine a Switch with two to four ports
- Makes forwarding decision in software.

Connect Different physical networks
- Can connect different topologies
- Gets around physical network size limitation/  collisions.

OSI Layer 2 device
- Distributes traffic based on MAC address

An example of a modern bridge is a wireless access point
- Bridges wired Ethernet to wireless.

#

## Switch

Bridging done in hardware
- Application specific integrated circuit (ASIC)

OSI Layer 2 Device
- Forwards traffic based on data link address

Many ports and features
- Core of enterprise network
- May provide power ove Ethernet (PoE)

Multilayer Switch
- Layer 3 (routing) functionality

#

## Router

Routes traffic between IP Subnets

- OSI Layer 3 device
- Routers inside switches sometimes called layer 3 switches
- Layer 2 = Switch, Layer 3 = Router

Often connect diverse network types:
- LAN, WAN, copper, fiber

#

## Access Point

Not a wireless router
- A wireless router is a router and an access point in a single device

An access point is a bridge 
- Extends the wired network onto the wireless network
- OSI Layer 2 device.

#

## Cable Modem

Broadband
- Transmission across multiple frequencies
- Different taffic types.

Data on the cable network = DOCSIS (Data Over Cable Service Interface Specification)
- Supports a wide range of speeds
- 4 Mbits/s thru 250 Mbits/s
- Gigabit speeds are possible

Can support Multiple services
- Data, Voice, video.

#

## DSL Modem

ADSL (Asymmetric Digital Subscriber Line)
- Uses telephone lines.

Download speed is faster than upload speed (Asymmetrical)
- Based on how far away you are from Central Office (CO)

#

## Repeater

Recieve Signal, Regenerate, Resend
- No fowarding decision to make.

Commonly use to:
- Boost copper or fiber connections
- Convert one network media to another
- Extend wireless network reach.

#

## Media Converter

OSI Layer 1
- Physical Layer Singal conversion

Extend a copprt wire over a long distance
- Convery it to fiber and back again

You have fiber
- Switch only as copper ports

Almost always powered especially Fiber to copper.
