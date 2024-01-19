# Domain 1.5

## Introduction to IP 

### A Series of moving Vans

We use a shipping truck to move large amount of data.
- On a network, we use IP.

We need roads for the moving vans.
- On a network, the network topology is the road:
  - Ethernet, DSL, cable system.
 
The vans = Internet Protocol (IP)
- We've designed the roads for this truck

Inside the van hold boxes = our data.
- Boxes of TCP and UDP.

#

### Internet Protocol

How IP operate: 
- Starts on the very basic of Ethernet Frame.
- Commuication between a client and server.
- Ethernet frame have an ethernet header and an ethernet trailer.
  - Inside the header and trailer, there is an ethernet payload.
- Inside the payload can hold the IP and IP payload.
- Inside the IP payload, there can be TCP or UDP and TCP or UDP payload.
- Inside the TCP payload, there can be HTTP data because we are communicate over the internet.
 
<img width="778" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0b9d8805-6536-44dc-8a47-bf463f2ab2e7">


#

### TCP and UDP

Transported inside of IP
- Encapsulated by the IP Protocol.

Two ways to move data from place to place.
- TCP or UDP.

Refer as OSI Layer 4; Transport Layer.

By using TCP and UDP, we can perform multiplexing
- We can use multiple applications simulataneously over the same network by using TCP or UDP.

#

### Transmission Control Protocol (TCP)

Connection-oriented
- A formal connection setup and close.
- Refer to as "Reliable" delivery.
  - Recover from errors.
  - Can manage out-of-orange messages or retransmissions.
  - Put sequence into packets.
- Flow Control: The receiver can manage how much data is sent.

<img width="346" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/2008f8aa-70a1-4676-aa64-9af0b2f28038">

#

### User Datagram Protocol (UDP)

Conectionless
- No formal open or close to the connection.
- Refer to "Unreliable" delivery.
  - No error recovery.
  - No reordering of data or retransmission.
- No Flow Control: Sender determine the amount of data transmitted.

<img width="353" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7ec648f6-f338-4b2f-9123-9fb19d0dd239">

#

### Ports

Non-ephemeral ports = Permanent Port Numbers.
- Port 0 to 1023: Usually on a server or service.

Ephemeral ports = Temporary Port Numbers.
- Port 1024 to 65535: Determine in real-time by the clients.

#

### Port Numbers

- TCP and UDP Ports can be any number between 0 and 65535.
- Most server services uses non-ephemeral (non-temprary) port numbers.
  - Not always the case.
- Port numbers are for communication, not sercurity.
- Service Port numbers need to be "Well Known".
- TCP port numbers are not the same as UDP port numbers.
