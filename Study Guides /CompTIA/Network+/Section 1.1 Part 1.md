# OSI Model

- Open Systems Interconnection Model
- 7 Layers in the OSI Model
- Please; Do; Not; Touch; Small; Pen; Again
- Physical; Data Link; Network; Transport; Session; Presentation: Application

#

- Revers: All; People; Seem; To; Need; Data; Processing
- Application; Presentation; Session; Transport; Network; Data Link; Physcial

#

- Do; Some; People; Fear; Birthdays
- Data; Segments; Packets; Frames; Bits

#

- Data = Layer 5,6,7 or Sessions, Presentation, Application layer.
- Segments = Layer 4 or Transport layer.
- Packets = Layer 3 or Network layer.
- Frames = Layer 2 or Data Link layer.
- Bits = Layer 1 or Physical layer.

#

Ethernet Frame

- FCS = Frame Check Sequence: make sure data is the same as sent and recieved.
- Data
- Source Port
- Destination Port
- Source IP Address
- Destination IP Address
- Source MAC
- Destination MAC
- Preamble: warning for network card there is incoming frame; bunch of 1s and 0s alternate.

#

MAC Address = Unique 48 bits values in **network card**, wired or wireless

#

Layer 7: Application - Your Eyes
Layer 6: Presentation - Application Encryption (SSL/TLS)
Layer 5: Session - Control Protocols, Tunneling Protocols
Layer 4: Transport - TCP Segment, UDP Datagram
Layer 3: Network - IP Address, Router, Packet
Layer 2: Data Link - Frame, MAC address, Extended Unique Identifier (EUI-48, EUI-64), Switch
Layer 1: Physical - Cables, Fiber, Signal

#

# Layer 1 - Physical Layer

Messer
- Physics of the network
  - Signaling, Cabling, Connectors
  - This layer isn't about protocols
- Physical layer problem = fixing cabling, run loopback test, replace cable, swap adapter cards.

Meyers
- Makes sure 1s and 0s gets to different hosts.
  - Strip off: Preamble and Frame Check Sequence on the Ethernet Frame.

Dion
- Layer that tell us if we are using ethernet network; fiber or copper cables; Cat5 or Cat6, Wi-Fi.
  - All data send across the layer = bits/ binary bits.
- Layer 1 issue:
  - View network from a physical topology perspective. (Bus, ring.. topology)
  - How is communication synchronized?: how does the reciever knows when it's readdy to accept 1s and 0s.
    - Transport Asynchronously or Synchronously.
      - Asynchronously: A voice mail, uses start and stop bits to indicate when transmission occurs.
      - Synchronously: Phone call (talking at the same time), use a reference clock to coordinate the transmission by both sender and reciever. Every second the clock pass = transmit and recieve.
  - How is bandwidth of the cable utilized?
    - Broadband or Baseband.
      - Broadband: Divides bandwidth into separate channels. (TV: single cable but carries multiple channels)
      - Baseband: Use all available frequencies on a medium (cable) to transmit data. (telephone, Ethernet betwork)
        - Baseband use reference clock - allow us to send information for both sender/reciever at certain time (synchronous communication).
  - How can we get more out of a limited network?
     - Time Division Multiplexing (TDM): each session takes a turn using time slots to share the medium between all users.
     - Statisical Time-Division Multiplexing (StatTDM): Dynamically allocates the time slot on an as needed basis.
     - Frequency-Division Multiplexing (FDM): Divides the medium into channels based on frequencies and each sessions is transmitted over a different channel.
- Multiplexing = Getting more out of a limited network. Allows mutliple people to use a baseband connection at the same time.
- Example of Layer 1:
  - Cables: Ethernet/ Fiber Optic
  - Radio Frequencies: Wi-Fi/ Bluetooth
  - Infrastructure Devices: Hubs/ Wireless Access Points/ Media Converters.
- Layer 1 are dumb devices: Whatever they take in, spit it back out.

#

# Layer 2 - Data Link Layer

Messer
- Also refer to DLC or Data Link Control Protocol.
  - MAC address on Ethernet. Media Access Control
  - Might refer to the switching layer.

Meyers
- Job: Allow individual system to be addressed ethernet frame get into right spot.
  - Check the Destination MAC address on the Ethernet Frame. Destination MAC Address = It's own MAC Addresss
  - If it's different MAC Address from its own MAC Address, it will erase it.
  - Use the Source MAC Address to send back Ethernet Frame to the sender.
  - Strip away: Source MAC Address and Destination MAC Address.

