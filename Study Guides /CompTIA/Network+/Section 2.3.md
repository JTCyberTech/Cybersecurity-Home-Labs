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

#

# VLANs and Trunking

## LANs

Local Area Networks
  - A group of device in the same broadcast domain

Separate Switches can create separate broadcast domain.
- Physically separate switches there is no way for anyone on the red network to communicate to the blue network and vice versa.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/fffa2510-770d-4748-a443-82ceb1677433)

#

## VLANs

Virtual Local Area Networks
- A group of devices in the same broadcast domain
- Separated logically instead of physically
  - Provides segmentation within the switch:
    - We have interface that are configured for red VLAN
    - Have other interfaces that are configured for the blue VLAN.
- Stil maintain separation of the broadcast domains
  - The red devices can't communicate to the blue devices, vice versa.
  - But separation is done logically inside of the switch rather than physically across multiple switches.
 
![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5e3159c8-b72a-4fd7-b420-7f6c62602ccd)

#

## Configuring VLANs

VLAN 1,2,3 can't communicate with each other.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/442f8d26-273d-4ade-893b-65b0942f7922)

Connecting VLAN 100 on one switch to VLAN 100 on the other and VLAN 200 on one switch to VLAN 200 on the other.
- One way to accomplish = extend an ethernet cable from VLAN 100 on one switch to VLAN 100 interface on the other switch.
  - This won't scale very well. Beacuse it will get messy if there are more VLANs.
- Another way to accomplish = use VLAN trunking

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/b8b8188c-0ec6-411e-bbe6-d504fff553a0)

#

## VLAN Trunking

Instead of extending separate ethernet links for each individual VLAN, we can extend a single connection for each individual VLAN.
- Communicate all VLANs across that single connection = VLAN Trunking/ IEEE 802.1Q/.1Q
- .1Q trunk = can send multiple VLANs across that trunk and then break them out into the appropriate VLAN on the other side.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/1d3c724a-09cd-4bb3-95b6-2c1e54c0063b)

#

## 802.1Q Trunking

- Take a normal Ethernet Frame

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/c205fc5f-5eaf-42fc-bc85-8953a759dae4)

- Add a VLAN header in the Frame
  - VLAN header = information about which VLAN is associated with this data.
- VLAN IDs - 12 bits long, allow to have 4094 VLANs inside of that trunk connection.
  - Normal range = 1 thru 1005
  - Extended range = 1006 thru 4094
  - 0 and 4095 are reserved VLAN numbers.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/b42c42dd-0662-4b60-99e1-446eedaf6393)

- Before 802.1Q, there was ISL (Inter-Switch Link)
  - ISL is no longer used, everyone now uses 802.1Q standard
 
#

## Trunking between Switches

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/6821565c-14cd-4352-9bea-efc98f494f23)

#

## Working with data and voice

Old school: Connect computer to switch, connect phone to PBX (Private Branch Exchange)
- Two physical cables, two different technologies

Now: Voice over IP 
- Connect all devices to the Ethernet switch
- One network cable for both

Data and voice cabling 
- Computer connects to phone
- Phone connects to switch that's located inside of a closet nearby
- One cable, one run

One problem:
- Voice and data don't like each other
- Voice is very sensitive to congestion
- Data loves to congest the network

Resolve this problem:
- Put the computer on one VLAN and the phone on another
- But the switch interface is not a trunk
- How does that work?

Each switch interface has a data VLAN and a voice VLAN
- Configure each of them separately

#

## Configuring voice and data VLANs

- Data passes as a normal untagged access VLAN
- Voice is tagged with an 802.1Q header

Computer = VLAN 100, VoIP = VLAN 200
- When we send information from our computer, it sent across the ethernet link as a normal access ethernet frame with any type of VLAN trunking.
- But if we communicating from our phone/ VoIP, we will tag all of the communication between our phone and the switch with an 802.1Q header that designates that it came from VLAN 200.
- This allows us to set priorities in the switch and assure that the quality of service is maintained for all of out voice communication. 

#

## Spanning Tree Protocol

IPv4 has a TTL field where will identify when a packet is looping thru separate routers and eventually drop the packet from the network.
- With layer 2 ethernet, there is not a TTL function.
- If a loop is created in the network and frame is introduced into that loop, there is no function to drop or remove the frame from the network
- Only way to stop the loop is to physically unplug the cable so the loop no longer exist.

Key with ethernet and switching is to make sure that loop doesn't occur in the first place
- We do that by using **Loop Protection** 

Creating a Loop is easy:
- Just connect two switches to each other
- beacuse there are not counting mechanism at MAC Address, frame will go back and forth

Resolve:
- Unplug one of the cables, remove the loop

IEEE standard 802.1D to prevent loops in bridged (switched) networks (1990)
- By Radia Perlman
- This is the Spanning Tree Protocol


#

### STP port States

When interface is connected to a network, STP begins process of identifying if a loop would be created with the interface.
- There number of modes that interface will placed in.
- Mode: 
  - Blocking port state.
  - Listening port state.
  - Learning port state.

Blocking
- If STP identifies that loop would be created by turning on this interface.
  - Will administratively block all traffic from going in or out of that interface to prevent loop.
- Not forwarding to prevent a loop.

Listening
- Not forwarding and cleaning the MAC table.
- Determine block/not block traffic, it needs to listen for a certain amount of time to be able to know what devices and switches may already be the network.

Learning
- Not forwarding and adding to the MAC table.
- Process of building its own internal topology, so that it understands whether a loop may be occurring or not. 

Forwarding 
- Data passes thru and is fully operational,
- Once comfortable that no loop would be created, begins forwarding traffic.

Disabled
- Administrator has turned off the port.

#

### Spanning Tree Protocol

Root Port =  Root of the network.
Designated Port = all other operational ports on every other bridge.
Block Port = identify potenital loops and it will disable or block individual ports.
- For example: Network C wants to talk to Network Y, have to go thru Bridge 21, 1, 6, 5 then network Y.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3dce8084-6805-44aa-a892-fe73f1b6b4e4)

If there is a cut off to the bridge, STP will recreate a whole another mapping network based on the change. Bridge 5 will change, Network A will no longer communicate with the Root bridge of the network.
- Bridge 5 will change, RP and DP.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0f95c519-6437-49eb-a352-14e14bf557bd)


#

### RSTP (802.1w)

Rapid Spanning Tree Protocol (802.1w)
- Much needed updated of STP
- Latest standard.

Faster convergence
- From 30 to 60 seconds for STP to 6 seconds for RSTP.

Backward compatible with 802.1D STP
- You can mix both in your network.

Very similar process
- An update, not a wholesale change.

#

## Interface Configurations

Basic Interface Configuration

- Speed and Duplex
- Speed = 10/ 100/ 1000/ 10 Gig
- Duplex = half / Full
- Automatic and manual
- Needs tomatch on both sides

