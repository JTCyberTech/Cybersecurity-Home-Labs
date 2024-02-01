# Domain 1.6

## DHCP

IPv4 address configuration used to be manual
- IP Address, subnet mask, gateway, DNS serversm NTP servers, etc.

October 1993: The bootstrap Protocol
- BOOTP

BOOTP didn't automatically define everything.
- Still required some manual configurations.
- BOOTP: didn't know when an IP address might be available again after used.

Upgraded version of BOOTP: Dynamic Host Configuration Protocol
- Initially released in 1997, updated thru the years.
- Provide automatic address/ IP configuration for almost all devices.

#

### Step 1: Discover

DHCP Discover sent from Sam (0.0.0.0:UDP/68) to 255.255.255.255:UDP/67

#

### Step 2: Offer

DHCP Offer Sent from DHCP Server (10.10.10.99:UDP/67) to 255.255.255.255:UDP/68

#

### Step 3: Request

DHCP Request sent from Sam (0.0.0.0/UDP:68) to 255.255.255.255:UDP/67

#

### Step 4: Acknowledgement

DHCP Acknowledgement sent from DHCP Server (10.10.10.99:UDP/67) to 255.255.255.255:UDP/68

#

### Managing DHCP in the enterprise

Limited Communication range
- Uses the IPv4 Broadcast Domain
- Stop at a router

Multiple Servers needed for redundancy
- Across Different Locations

Scalability is always an issue
- May not want or need to manage DHCP Servers at every remote location

#

### DHCP Relay

DHCP relay = IP Helper

#

## Configuring DHCP

### Scope Properties 

- IP Address range
  - Excluded addresses
- Subnet mask
- Lease Durations
- Other:
  - DNS Server
  - Default Gateway
  - VoIP Servers
 
#

### DHCP Pools

Grouping of IP Addresses:
- Each subnet has its own scope:
  - 192.168.1.0/24
  - 192.168.2.0/24
  - 192.168.3.0/24
 
A scope is generally a single configuous pool of IP Addresses.
- DHCP Exceptions can be made inside of the scope.

#

### DHCP Address Assignment

Dynamic Assignment
- DHCP Server has a big pool of addresses to give out.
- Addresses are reclaimed after a lease period.

Automatic Assignment
- Similar to Dynamic allocation
- DHCP Server keeps a list of past assignments
- You will always get the same IP Address

#

### DHCP Address Allocation

Static Assignment
- Administratively configured

Table of MAC Addresses
- Each MAC Address has a matching IP Address

OTher names: 
- Static DHCP Assignment
- Static DHCP
- Address Reservation
- IP Reservation

#

### DHCP Leases

Leasing your address
- It's only Temporary
- But it can seem permanent

Allocation
- Assigned a lease time by the DHCP Server
- Administratively configured

Reallocation
- Reboot your computer
- Confirms the lease

Workstation can also manually release the IP Address
- Moving to another subnet

#

## DNS

Domain Name System
- Translates human-reable name into computer readable IP Addresses
- You only need to remember Google.com

Hierarchical
- Follow the path, very easy to organize things.

#

### DNS Hierarchy

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/8902619b-6a51-4ff8-845a-91c11a75759b)

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/45d23438-abe6-48a3-8e83-5e684f5affbc)

#

### Internal va External DNS

Internal DNS
- Managed on internal Servers
- COnfigured and maintained by local team
- Contains DNS information about internal devices
- DNS service on Windows Server

External DNS
- Often Managed by third party
- Does not have internal device information
- Google DNS, Quad9

#

### Recursive and Iterative DNS Queries

Recursive Query
- Delegate the lookup to DNS Server
- DNS server does the work and reports back
- Large DNS cache provides a speed advantage

Iterative Query
- Do all of the queries yourself
- Your DNS cache is specific to you

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/97b3b2c8-4877-40c0-a33e-403ed0565692)

#

### Authoritative 

Authoritative 
- The DNS server is the authority for the zone

Non-Authoritative 
- Does not contain the zone source files
- Probably Cached information

TTL (time to live)
- Configured on the authoritative server
- Specifies how long a cache is valid
- A very long TTL can cause problems if changes are made

#

### Lookups

Forward Lookup
- Provide the DNS server with an FQDN
- DNS server provides an IP Address

Reverse DNS
- Provide the DNS server with an IP Address
- The DNS Server provides an FQDN

#

## DNS Record Types

Resource Record (RR)
- Database Records of domain name services

Over 30 record types
- IP Addresses, certificates, host alias names, etc

#

### SOA 

Start of Authority
- Describes the DNS Zone details

Structure
- In SOA (Internet Zone, Start of Authority) with name of zone
- Serial number
- Refresh, retrym and expiry timeframes
- Caching Duration/ TTL (Time To Live)

#

### Address Records

A vs AAAA
- Defines the IP Address of a host
- Most popular query

- AAAA = IPv6

A records = IPv4 Addresses
- Modify the A record to change the host name to IP Address resolution

AAAA records = IPv6 Addresses
- Same DNS server, different records

#

### Canonical Name Records (CNAME)

A name is an alias of another, canonical name
- One Physical server, multiple services

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/95b62dea-595b-48aa-b6c0-8eefc2149069)

#

### Service Records (SRV)

Find a specific service
- Where is the Windows Domain Controller?
- Where is the instant message server?
- Where is the VoIP controller?

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/6fe5d44d-7eb2-441e-87cc-126a39ad42a8)

#

### Mail Exchanger Record (MX)

Determines the host name for the mail server 
- This isn't an IP Address; it's a name

#

### Name Server Records (NS)

List the name server for a domain
- NS records point to the name of the server 


#

### Pointer Record (PTR)

The reverse of an A or AAAA record
- Added to a reverse map zone file
- Provide an IP Address, spit back FQDN

#

### Text Records (TXT)

Human readable text information
- Useful Public Information

SPF Protocol (Sender Policy Framework)
- Prevent mail spoofing
- Mail servers check that incoming mail really did come from an authorized host

DKIM (Domain Key Identified Mail)
- Digitally sign your outgoing mail
- Validated by the mail server, not usually seen by the end user
- Put your public key in the DKIM TXT record

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/8c202c68-911a-4b67-9047-69dcac11e8f5)

- The SPF TXT describes the outgoing mail server for the domain.
- The DKIM TXT has the public key, so that someone receiving mail from the server can verify that it really did originate on my email server.

#

### Zone Transfers

Replicate a DNS database
- The primary DNS server has the primary copy of the zone information

Synchronize to a secondary server
- Provide redundancy

Triggered by referencing the serial number
- If the serial number increases, ther must have been a change

Full Zone Transfers can be a security risk
- Attackers can use the data as reconnaissance
