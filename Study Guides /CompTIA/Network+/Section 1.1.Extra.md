# MAC Address

Hub = Repeater
- Take signal from ports and recreate multiple copies of it and send it out to all connected cables.

MAC Address = Phyiscal Address
- Unique identifier for the network card.
- Hexadecimal vaule, 48 bit address. Each Hexadecimal = 4 binary characters.
- First 6 digits = Original Equipment Manufacturer (OEM)
- Last 6 digits = Organizationally Unique Identifier (OUI)

Cyclic Redundancy Check (CRC)
- Used to verify that the data is good.
- If bad data, knows to resend it.

#

# Ethernet Frames

- Preamble: Job = know when a frame is coming.
- Destination MAC: Address to know where it's going.
- Source MAC: Return Address to know where the reciever send it back.
- DATA Type: Also "Ether Type" job = what kind of data is hauling. (0800 or ARP)
- DATA: Can haul Min: 64 bytes or octets. Max: 1522 bytes or octets.
  - PAD: Pushes the data to absolute minimum size 
- FCS: Frame Check Sequence = 32 bits cyclic redundancy check, check the value if it's not correct, resend.
  - Used for error detection.

#

# TCP/IP Model

- Only have 4 layers.
- Application, Presentation, Session layers in OSI Model = Application Layer in TCP/IP Model.
- Transport Layer in OSI Model = Transport Layer in TCP/IP Model. (Everything Same)
- Network Layer in OSI Model = Internet Layer in TCP/IP Model. (Everything Same just name changed)
- Data Link, Physical Layer in OSI Model = Network Interface Layer in TCP/IP Model.

## Layer 1 - Network Interface TCP/IP Model

- Physical and electrical characterstics.
- Describe how to transmit bits across a network and determines how the network medium is going to be used.
  - Twisted pair copper cabling, coaxial cable, fiber optic cable?
  - Wireless? TCP over ethernet? Token Ring, Serial?

#
 
## Layer 2 - Internet TCP/IP Model

- Where data is taken and packaged into IP Datagrams.
- Contains source, destination IPs. Forward those datagrams between different hosts across networks with routers.
- Where internet is going to get connected to intranet.
  - IP, ICMP, ARP, Reverse ARP.

#

## Layer 3 - Transport TCP/IP Model

- Defines the level of service and the status of the connection being used by TCP, UDP, or RTP.
  - TCP = Connection full; UDP = Connectionless; RTP = Real-time.
 
#

## Layer 4 - Application TCP/IP Model

- Dictates how programs are going to interface with the transport layer by conducting session management.
- HTTP for web browsing
- Telnet for remote control
- FTP for file transfer
- SSH for remote shell
- SNMP for network management
- DNS for domain name resolution
- SMTP for sending mail
- SSL or TLS for secure web browsing and encryption

#

# Ports

- 0 to 65535
  - 0 to 1023 = Well-known/ Reserved Ports
  - 1024 to 65535 = Ephemeral Ports
 
## IPv4 Packet

- Consists of a source address, destination address, IP flags, and protocol.
