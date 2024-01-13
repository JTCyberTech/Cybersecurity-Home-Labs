# Domain 1.4

## Binary Math

- Bit = zero and one
- Off or On, Cold or Hot = 0 or 1.
- A byte = 8 bits
  - Often called "octet" to avoid confusion.
 
<img width="766" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7968e74a-2117-4ab5-ab6b-ccde5656904e">

Can be larger if working on additional IP subnetting.
- Majority = 8 single bits made up into a byte.

#

### Binary to decimal calculation

- Binary of 00000010 in decimal.
  - it will be 2 decimal, since only 1 is on the 2 for binary chart.
 
<img width="759" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0325bad5-1f3d-46cd-8083-4056f7908bde">

#

- Binary of 10000010 in decimal.
  - 130 decimal
 
<img width="774" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7ea3adcf-9c6e-45f3-828f-172b71f148f4">

#

- Binary of 11111111 in decimal.
  - 255 decimal
 
#

### Decimal to binary calculation

= Decimal 154 in binary.
  -10011010

<img width="776" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/32b4d099-9471-416e-95f0-1a87174af97a">

#

### Extending binary math

- Power of two
  - Usefil for binary calculations and subnetting
 
<img width="771" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/fc72b28b-6fa9-4e16-afb1-7a872da483c6">

#

## IPv4 Addressing

IPv4 have 3 important addresses to be configurate.
- IP Address - 192.168.1.165
  - Every device needs a unique IP Address that identify on the network.
- Subnet Mask - 255.255.255.0
  - Used in conjunction with IP Address so your device understands what IP subnet it live on.
  - Used by local device to determine what subnet it's on.
  - Used to transmit across the network thru default gateway.
- Default Gateway - 192.168.1.1
  - IP Address that is on the same local subnet as your IP address.
  - Where you send all traffic that needs to go outside of this local subnet.
  - Router that allows you to communicate outside of your local subnet.
  - Must be IP Address on local subnet.

IPv4 Address Breakdown
- OSI Layer 3 Address
  
<img width="386" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ecdf93ce-039a-4231-91fd-f3653de5db07">

 
#

### Loopback Address

- An address to yourself
  - If you send any traffic to this address, you send it to yourself.
- Ranges: 127.0.0.1 to 127.255.255.254
- Easy way to self reference (127.0.0.1)
  - Great way to determine if the IP stack inside the system is working properly.
  - Perform this ping:
    - If you get a response, then your IP stack is working properly.
    - If no response, then problem with the TCP/IP stack inside OS.
   
#

### Reserved Address

- Set aside for future use or testing.
- Range: 240.0.0.1 to 254.255.255.254
- All "Class E" Address.

#

### Virtual IP Address (VIP)

- Assigned interal to your system, but not assigned to physical network adapter.
- Assigned to a logical adapter that only exist inside the software of your system.
- Not associated with a physical network adapter
- Virtual Machine, internal router address. (Static IP Address reference for that router)

#

### DHCP

Dynamic Host Configuration Protocol
- IPv4 Address configuration used to be a manual process.
  - IP Address, subnet mask, gateway, DNS servers, NTP servers.
- Provides automatic address and IP configuration for almost all devices.

#

### Automatic Private IP Addressing (APIPA)

- Used when a DHCP is not available.
- An IP Address that is not assigned by the DHCP but the APIPA.
- Called: A link-local Address
  - Not able to communicate outside of your local subnet/ can't communicate to internet.
  - Routers are not able to forward those IP Address.
- Range: 169.254.0.1 to 169.254.255.254
  - But the first and last 256 addresses are reserved.
  - Range that can only be used: 169.254.1.0 to 169.254.254.255
- Automatically assigned and using ARP to confirm if the address is free.

#

## Public Addresses vs Private Addresses

- We uses NAT to increase the number of availabe devices by setting aside some IP address range.
  - Private IP Addresses.

### Network Address Translation (NAT)

- Estimated 20 billion different devices connected over the internet.
- IPv4 only support 4.29 billion addresses.
- Address space for IPv4 is exhausted. No more available addresses to assign.
- We use NAT to address this issue but it's not the only reason to use NAT.