Dion
- Layer that package data into frames and transmits the frames on the network.
  - Performs error detection/ correction/ identifying unique network device using MAC Addresses.
- MAC: Phyisical Addressing system of a device which operates on logical topology.
  - 48-bit address assigned to Network Interface card (NIC).
    - 12-digit hexadecimal. (D2:51:F1:3A:34:65)
    - Each letter = 4 bits.
    - First 6 letters (D2:51:F1) = vendor who made the card.
    - Last 6 letters (3A:34:65) = Unique value/ exact machine it belong to.
- Layer 2 issue: Devices view network logically.
  - Logical Link Control (LLC): Provides connection services and allows acknowledgement of receipt of message.
    - Basic Flow Control: Limit amount of data sender can send at once to keep receiver from overwhelmed.
    - Basic Error Control: Allows reviever to let sender know when an expected data frame wasn't received or corrupted by using a checksum.
  - How commuication synchoronized? 3 Schemes
    - Isochronous Mode: Network devices use a common reference clock source and create time slots for transmission. (Less overhead than Synchronous/Asynchronous).
    - Synchronous Mode: Network devices agree on clocking method to indicate beginning and end of frames. (Use Control characters or separate timing channel).
    - Asynchronous Mode: Network devices reference their own internal clocks and use start/stop bits.
- Example of Layer 2: Network Interface Cards (NIC), Bridges, Switches
  - Switches = smarter, logic to learn which physical ports are attached to which devices based on MAC Address.

#

# Layer 3 - Network Layer

Messer
- Routing Layer: Layer associated with IP Addresses
- Layer where frames is broken into smaller pieces to move between different types of networks.

Meyers
- MAC Address is good for moving data between local area network.
- IP Address is good for moving data between internet.
- Layer 3 looks at the incoming packets' IP addresses and make sure it's going to the right place.
- Strip away: the Source and Destination IP Address.

Dion
- Forward Traffic (Routing) with logical address. With (IPv4 or IPv6).
- Logical Addressing: IP is most common.
- How should data be forwarded or routed? 3 ways
  - Packet Switching: Known as "Routing", Data is divided into packets and forwarded based on IP Address.
  - Circuit Switching: Dedicated communication link is established between two devices. (Same path every time during the session)
  - Message Switching: Data is divided into messages, similar to packet switching but these messages may be stored then forwarded.
- Route Discovery And Selection
  - Decide which path to take to send the message.
  - Routers maintain a routing table to understand how to forward a packet based on destination IP address.
  - Routing protocols helps decide how data is going to flow across the network/ how routers communication the information.
- Connection Services
  - Flow Control: Prevents sender from sending data faster than receiver can get it.
  - Packet Reordering: Allow packets to be sent over multiple link and across multiple route for faster services.
- ICMP (Internet Control Message Protocol): Used to send error messages and opertional information to an IP destination.
  - PING and traceroute.
- Example of Layer 3: Routers, MUltilayer Switches, IPv4 and IPv6 Protocol, Internet Control Message Protocol (ICMP)

#

# Layer 4 - Transport Layer

Messer 
- Post Office Layer: Describes how data is being delievered and where it is being delievered into a system.
- Protocol used: TCP and UDP (Transmission Control Protocol and User Datagram Protocol).
  - Used when accessing a webpage.
  - Webpage too large have to chop it up into seperate frames to send multiple parts and put back together on the other side.

Meyers
- Job: To assemble and disassemble different pieces of data as they come in.
- Chop it up into byte chunks so individual frame can send it out.

Dion
- Dividing line between the upper layers and lower layers of OSI model.
  - Lower Layers = Physical, Data Link, Network Layers.
  - Upper Layers = Transport, Session, Presentation, Application Layers.
- Focused on TCP and UDP Protocols.
  - TCP: Transmission Control Protocol: connection oriented protocol, reliable transport of segments.
    - If segments dropped, protocol detects it and resents segment.
    - Acknowledgements received for successful communications.
    - Used for all network data that needs to be assured to get to its destination.
    - 3 Ways Handshake: SYN, SYN/ACK, ACK.
  - UDP: User Datagram Protocol: Connectionless Protocolm unreliable transport of segments.
    - If segment dropped, sender is not aware.
    - Good for audio and visual streaming.
    - Lower overhead for increased performance.

