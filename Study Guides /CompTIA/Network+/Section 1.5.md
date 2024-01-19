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

#

## Common Ports

### Telnet 

Telnet = Telecommunication Network
- TCP 23
- If you need to get a console screen from a remote device.
- Console Access
- Problem: It sends the information data without any type of encryption.
  - In the clear communication.
  - Login with username and password; hacker easily can intercept it.
- Not the best choice for production systems.

#

### Secure Shell 

SSH = Secure Shell
- TCP 22
- Encrypted communication link.
- Looks and acts the same as Telnet.

#

### DNS

DNS = Domain Name System
- UDP 53
- TCP 53 - If large transfers
- Converts names to IP Addresses
- Professormesser.com = 162.159.246.164
- In your network, you probably have multiple DNS Servers working simultaneously.

#

### SMTP

SMTP- Simple Mail Transfer Protocol
- TCP 25 (using Plaintext)
- TCP 587 (using TLS Encryption)
- Server to server email transfer.
- Also used to send mail from a device to a mail server.
  - Commonly configured on mobile devices and email.
- For inbound email: Uses IMAP or POP3.

#

### IMAP4; POP3

IMAP4= Internet Message Access Protocol v4; POP3 = Post Office Protocol Version 3
- POP3 = TCP 110 (Plaintext); TCP 995 (TLS)
  - Basic mail transfer functionality.
- IMAP4 = TCP 143 (Plaintext); TCP 993 (TLS)
  - Includes management of email inbox from multiple clients.
  - Example: Delete email in one device; deletes email for all the device.
- Common way to recieve email from an email server.
- Authenticate and transfer.

#

### SFTP

SFTP = Secure File Transfer Protocol
- TCP 22
- Uses the SSH File Transfer Protocol.
- Provides files system functionality.
  - Resuming interrupted transfers, directory listings, remote file removal.
- Encrypted communication: Uses SSH (Port 22)

#

### FTP

FTP = File Transfer Protocol
- TCP 20 (Active Mode Data): When we actually transferring the file.
- TCP 21 (control): tell the system which file to send.
- Transfer files between system.
- Authenticates with a username and password.
- Full-featured functionality (list, add, delete, etc)

#

### TFTP

TFTP = Trivial File Transfer Protocol
- UDP 69
- Very simple file transfer application; read files and write files.
- No authentication; Not used on production systems.

#

### DHCP

DHCP = Dynamic Host Configuration Protocol
- UDP 67; UDP 68
- Automated configuration of IP Address, subnet mask and other options.
- Requires a DHCP Server.
  - Server, application, integrated into a SOHO router.
- Dynamic/Pooled
  - IP Addresses are assigned in real time from a pool.
  - Each system is given a lease and must renew at set intervals.
- DHCP reservation
  - Addresses are assigned by MAC address in the DHCP server.
  - Quickly manage addresses from one location.
 
#

### HTTP/ HTTPS

HTTP = Hypertext Transfer Protocol (Secure)
- HTTP = TCP 80 (Web server communication)
- HTTPS = TCP 443 (HTTP over TLS or SSL) (Web server communication with encryption).
  - SSL = Secure Sockets Layer; TLS = Transport Layer Security.
- Communciation in the browser.

#

### SNMP

SNMP = Simple Network Management Protocol
- UDP 161
- Gather Statistics from network devices 
- Version 1: The original; Structured tables; Plaintext over the network.
- Version 2: Good Step Ahead; Data type enchancements; Bulk Transfer; Still Plaintext over the network.
- Version 3: Secure Standard; Message integrity; Authentication; Encryption.

#

SNMP Trap
- UDP 162
- Alerts and notifications from the network devices if anything bad happens.

#

### Syslog

- UDP 514
- Standard for message logging.
- Diverse System, consolidated log.
- All devices on the network send their log to Syslog.
- Usually a central log collector
  - Integrated into SIEM (Security Information and Event Manager).
- Will need a lot of disk space; pulling in all the log info from every switch and router, firewall, linux server, window server, etc.

#

### RDP

RDP = Remote Desktop Protocol
- TCP 3389
- Share a desktop from a remote location.
- Remote Desktop Services on many Windows Versions.
- Can connect to an entire desktop or just an application.
- If someone is using MacOS, Android, iPhone, Linux: they can still view the desktop of Windows device using RDP.

#

### SNTP

NTP = Network Time Protocol
- UDP 123
- Switches, routers, firewalls, servers, workstation
- Every device has its own clock to make sure the log for all device is in sync.
  - Log files, authentication information, outage details.
- Automatic updates 12:00 lights
- Flexible - you control how clocks are updated.
- Accurary is better than 1 millisecond on a local network.

#

### SIP

SIP = Session Initial Protocol
- TCP 5060 or TCP 5061
- Voice over IP (VoIP) signaling
- Setup and manage VoIP sessions
  - Call, ring, hang up
