# Introduction to Port Forwarding

- Port forwarding is necessary to connect applications and services to the Internet.

- Without port forwarding, applications and services such as web servers are only available to devices within the same direct network.

- In the example network, a server at "192.168.1.10" hosts a webserver on port 80.

- Only the two other computers on the same network can access it (`intranet`).

<p align="center">
<br/>
<img src="https://i.imgur.com/1lFBf5z.png" height="90%" width="90%" alt=""/>
<br />

- To make a `website accessible` on the Internet, use `port forwarding`.

<p align="center">
<br/>
<img src="https://i.imgur.com/XWOftvC.png" height="90%" width="90%" alt=""/>
<br />
Network #2 can access the webserver on Network #1 using Network #1's public IP (82.62.51.70)

- Port forwarding `opens specific ports`, while `firewalls control` if `traffic` can use those ports.

- Port forwarding settings are configured on the network's `router`.

<h2></h2>

Questions 1: What is the name of the device that is used to configure port forwarding?

Answer: `Router`


<h2></h2>

# Firewalls 101

Firewall is like a network guard that decides what traffic can come in and go out. Admins can set rules for this based on numerous factors such as:

- Origin: Check where the traffic is coming from.
- Destination: Examine where the traffic is going.
- Port: Verify which port the traffic is meant for.
- Protocol: Determine if the traffic uses UDP, TCP, or both.


Firewalls vary in types and sizes. 

- They can be hardware-based for large networks or found in home routers.
- Software-based firewalls like Snort are also used.
- They can be grouped into 2 to 5 categories based on their features and functions.

<h2></h2>

<h3>Two Primary Categories of Firewalls</h3>

Stateful: 

- This firewall looks at the whole connection, not just individual packets.
- It uses more resources because it makes dynamic decisions.
  - For example, a firewall could allow the first parts of a TCP handshake that would later fail.
- If a connection is bad, it blocks the whole device.


Stateless:

- Uses static rules for deciding if packets are okay.
  - For example, a device sending a bad packet will not necessarily mean that the entire device is then blocked.
- Uses fewer resources but is less smart.
  - For example, these firewalls are only effective as the rules that are defined within them. If a rule is not exactly matched, it is effectively useless.
- Useful for handling lots of traffic from multiple sources.
  - For example. a DDoS attack.
 
<h2></h2>

Questions 1: What layers of the OSI model do firewalls operate at?

Answer: `Layer 3,Layer 4`

Questions 2: What category of firewall inspects the entire connection?

Answer: `Stateful`

Questions 3: What category of firewall inspects individual packets?

Answer: `Stateless`



# VPN Basics

VPN (Virtual Private Network)

- A technology that helps devices on different networks talk securely.
- They create a dedicated path (tunnel) over the Internet.
- Devices in this tunnel create their private network.

For Example: 

- Only devices within the same network (such as within a business) can directly communicate.
- However, a VPN allows two offices to be connected.

<p align="center">
<br/>
<img src="https://i.imgur.com/Xbkv9E3.png" height="90%" width="90%" alt=""/>
<br />
Devices on Network #3 are part of Network #1 and Network #2. They create a private network, Network #3. Only devices on this private network can communicate using the VPN.


<h2></h2>

<h3>VPN Benefits</h3>

- Allows networks in different geographical locations to be connected.
  - For example, a business with multiple offices will find VPNs beneficial, as it means that resources like servers/infrastructure can be accessed from another office.

- Offers privacy.
  - VPN uses encryption for data protection. Only the sender and receiver devices can understand the data. Data is safe from eavesdropping (sniffing).
  - Useful in public WiFi with no network encryption. VPN protects your traffic from being viewed by others.
 
- Offers anonymity.
  - Journalists and activists rely on VPNs for secure reporting in countries with restricted freedom of speech.
  - Normally, your internet traffic is visible to your ISP and others, allowing tracking.
  - The anonymity of a VPN depends on how other devices on the network handle privacy. If a VPN logs your data, it's similar to not using a VPN in terms of privacy.

 
<h3>TryHackMe VPN</h3>

TryHackMe uses a VPN to connect you to our vulnerable machines.

- This makes your interactions with our machines secure.
- It also prevents service providers from thinking you're attacking other machines on the internet.
- The VPN adds security because vulnerable machines aren't accessible directly through the internet.

<h2></h2>

<h3>Type of VPN</h3>

- PPP: Used by PPTP for `authentication and data encryption`. VPNs use a private key and a public certificate, like SSH. Connection requires matching private key and certificate. Not able to exit a network on its own (non-routable).

- PPTP: Point-to-Point Tunneling Protocol,  lets data from PPP go in and out of a network. It's easy to set up and works on most devices. It's not very secure compared to other options.

- IPSec: uses the Internet Protocol (IP) to encrypt data. Setting up IPsec can be tricky compared to other options. It offers strong encryption and works on many devices when configured correctly.


<h2></h2>

Questions 1: What VPN technology only encrypts & provides the authentication of data?

Answer: `PPP`

Questions 2: What VPN technology uses the IP framework?

Answer: `IPSec`


<h2></h2>

# LAN Networking Devices

<h3>What is a Router?</h3>

- A router connects networks and passes data between them. It uses a process called routing to make data travel across networks.
- Routing creates a path for data to be delivered.
- Routers work at Layer 3 in the OSI model.
- They have an interface for administrators to set rules like port forwarding and firewalling.

Routers and Switches have different functions

- Determining the path involves factors like:
  - Shortest path
  - Reliability
  - Faster medium (copper or fiber)
 
<h2></h2>

<h3>What is a Switch?</h3>

- A switch connects multiple devices. Switches use Ethernet cables to connect devices.
- They can work at both layer 2 and layer 3 of the OSI model.
- Layer 2 and layer 3 functions are exclusive; layer 2 switches cannot do layer 3 tasks.
  - For example, a layer 2 switch in the diagram below. These switches will forward frames (remember these are no longer packets as the IP protocol has been stripped) onto the connected devices using their MAC address.
 
- Layer 3 switches are more advanced than layer 2 switches. It can do some router tasks liks sending frames to devices (same as layer 2) and Route packets to other devices using the IP protocols.


<h2></h2>

<h3>VLAN</h3>

- VLAN (Virtual Local Area Network) divides devices in a network.
- Devices share an Internet connection but are treated separately.
- Security is maintained by rules that control device communication.

<p align="center">
<br/>
<img src="https://i.imgur.com/Xbkv9E3.png" height="90%" width="90%" alt=""/>
<br />
"Sales Department" and "Accounting Department" can use the Internet. But, they can't talk to each other, even though they're on the same switch.


<h2></h2>

Questions 1: What is the verb for the action that a router does?

Answer: `Routing`

Questions 2: What are the two different layers of switches? Separate these by a comma I.e.: LayerX,LayerY

Answer: `Layer2,Layer3`