<img width="384" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ebc4fe03-33d4-4bf1-9766-dd0348b5a246">

- Windowing: Allows the clients to adjust the amount of data in each segment.
  - Continually adjusts to send more or less data per segment transmitted.
  - Adjusts lower as number of retransmissions occur.
  - Adjusts upwards as retransmissions are eliminated.
  - Want to be able to send as much information as quickly as possible with the least amount of retransmissions but still getting the maximum throughput.
- Buffering: Occurs when devices (routers) allocate memory to store segment if bandwidth isn't readily available.
  - When available, it transmits the contents of the buffer.
  - If the buffer overflows, segments will be dropped.
  - We want to buffer things and hold it and then as we have room, we can send that information out, clear the bufferm and keep on moving.
  - Can keep costs down by knowing utilization is over our network for long period of time.
- Example of Layer 4: TCP and UDP, WAN accelerators, Load Balancer and Firewalls.


#

# Layer 5 - Session Layer

Messer 
- Communication management between devices (Start, Stop, Restart).
- Use Control Protocols, Tunneling Protocols.

Meyers
- Makes the connection to the remote host. Establishing connection to web servers if web browser.
- Once established, data can move back and forth between the two individual systems.
- If IP address gets the data to the right computer, it is the port numbers which are part of the packet that get the data to the right application.
- Strips away: Source and Destination Ports.

Dion
- Think of a session as a conversation that must be kept separate from other to prevent intermingling of the data.
- Set up a Session, Maintaining a Session, Tearing Down a Session.
  - Set up a Session: Check user credentials, assign number to session to identify them, negotiate services needed for session, negotiate who begins sending data.
  - Maintain a Session: Transfer data back and forth across the network.
    - If there is a break in the connection, have to reestablish connection.
    - Acknowledge receipt of data.
  - Tearing Down a Session: Ending a session after the transfer is done or when the other party d/c.
    - Due to mutual agreement/ After the transfer is done.
- Example of Layer 5: H.323 and NetBIOS.
  - H.323: Used to set up, maintain, tear down a voice/ video connection.
    - H.323/ H.264 = Streaming Audio or Steaming Video. (Real Time Protocol RTP).
  - NetBIOS: used by computer to share files over a network.


#

# Layer 6 - Presentation Layer

Messer
- Character Encoding.
  - Takes the data into a form that we can understand.
- Application encryption.
- Often combined with Layer 7 Application Layer.

Meyers
- Job: Make sure data not only get to the right application but gets it in a format that application can view.

Dion
- Responsible for formatting data and securing data with proper encryption.
- Data Formatting and Encryption.
  - Data Formatting: formatted by computer so it has compatibility between different types of devices.
    - ASCII, GIF, JPG, PNG.
    - ASCII: Ensures data is readableby recieving system. Provides proper data structures. Allows negotiate data transfer syntax for Layer 7 application layer.
  - Encryption: Use scramable the data in transit to keep it secure from prying eyes and provide data confidentiality.
- Example of Layer 6:
  - Scripting Languages - HTML, XML, PHP, JavaScript.
  - Standard Text - ASCII, Unicode, EBCDIC.
  - Pictures - GIF, JPG, TIF, SVG, PNG.
  - Movie Files - MP4, MPG, MOV.
  - Encryption Algorithms - TLS, SSL.

#

# Layer 7 - Application Layer

Messer
- A layer that we get to see.
- HTTP, FTP, DNS, POP3

Meyers
- Smarts built into applications, so when data comes up from lower layers, application can actually read this thing.

Dion
- Provides all application level services.
- Application like file transfer or network transfer.
  - Not Chrome, Word, PowerPoint, or Notepad.
- Layer where users communicate with computer.
  - Function like application services and service advertisement.
  - Application Services: unites communicating components from more than one network application.
    - Example: File transfer, file sharing, E-mail, Remote Access, Network Management Activities, Client/server processes.
    - Email = POP3, SMTP, IMAP.
  - Service Advertisement: Where application can send out announcements to other devices on the network.
    - Example: Printers, File Servers. 
- Example of Layer 7:
  - Email Applications (POP3, IMAP, SMTP).
  - Web Browsing (HTTP, HTTPS).
  - Domain Name Service (DNS)
  - File Transfer Protocol (FTP, FTPS)
  - Remote Access (TELNET, SSH)
  - Simple Network Management Protocol (SNMP)
