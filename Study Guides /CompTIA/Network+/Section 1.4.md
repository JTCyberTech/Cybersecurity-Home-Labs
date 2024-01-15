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


#

## Classful Subnetting

- 3 classes that are not used since 1993 but still relative
  - Class A: 255.0.0.0
  - Class B: 255.255.0.0
  - Class C: 255.255.255.0
- Used as a starting point when subnetting; standard values.

Technically have 5 classes, Class A - E
- Class A to C = assign to work stations.
- Class D = IPv4 and multicast.
- Class E = Reserved range, you will never use these IP Address on your production network.

Most important 3 columns:
- Class; Leading Bits; Default subnet mask.

<img width="764" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3c6ab483-852a-4788-9b7e-be98cff4593d">

# 

### What is the IP Class?

<img width="416" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/75193724-fda6-4020-934e-0bd57427ffeb">

#

### The Construction of a Subnet

Network Address
- When working with IP Subnetting there are 4 separate values you need to know how to calculate.
  1. Network Address
     - The first IP Address of a subnet.
     - Set all host bits to 0 (0 decimal)
  2. First Usable Host Address
     - One number higher than the network address.
  3. Network Broadcast Address
     - The last IP Address of a subnet
     - Set all host bits to 1 (255 decimal)
  4. Last Usable Host Address
     - One number lower than the broadcast address.
    
#

### Subnet Calculations

IP Address: 10.74.222.11
- Class: A address (the first octet = 10)
- Subnet Mask: 255.0.0.0 (Class A subnet mask = 255.0.0.0)
- Since the Subnet Mask is 255.0.0.0 for 10.74.222.11
  - Network = 10.
  - Host = 74.222.11
  
To calculate the Network Address (Set all Host bits to 0)
- Network = 10.
- Host = 0.0.0

<img width="730" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/f056f825-2af6-4a42-8aea-cbd7e640ffa8">

