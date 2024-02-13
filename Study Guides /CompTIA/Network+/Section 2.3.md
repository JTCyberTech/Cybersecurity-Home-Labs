# Intro to Ethernet

## SOHO LAN

Small Office Home Office

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/20cb40ba-91c3-4ebe-aad8-ae7ebb6f7204)

#

## MAC Address

Ethernet Media Access Control Address
- Physical Address of a network Adapter
- Unique to device

48 bits or 6 bytes long
- Display in hexadecimal
- First 6 = Organization Unique Identifier (OUI)
- Last 6 = Network Interface Controller Specific (Serial number)

#

## Duplex 

Half Duplex
- A device cannot send and recieve simultaneously
- All LAN hubs are half duplex devices
- Switch interfaces can be configured as half duplex
  - Usually only when connecting to other half duplex device
 
Full Duplex
- Data can be sent  and recieved at the same time over same ethernet interface
- A properly configured switch interface will be set to full duplex

#

## Half Duplex Ethernet

- Traffic received on one interface is repeated to all other interfaces for Hub

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0754e48f-8803-452b-973e-4d1ba1cf7d90)

- If two devices communicate at the same time you will have collision.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/50bb1e97-db71-4899-a0e5-2a46d9991b55)

#

## CSMA/CD

Carrier-sense Multiple Access with Collision Detection (CSMA/CD)
- CS = Carrier Sense
  - When you connect to a network, the ethernet adapter needs to identify that it is connected to a network with other devices.
  - Senses a carrier that it's able to use to communicate across that network

- MA = Multiple Access
  - You can have many different devices communicating on the same ethernet network
 
- CD = Collision Detect
  - Collision = Two stations talking at the same time
  - Identify when data gets garbled
 
- Half Duplex Ethernet
  - Not used any longer.
 
#

## CSMA/CD Operation

Listen for an opening
- Don't transmit if the network is already busy

If it's not busy, then Send a frame of data
- You send data whenever you can
- There is no queue or prioritization

If a collision occurs
- Transmit a jam signal to let everyone know a collision has occurred
- Wait a random amount of time
- Retry the transmission

#

## Full Duplex Ethernet

Sam's PC creates an Ethernet Frame
- Sam's MAC address is the source
- SGC Server MAC address is the destination

Frame is sent to Switch A
- Switch A examines the destination MAC address
- Sends frame out the interface that matches the destination MAC
- Determines the best route to send that frame. Device at the other end is Switch B

Frame is sent to Switch B
- Switch B forward the frame to the interfaces that matches the destination (SGC Server) MAC Address
- Destination PC receive the frame, identifies a matching destination MAC
- Destination PC accepts the frame.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/1d44c750-2bb2-4794-96b4-37d45d0f60a3)

Full duplex
- Send and recieve can happen at the same time.
- Send without having collision.

#

# Network Switching Overview

## Switch

- Role of Switch is to forward traffic based on the destination MAC Address
- Switch need to keep an ongoing and active list of all the devices it happens to know about based on the MAC Addresses of those devices.
- Switch build this list by looking at the incoming traffic and examining the source MAC Address and tying that source MAC Address to a specific physical interface.
- Maintain a loop free environment
  - Using Spanning Tree Protocol (STP)
 
#

## Learning the MACs

Switches examine incoming traffic
- Makes a notes of the source MAC address

Add unknown MAC addresses to the MAC Address table
- Sets the output interface to the received interface

#

## Flooding for unknown MACs

- The switch doesn't always have a MAC address in the table
- When in doubt send the frame to everyone
- Flood only happends when the switch doesn't know the MAC Address in the table.

#

## Address Resolution Protocol (ARP)

On IPv4 network devices are able to obtain the MAC address of a remote device using the ARP protocol.
- ARP will query the network for a specific IP address, that IP address will response back with its MAC address

Determine a MAC Address based on IP Address
- You need the hardware address to communicate.

Arp -a
- View local ARP Table
- Your Local computer keeps a cache of all of the MAC address that it currently knows.

When Performing Ping request:
- First thing that occurred was an ARP request made to the network to try to find that device and receive an ARP response
- Then allowed me to send traffic to that device directly.

#

## NDP (Neighbor Discovery Protocol)

IPv6 doesn't have broadcasts so can't use ARP
- Operates using multicast with ICMPv6

Neighbor MAC Discovery
- Replaces the IPv4 ARP

Can also be used in conjunction with SLAAC (Stateless Address Autoconfiguration)
- Automatically configure an IP Address without DHCP server

NDP also used to identify any duplicate addresses using DAD (Duplicate Address Detection)
- No duplicate IPs

#

## NDP in action

There is no ARP in IPv6
- Sent Neighbor Solicitation (NS) as a multicast
- Neighbot Advertisement (NA)

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/32c1f255-51df-49b6-90e3-ed07ec43735b)

#

## Power over Ethernet (PoE)

Power provided on an Ethernet cable
- One wire for both network and electricity
- Phones, cameras, wireless access points
- Useful in difficult to power areas.

Power provided at the switch
- Built in power = Endspans: Power that is coming from the switch
- In line power injector = Midspans: Power that is coming from an injector

Power Modes
- Mode A: Sending Power on the data pairs; If you are using gigabit connections, you are using all of those wires for your gigabit ethernet data. These cases, we using Mode A, sending power and data over same wire.
- Mode B: Sending Power on the spare pairs; If your ethernet network is a 10 or 100 megabit per second connection, then you have some extra wire inside of that cable that you could use for power.

#

## PoE and PoE+

PoE: IEEE 802.3af-2003
- Original PoE specification
- Now part of the 802.3 standard
- 15.4 watts DC power
- Max current of 350 mA

PoE+: IEEE 802.3at-2009
- Updated PoE specification
- Also part of the 802.3 standard now.
- 25.5 watts DC power
- Max current of 600 mA