Use:
- When a device changes an IP Address as it's communicating thru the network.
- Commonly done using a router.

<img width="752" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/89f3b11a-2542-4321-b028-a42f190c4a0c">

- If Vala wants to send packet to a website.
  - When the packet is sent to the router, it knows that Vala is using a private address to it changes to a Public IP Address configurated for the router.
- Only works when there is only one IP address inside the switch that needs to be translated.

#

### Port Address Translation (PAT)/ NAT Overload

- Used when there is multiple IP Addresses inside the switch that needs to be translated.

<img width="728" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/377e5560-95ee-4c86-980c-f6729f04730a">

- Adds a random port number to the Source IP and the port number that is for the Destination IP.
- When the packet is sent to the router:
  - Router recognizes that internal IP address needs to be change to public IP Address.
  - Need to change the Port Number as well.
  - Change by creating a NAT Table.
    - Translate the private IP Address and what is available as a public IP Address.
    - Can translate back from public IP Address into the same Private IP Address with this NAT table.

<img width="244" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/8679070b-7ee6-4483-a532-d89de953bf6c">

#

### RFC 1918 

- RFC = Request For Comment
- RFC 1918 = defines what private IP Address ranges will be.

<img width="575" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f8eb8bcd-a6cc-432b-848e-fbb818b88275">

- First column is most important.
- All private IP Address:
  - 10.0.0.0 to 10.255.255.255
  - 172.16.0.0 to 172.31.255.255
  - 192.168.0.0 to 192.168.255.255

#

## Network Communication

### Unicast

- Means: one device is sending infomration directly to another device.
- One-to-one communication between devices.
  - One device make a request to a server, server respond to that individual request.
- Example: Web Surfing, File Transfers
- Disadvantage: Does not Scale will if it needs to commuicate with multiple devices simulataneously.
  - Example: Real-time streaming, unicast will have to send a single separate to every single device on the network. (one-to-one communication)
- Common used in IPv4 and IPv6.

<img width="294" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d3f2a406-8650-407c-b5e4-0d7698547602">

#

### Broadcast

- A more efficient way to send traffic to multiple device on the network simultaneously.
- Means: One device can send one piece of information to everyone at once.
- One-to-all communication between devices.
- Disadvantage: Limited scope - the broadcast domain, usually limited to your local IP subnet.
  - Can't send one packet to the internet and communicate with every other device on the internet.
  - Once you have large number of broadcast on the network, can create performance problems for all other devices.
    - Corrects this issue using IPv6's multicast by limiting the scope of what is sent to all the device.
- Uses: ARP requests that use broadcasts extensively.
- Only used in IPv4

<img width="311" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/9d9375db-f5c7-4d1c-b86b-82c510e73528">

#

### Multicast

- Allows you to send a single frame that would only be seen by devices that are interested in receiving that information.
  - Other devices are not involved in that communication are not affected by multicast.
- Delivery of information to interested systems.
- One-to-many-of-many communication between devices.
- Example: Multimedia delivery, stock exchanges, dynamic routing updates.
- Disadvantage: Very specialized because required to only send traffic to interested parties on the network.
  - Technology that is difficult to scale scale across large networks.
- IPv4 and extensive for IPv6 because IPv4 doesn't support IPv6.

<img width="277" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/cdf35db6-4218-42e8-aba1-a8b000b4906c">

#

### Anycast

- A source device that needs to communicate with a different type of device and many devices available on the network but you only need to talk to one of those devices.
- Allows you to communicate to a single device on the network, but that single device can be one of many options available.
- Single Destination IP Address has multiple paths to two or more endpoints.
- One-to-one-of-many commuciation between devices.
- Used in IPv4 and IPv6.
- Packets sent to anycast address are delivered to the closest inerface.
  - Example: Announce the same route out of multiple data centers. clients use the data center closest to them.
  - Anycast DNS.

<img width="279" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5a70bc82-7c75-4ae7-b5f1-1ed19b0a5077">