To Caluculate the First host Address (add one decimal to the end of Network Address's Host side)
- Network = 10.
- Host = 0.0.1

<img width="735" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/6e7aa2b9-5b79-4a3c-85be-43bd5b03f976">

To Calculate the Network Broadcast Address (Set all host bits to 1 or 255 in decimal value)
- Network = 10.
- Host = 255.255.255

<img width="734" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/c1efface-c7a1-4229-9f91-27e9382d1885">

To Calculate the Last Host Address (Subtract one decimal at the end of the Network Broadcast Address's Host side)
- Network - 10.
- Host = 255.255.254

<img width="730" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/48efc226-d977-4251-b07e-83397a709fef">

#

IP Address = 172.16.88.200
- Class: B
- Subnet Mask: 255.255.0.0
- Network Address: 172.16.0.0
- First Host Address: 172.16.0.1
- Broadcast Address: 172.16.255.255
- Last Host Address: 172.16.255.254

<img width="779" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/fd3cbe1f-01ca-4762-852e-afb2a4556649">

#

IP Address = 192.168.4.77
- Class: C
- Subnet Mask = 255.255.255.0
- Network Address: 192.168.4.0
- First Host Address: 192.168.4.1
- Broadcast Address: 192.168.4.255
- Last Host Address: 192.168.4.254

<img width="750" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3fce2722-b828-4e27-b452-9dcebee1c3d6">

#

## IPv4 Subnet Masks

- Ones on the rleft side and Zeros on the right side.
- Example:
  - Binary Value = 11111111.11111111.11111111.00000000 
  - Decimal Value = 255.255.255.0
- Shortcut: counting up the number of 1s and putting it right after the slash value.
  - The subnet mask example is also: /24
  - /24 = CIDR block notation. CIDR = Classless Inter-Domain Routing.
  - Other names: slash notation, prefix notation.

#
 
### Binary to CIDR Block Notation

Example: 11111111.11111111.00000000.00000000 
- In bits: 8 + 8 + 0 + 0 = 16 bits
- CIDR Block: /16

<img width="772" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/664e46a9-48d7-4bf3-902a-bdd1fc2d848a">

#

Example: 11111111.11111111.11111111.11000000 
- In bits: 8 + 8 + 8 + 2 = 26 bits
- CIDR Block: /26

<img width="771" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/17fd85e4-a8bf-45b8-8e33-e9849aaa7e57">

#

Example: 11111111.11110000.00000000.00000000 
- In bits: 8 + 4 + 0 + 0 = 12 bits
- CIDR Block: /12

<img width="774" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/c96eaaed-43f5-4f18-87c6-1ea38a2dc40b">

#

### Subnet Masks - Binary to Decimal

<img width="164" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/596f00ce-3b2f-4355-b9af-f9fc8509c181">

#

### Binary to CIDR Block Notation

Example: 11111111.11110000.00000000.00000000 
- Decimal value: 255 . 240 . 0 . 0
- CIDR Blcok: /12

<img width="779" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/81f1d228-0052-4efc-b315-da899ffb15d8">

#

Example: 11111111.11111111.11100000.00000000 
- Decimal Value: 255 . 255. 224 . 0
- CIDR Block: /19

<img width="774" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/ec55170d-5df8-4bdf-80a8-76405aa32afc">


#

Example: /26
- Binary value: 11111111.11111111.11111111.11000000
- Decmail Value: 255 . 255 . 255 . 192

<img width="864" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/2cd804a6-ec3d-48d5-9456-1920d581aac5">

#

Example: /20
- Binary value: 11111111.11111111.11110000.00000000
- Decimal value: 255. 255 . 240 . 0

<img width="840" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/22aa8271-de7f-432a-bbf4-5c926bf5881b">

#

## Calculating IPv4 Subnets and Hosts

Class-based Network are inefficient
- The subnet mask is based on the network class

Classless
- Variable Length Subnet Masks (VLSM)
- Allow network Admin to define their own masks
- Customize the subnet mask to specific network requirements.
- Use different subnet masks in the same classful network.
  - 10.0.0.0/8 is the class A network.
  - 10.0.1.0/24 and 10.0.8.0/26 would be VLSM.
 
#

### Defining Subnets

IP Address: 10.0.0.0
- Class A: Subnet mask: 255.0.0.0
- "Classful" Addressing

<img width="790" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/17a4a32c-dfb6-4543-8537-85edb52170b8">

Placing the subenet

<img width="786" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/8ebeaffb-7248-464b-a49e-1ee9313f70a3">

- Challenge that network admin have to face
  - Detemine where to draw that line.
  - Deteremination on number of subnet bits and host bits that is left over.
  - Determine how they should best engineer the subnetting for their network.
 
#

### Calculating Subnets and Hosts

- Power of 2

<img width="733" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/2d01f6a6-6967-4300-864c-b9d3889d2300">

- Number of Subnet = 2 ^ subnet bits
- Hosts per Subnet = 2 ^ host bits - 2

# 

Example: IP Address = 10.1.1.0/24

- Binary value: 11111111.11111111.11111111.00000000
- Class: A; because it starts with 10 on the first octet.
  - So we know that the default is 8 bits for Network Address.
- Network: 8 bits
- Subnet: 24 bits - 8 bits = 16 bits.
- Host: 8 bits.
- Number of subnets = 2 ^ 16 bits = 65536
- Host per subnet = (2 ^ 8 bits) - 2 = 256 - 2 = 254

<img width="765" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/2bcc1cf7-8e8f-4779-b036-54a8a70f943c">

#

Example: IP Address = 192.168.11.0/26

- Binary value: 11111111.11111111.11111111.11000000
- Class: C; because it starts with 192 on the first octet.
  - So we know that the default is 24 bits for the Network Address.
- Network: 24 bits
- Subnets: 2 bits; 26 bits - 24 bits = 2 bits.
- Hosts: 6 bits
- Number of subnet = 2 ^ 2 bits = 4
- Host per subnet = (2 ^ 6 bits) - 2 = 64 - 2 = 62

<img width="769" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/16d80c42-cd65-4271-a662-d1343f5f6f4d">

#

Eaxmple: IP Address = 172.16.55.0/21

- Binary value: 11111111.11111111.11111000.00000000
- Class B; Because it starts with 172 on the first octet.
  - So we know that the default is 16 bits for the Network Address.
- Network: 16 bits
- Subnets: 5 bits; 21 bits - 16 bits = 5 bits
- Hosts: 11 bits
- Number of Subnet = 2 ^ 5 bits = 32
- Number of Host = (2 ^ 11 bits) - 2 = 2048 - 2 = 2046

<img width="763" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7c745e96-8e6b-4f27-a732-f3bf7466e185">

#

## Magic Number Subnetting

Example for Long way: 192.168.1.0/24
- We need an IP addressing scheme with more than one network address that can support 40 devices per subnet.
  - This means it need more than 40 for number of host.

<img width="763" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/03508a45-cca1-4c73-8490-0447ebbd3d34">

<img width="793" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3df1d727-7f4c-47f0-a805-7f287eb0a87b">

#

### Four important Addresses

1. Network Address / Subnet ID
  - The first address in the subnet.
2. Broadcast Address
  - The last address in the subnet.
3. First available host address
  - One more than the network address.
4. Last available host address
  - One less than the broadcase address.

<img width="593" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/81a3f6b5-1829-4968-bec2-8c054a1962f0">

- This is way too much calculation and conversion.
- Need a shortcut.

#

### Magic Number Subnetting
- Very Straightforward method: Can often perform the math in your head.
- Subnet with minimal math: Still some counting involved.

#

### Some helpful Charts

CIDR to Decimal Charts
- Memorization will increase Speed

<img width="266" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/9b95dac7-cc86-4993-9482-1c95a78d1b35">

#

Complete CIDR to Decimal Charts

<img width="716" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/643267da-3c82-4acd-9d5e-5e3cdaca93a4">

#

Host Ranges
- Larger block are easier to remember
- Multiply quickly for smaller blocks


<img width="775" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5e1164a8-a681-4862-b908-6e5011062069">

#

The magic number process
- Convert the subnet mask to decimal (if necessary)
  - If only given CIDR Block Notation:
    - Convert it to the decimal notation.
    - Identify: interesting Octet
    - Calculate the "magic number": 256 - the intesting octet.
    - Calculate the host range.
    - Identify the network address; first address in the range.
    - Identify the broadcast address; last address in the range.
   
# 

### Find the Subnet ID

Example: 
- IP Address = 165.245.77.14
- Subnet Mask: 255.255.240.0

Need to determine these 4:
- Subnet Mask: 255.255.240.0
- Action Perform: Copy, Copy, Substruct from 256; Get magic number , Zero
- IP Address: 165.245.77.14
- Subnet ID: 165.245.64.0

To determine the Subnet ID and Action:
- If the subnet mask is 255, copy the IP Address to Subnet ID
  - Since Subnet mask for 165.245 for IP Address are both 255, we copy both.
- If the subnet mask is 0, we put 0 to the Subnet ID.
- If there is a value that is not 255 or 0. Then that is the "Interesting Octet"

Calculating the Interesting Octet for Subnet ID:
- Subtract the interesting Octet Subnet Mask from 256.
- 256 - 240 = 16.
- 16 = the Magic Number.
- Look at the host chart, and find the host that is multiply by 16. Then closest smallest divisible by 77 on the IP Address 165.245."77".14 is the Subnet ID.
    - In this case = 64; Since 16,32,48,64,80. "77" is between 64 and 80 and 64 is smaller.
   
<img width="791" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7a18cf7c-e3d2-41e5-9ac1-1ff52d810e19">

#

#### Find the Broadcast Address Using Subnet ID

Example: 
- IP Address = 165.245.77.14
- Subnet Mask: 255.255.240.0
- Subnet ID: 165.245.64.0

Need to determine these 4:
- Subnet Mask: 255.255.240.0
- Action Perform: Copy, Copy, Substruct from 256; Get magic number , Zero
- Subnet ID: 165.245.64.0
- Broadcast Address: 165.245.79.255

To determine the Broadcast Address and Action:
- If the subnet mask is 255, copy the Subnet ID to the Broadcast Address
  - Since Subnet mask for 165.245 for Subnet ID are both 255, we copy both.
- If the subnet mask is 0, we put 255 to the Broadcast Address.
- If there is a value that is not 255 or 0. Then that is the "Interesting Octet"

Calculating the Interesting Octet for Broadcast Address:
- Subtract the interesting Octet Subnet Mask from 256.
- 256 - 240 = 16.
- 16 = Magic Number.
- Calculate Subnet ID + Magic Number - 1
  - 64 + 16 - 1 = 79.
  Broadcast Address = 165.245."79".255

<img width="775" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/1cad98ae-5b17-40fe-9a30-f38230590cca">

#

### Find the Host Range

Example: 
- IP Address = 165.245.77.14
- Subnet Mask: 255.255.240.0
- Subnet ID: 165.245.64.0
- Broadcast Address: 165.245.79.255

First host is Subnet ID + 1
- First available host address = 165.245.64.1

Last host is broadcast address - 1
- Last available host Address = 165.245.79.254

#

### Find the Subnet ID Example 2

Example 2: 
- IP Address = 10.180.122.244
- Subnet Mask: 255.248.0.0

Need to determine these 4:
Subnet Mask: 255.248.0.0
Action Perform: Copy, Get interesting Octet; 256 - 248 , Zero, Zero
IP Address: 10.180.122.244
Subnet ID: 10.176.0.0

Calculation:
- Interest Octet = 256 - 248 = 8
  - 256 - Subnet Mask of Intesting Octet.
  - 8 = Magic Number
  - Look at IP Address position of the Interestin Octet. 180.
  - 180; closest divisible by 8 = 176
- Subnet ID = 255.176.0.0

#

### Find the Broadcast Address Example 2 

Example 2: 
- IP Address = 10.180.122.244
- Subnet Mask: 255.248.0.0
- Subnet ID: 10.176.0.0

Need to determine these 4:
Subnet Mask: 255.248.0.0
Action Perform: Copy, Get interesting Octet; 256 - 248 , If 0 put 255, If 0 put 255
Subnet ID: 10.176.0.0
Broadcast Address: 10.183.255.255

Calculating the Interesting Octet for Broadcast Address:
- Subtract the interesting Octet Subnet Mask from 256.
- 256 - 248 = 8.
- 8 = Magic Number.
- Calculate Subnet ID + Magic Number - 1
  - 176 + 8 - 1 = 183.
  Broadcast Address = 165."183".255.255

#

### Find the Host Range

First Available Host Address:
- Subnet ID + 1 = 10.176.0.1

Last Available Host Address:
- Broadcast Address - 1 = 10.183.255.254

#

### Speed up with Charts 

If the example have /27 at the end.
- Example:
  - IP Address = 172.16.242.133/27
- We can look at the chart:

<img width="680" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0de88394-ed0c-42ed-bba3-7e188a17d438">

Found /27: 
- Magic number = 32
- Interesting Octet = 224

- Found: Subnet Mask = 255.255.255.224

Calculate Subnet ID: Copy, Copy, Copy, magic number = 32 (256 - 224 = 32); 
- Closest number from IP "133" divisible by 32; "128" (32 x 4 = 128)
- Subnet ID = 172.16.242.128

Calculate Broadcast Address: Copy, Copy, Copy, magic number + Subnet ID - 1
- 32 + 128 - 1 = 159
- Broadcast Address = 172.16.242.159

Calculate Host Range: 
- First Availble Host: Subnet ID + 1 = (172.16.242.128 + 1) 172.16.242.129
- Last Available Host: Broadcast Address - 1 = (172.16.242.159 - 1) = 172.16.242.158

<img width="435" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d93503e8-1cc3-4efb-98a3-cd7f2ad17404">

#

## Seven Second Subnetting

### Subnet Masks and Subnets

The Network First Chart

<img width="791" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/3a58e89e-7aba-4925-b1ef-42905f2f3308">

#

The Networks Second Chart

<img width="420" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/fb1372cf-be67-481f-8319-d1dd396990ab">

#

### The Seven Second Subnetting Process

Convert IP Address and Subnet Mask to decimal
- Use chart to convery between CIDR block notation and decimal.
- Same Chart also shows the number of devices per subnet.

Determine network/subnet Adddress
- Second Chart Shows the Starting Subnet Boundary.

Determine Broadcast Address
- Second Chart Shows the Ending Subnet Boundary.

Calculate First and Last Usable IP Address
- Add one from network Address, Subtract one from Broadcast Address.

#

### Seven Second Subnetting Example 1

Example: IP Address = 165.245.12.88/24

1. Convert the Address and mask to decimal.
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.0 (Since /24 is on the 3rd octet)

2. Calculate the Network Address:
  - If Subnet mask = 255, bring down the address
  - If Subnet mask = 0, write 0.
    - IP Address: 165.245.12.88
    - Subnet Mask: 255.255.255.0
    - Network Address: 165.245.12.0 (Copy from IP Address if 255 on Subnet Mask)

3. Calculate the Broadcast Address:
  - If Subnet Mask = 255, bring down the address.
  - If Subnet Mask = 0, Write 255.
    - IP Address: 165.245.12.88
    - Subnet Mask: 255.255.255.0
    - Broadcast Address: 165.245.12.255

4. Calculate the First/Last Usable IP Address:
  - First IP = Network Address + 1.
    - Network Address = 165.245.12.0
    - First IP = 165.245.12.1
  - Last IP = Broadcast Address - 1.
    - Broadcast Address = 165.245.12.255
    - Last IP = 165.245.12.254

5. Put Everything Together:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.0
  - Network Address: 165.245.12.0
  - Broadcast Address: 165.245.12.255
  - First Usable IP Address = 165.245.12.1
  - Last Usable IP Address = 165.245.12.254

<img width="782" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/bdee1a1b-63b3-4467-8770-b7f917f6f0c5">

#

### Seven Second Subnetting Example 2

Example: IP Address = 165.245.12.88/26

1. Convert the Address and mask to decimal:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.192 (192 because /26 is 192 on the fourth octet)
    - Look at the first chart: /26 = 192 decimal.

2. Calculate the Network Address:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.192 
  - Network Address: 165.245.12.64
    - Look at the first chart: /26 = 192 for decimal and 64 for address.
    - Look at the second chart: 64 address; Then look at the IP Address = 88 for interest octet.
      - 88 is between 64 and 128, for Network Address; we pick the lower one, so it's 64.

3. Calculate the Broadcast Address:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.192
  - Broadcast Address: 165.245.12.127
    - Look at the first chart: /26 = 192 for decimal and 64 for address.
    - Look at the second chart: 64 address; Then look at the IP Address = 88 for interest octet.
      - 88 is between 64 and 128, for Broadcast Address; we pick the higher one and substruct it by 1.
      - 128 - 1 = 127

4. Calculate the First/Last Usable IP Address:
  - Add one to Network Address for First.
    - First Usable IP Address = 165.245.12.65
  - Substract one to the Broadcast Address for Last.
    - Last Usable IP Address = 165.245.12.126

5. Put Everything Together:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.255.192 
  - Network Address: 165.245.12.64
  - Broadcast Address: 165.245.12.127
  - First Usable IP Address = 165.245.12.65
  - Last Usable IP Address = 165.245.12.126

<img width="788" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7978c6c5-58db-4c43-8b9b-d0e0dbdcbe16">

#

### Seven Second Subnetting Example 3

Example: IP Address = 165.245.12.88/20

1. Convert the Address and mask to decimal:
  - Subnet Mask: 255.255.240.0

2. Caculate the Network Address:
  - Network Address: 165.245.0.0

3. Calculate the Broadcast Address:
  - Broadcast Address: 165.245.15.255

4. Calculate the First/Last IP Address:
  - First Usable IP Address = 165.245.0.1
  - Last Usable IP Address = 165.245.15.254

5. Put Everything Together:
  - IP Address: 165.245.12.88
  - Subnet Mask: 255.255.240.0
  - Network Address: 165.245.0.0
  - Broadcast Address: 165.245.15.255
  - First Usable IP Address = 165.245.0.1
  - Last Usable IP Address = 165.245.15.254

<img width="638" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/8804d1c1-8d0c-4ee7-bb11-b785bc78c436">

#

### Seven Second Subnetting Example 4

Example: IP Address = 18.172.200.77/11

1. Convert the Address and Mask to Decimal:
  - Subnet Mask: 255.224.0.0

2. Calculate the Network Address:
  - Network Address: 18.160.0.0

3. Calculate the Broadcast Address:
  - Broadcast Address: 18.191.255.255

4. Calculate the First/Last IP Address:
  - First Usable IP Address = 18.160.0.1
  - Last Usable IP Address = 18.160.255.254 

5. Put Everything Together:
  - IP Address: 18.172.200.77
  - Subnet Mask: 255.224.0.0
  - Network Address: 18.160.0.0
  - Broadcast Address: 18.191.255.255
  - First Usable IP Address = 18.160.0.1
  - Last Usable IP Address = 18.191.255.254 

<img width="634" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/1b3ef4e9-ca63-4b0d-b5eb-90122b10a602">

# 

### Seven Second Subnetting Example 5

Example: IP Address = 18.172.200.77/17

1. Find Subnet Mask by converting IP into decimal:
  - 255.255.128.0

2. Calculate Network Address:
  - 18.172.128.0

3. Calculte Broadcast Address:
  - 18.172.255.255

4. Calculate the First/Last IP Address:
  - First Usable IP Address = 18.172.128.1
  - Last Usable IP Address = 18.172.255.254

5. Put Everything Together:
  - IP Address: 18.172.200.77
  - Subnet Mask: 255.255.128.0
  - Network Address: 18.172.128.0
  - Broadcast Address: 18.172.255.255
  - First Usable IP Address = 18.172.128.1
  - Last Usable IP Address = 18.172.255.254

<img width="635" alt="image" src="https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/7896e800-0ed8-41e6-8c25-89fa11a9655e">