- Extend voice communication
  - Video Conferencing; Instant Messaging; File Transfer.
 
#

### SMB

SMB = Server Message Block
- TCP 445 (NetBIOS-less)
  - Direct SMB communciation over TCP without the NetBIOS transport.
- Protocol used by Microsoft Windows
- File sharing, printer sharing.
- Called CIFS (Common Internet File System).

#

### LDAP/ LDAPS

LDAP = Lightweight Directory Access Protocol (Secure)
- LDAP = TCP 389
  - Store and retrieve information in a network directory.
- LDAPS = TCP 636
  - A non standard implementation of LDAP over SSL.

#

### Databases

Microsoft SQL Server
- TCP 1433
- MS-SQL (Microsoft Structured Query Language)

Oracle SQL Net
- TCP 1521
- Oracle Net/Net8

MySQL Free and Open Source Database
- TCP 3306
- Ultimately acquired by Oracle.

#

<img width="721" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/a0490139-1029-4014-b453-a5b366f4d8fc">

#

## Other Useful Protocols

### ICMP

ICMP = Internet Control Message Protocol
- Text messaging for your network devices.
- Another Protocol carried by IP
  - That is not used for data transfer.
- Device can request and reply to administrative requests
  - Ping Command: Hey are you there? / Yes I am right here.
- Devices can send messages when things don't go well.
  - That network you're trying to reach is not reachable from here.
  - Your time-to-live expired, just letting you know.
 
#

### GRE

GRE = Generic Routing Encapsulation
- Common way to communicate between sites or devices is to create:
  - Tunnel between those devices and send all data inside of that tunnel.
- Common way to create the tunnel is to use GRE.
- Allow to Encapsulate traffic inside of IP.
  - Two endpoints appear to be directly connected to each other.
  - No built in encryption.
    - Need to add additional protocol to provide security.
   
#

### VPNs

VPN = Virtual Private Networks
- Common way to encrypt data over the tunnel from GRE.
- Encrypted (private) data traversing a public network.
- To do this usually needs a VPN Concentrator.
- Concentrator
  - Encryption/decryption access device.
  - Often integrated into a firewall.
- Many deployment options:
  - Specialized cryptographic hardware.
  - Software based options available.
- Used with client software:
  - Sometimes built into the OS.
 
#

### IPsec

IPsec = Internet Protocol Security
- Common VPN protocol.
- Security for OSI Layer 3.
  - Authentication and encryption for every packet.
- Confidentiallity and Integratrity/anti-replay (way to ensure no one is trying to resend infromation thru this encrypted tunnel)
  - Encryption and packet signing.
- Very Standardized: Common to use multi-vendor implementations.
- Two types of IPsec Protocol:
  - Authentication Header (AH)
  - Encapsulation Security Payload (ESP)
 
#

### Transport mode and Tunnel mode

1. If we would like to send a packet with IP header with some data over IPSec.

 <img width="421" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5111b9ee-89d2-4e81-85f0-c24b450e7bf7">

2. Take the original IP header and include that in Transport mode.
   - Inside of this original IP header, we would have an IPSec headers and then the data that we would commonly encrypt to be able to send across the network.
   - Might not be enough security because the IP header is the original IP Header.

<img width="740" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/982546f9-a780-4aef-8fd8-04b601fed662">

3. To add additional security, we might use Tunnel Mode.
  - Taking the original IP Header and original data and encrypting the data and putting it inside of an IPsec headers and IPsec trailers.
  - Then add a separate brand new IP header to the beginning, so that anyone looking at this data would have no idea where the original data was really originating from or where it is going to.

<img width="767" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/2cee17fb-5bb6-4926-a38b-0714004c61ed">

#

### AH

AH = Authentication Header 
- To ensure that everything being sent across the network is being recieved without any changes.
  - An Authenciation Header is needed to be added to the IPsec communication.
- Hash of the packet and a shared key.
  - MD5, SHA-1, or SHA-2 are common.
  - Adds the AH to the packet header.
 
<img width="787" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/93d48fe6-7f7d-4275-b07e-4b8fdfca2ba8">

#

### ESP

ESP = Encapsulation Security Payload
- Encrypts the packet.
  - MD5, SHA-1 or SHA-2 for hash, and 3DES or AES for encryption.
- Encrypted IP Header; Data; ESP Trailer.
- Authenticate ESP Header; IP Header; Data; ESP Trailer.
- Adds a IP Header, ESP Header, Integrity Check Value.

<img width="771" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/37bea5be-4c68-4062-b867-07265720d51c">

#

### Combining AH and ESP

AH and ESP
- Combine the data integrity of AH with the confiedentiality of ESP.

<img width="667" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ff5236a4-3d17-4937-aec4-0b57e6679e24">


<img width="735" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ef3097a3-a4bb-4ef7-958c-f44329717325">
