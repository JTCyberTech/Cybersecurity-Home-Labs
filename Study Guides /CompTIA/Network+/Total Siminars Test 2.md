# Attempt 1

1. You work as an assistant network administrator for a medium sized company. You have been tasked with maintaining your company's configuration management documentation. When would it be a good time to make updates to your network maps?

- When a router has been moved to another location: Network maps are the physical/logical represenation of our network. When you physcially move a router, switch, it would be a very wise plan to update documentation that refer's to its location.

#

2. Steve in the shipping department reports that his office is having a hard time connecting to the Internet, but they are able to connect to the network. Which of the following pieces of documentation would be the most useful in figuring out his problem? (Select two.)

- Wire Schemes, Network Map

#

5. How can technician Sandy ensure that a particular IP address is not leased out from the active scope?

- Reservations: You reserve IP addresses for specific devices like printer or server.

#

7. A Class B block assignment allows for how many hosts?

- Class B = 65,534 hosts
- Class A = 16.7 million hosts
- Class C = 254 hosts

#

# Attempt 2

2. Which of the following routing methods is the most difficult to manage?

- Static: Static Routing is most difficult to manage because you must enter all the routes manually in the routing table for each system

Incorrect: 
- Dynamic: automatically creates routing tables

#

9. A firewall that checks out all the incoming traffic and decides if the traffic is going to be allowed or filtered out is an example of which of the following?

- Stateful Inspecting: With stateful firewall, entire conversation between hosts will be monitored as a single stream. Keep and discard packets based on how it was configured.

Incorrect: 
- Packet sniffing: not feature of firewall. Feature on packet analyzers: Wireshark
- Packet Filering: What firewall does, not a type of firewall.
- Content Filtering: ability to keep or discard specific types of transmission. Operates higher in the OSI model and doesn't concern itself with IP address and port.

#

11. A large office has a group of 15 users. Some of the users complain of poor performance. After scanning the network's performance, the network engineer discovers that many of the computers show moderate to weak signals even though there are two APs less than 15 feet (4 meters) away in either direction. Which of the following is MOST likely the cause?

- The closest APs are down: Farther a client is from an AP, slower it will transfer data.

Incorrect:
- SSID mismatch: would prevent any connection.

#

13. Where would a patch antenna for 802.11 usually be placed?

- Against a wall: Patch antennas generate a half spherical signal, making them perfect use against a wall.

#

16. Your company requires the use of a smart card, biometric device, and a user name/password to login to your system. What kind of authentication are they using?

- MFA: Multifactor Authentication

#

20. Which of following types of cabling would be best to use near ventilation ducts to reduce toxic gases during a fire?

- Plenum: Plenum-rated cable is suitable for installing in ducts and ceilings because of its low fire-producing and toxic characteristics.   

Incorrect: 
- Polyvinyl Chloride (PVC): a cable coating we find on regular UTP, light on fire would release toxic gases.

#

# Attempt 3

3. Mike wants to connect two hubs. Which of the following will work? (Select two.)

- Use a crossover cable between two normal ports
- Use a patch cable from an MDIX port to a normal port

Explanation: 
- When connecting two hubs, the send and receive wires must be reversed.
- This is what MDIX (uplink) ports and crossover cables do:
  - If using a straight-through cable (patch cable), it must be connected to an MDIX port on one hub and normal port on the other hub.
  - If using a crossover cable, it must be connected to normal ports on both hubs.
 
#

7. What Windows utility enables you to query information from the DNS server and change how your system uses DNS?

- Nslookup: utility that runs from the command line, used to both query various information from a DNS server and change how your system uses DNS

#

8. ![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/45117c92-c47c-48cb-9827-acf03cbd447d)

- Netstat -r: route print = netstat -r

#

12. While working on your LAN, you notice that you cannot access your file server. Which of the following utilities would you use FIRST to troubleshoot the problem?

- ipconfig: assume a workstation will have problem before server, run ipconfig on system to make sure you have a good IP Address.

# 

16. Jim is about to install a wireless network. A fellow network administrator warned him about war drivers. What should Jim do to reduce the chance of exposing the wireless signals to war drivers?

- WAP placement: placement of your WAP means everything in war driving. To be a war driver you have to drive around in your car looking for free Wi-Fi Signals.

Incorrect: 
- Fitering Mac Address won't stop people from detecting your Wi-Fi
- Authentication and encryption won't help from detecting your Wi-Fi.

#

20. What can a network administrator configure to control specific IP addresses and ports access to the internal network? (Select TWO.)

- Firewall and ACL (Access Control List): Both can be configured to allow/restrict specific port or IP addresses from accessing the network.

Incorrect:
- MAC filtering and Switches = Layer 2
- IIS server = Hosting web pages
- Port scanner = detecting open ports for security

#

22. A user is using a PKI authentication method. Which of the following will the user need to implement PKI?

- Certificate Service: PKI = Public Key Infrastructure, a methodology for using various pieces to manage and distribute certificate.

#

29. You want to go implement Wi-Fi in your office. What device do you need to connect your clients to the network?

- Access Point: To connect a Wireless device to a wired network, a wireless access point is required. Infrastructure Mode.

Incorrect:
- Router, bridge, hub is not necessary to implement a WiFi network.

#

33. Given a network problem scenario, a technician should identify the problem, then establish a theory for the cause of the problem. What is the next logical troubleshooting step?

- Test the theory to determine the cause: Once you established the symptoms and isolated the scope of the problem, next step should be test out any theory as to what caused the issue.

Incorrect:
- Implementing an action plan or solution is good but we need to find out what caused the issue first.
- Documenting is the last step.

#

# Attempt 4 

11. Rebecca needs to spec the equipment for the installation of a complete network system: cables, switches, PCs… everything. The network only needs to be 100BaseT but must be easy to upgrade to 1000BaseT in the future. Which one of the following, although good to have, would be the least important element for Rebecca to buy now?

- 100/1000 Mbps Switch: She should install CAT 5e horizontal cables and CAT 5e patch panel. reinstalling cabling later would be expensive, she should also use 100/1000 Mbps NICs too
- 100/1000 Mbps switch would be good to have but simple 10/100 mbps switch would be fine at this point. Upgrading switch to 100/1000 mbps in the future would be simple process usually not cost a lot.

#

15. What is the loopback address for IPv6? (Select two.)

- ::1 and 0:0:0:0:0:0:0:1

#

22. Which of the following are dynamic routing protocols? (Select two.)

- RIP (Router Information Protocol): meains the oldest dynamic routing protocol
- OSPF (Open Shortest Path First): newer and better dynamic routing protocolm how navigate the best shortest router pathways as per its name.

Incorrect:
- DNS: handle name resolution in TCP/IP network but does not involve routing protocol
- HTTP: involves application level of Web servers/client

#

29. Brienne, an administrator, attempts to connect a laptop to a server with a length of CAT5 cable that has RJ-45 connectors on each end. She verified the IP settings as correct, but the two computers still cannot connect. Which of the following would MOST likely fix the connectivity problem?

- Wire pairs 1/2 and 3/6 need to be swapped on one end of the connection cables.:  When connecting similar device (2 computers) direcly with a network cable, you need a crossover cable instead of a straight thru cable. In other word, the calbe needs both a TIA/EIA 569A configuration and a TIA/EIA 568B configuration, each of which have different wire pairs at 1/2 and 3/6.

#

34. What routing algorithm does OSPF use?

- Link state: OSPF = Link state, RIP = Distance Vector, EIGRP = Hybrid

# 

36. Your company has to move the heavily-used intranet Web server from one computer to a new, faster system. You make the changeover and send out an e-mail to let everyone know. You then start getting a number of e-mails back saying users cannot access the new Web site by DNS name, even though you updated the "A" record in the DNS server. What's the most likely problem?

- THe user DNS cache still holds the old IP address: User needs to flush their DNS cache. Your system will always look first in the cache to see if they have already resolve this query.

#

38. You recently installed a keypad lock on the door to the telecom room. You only give the code to authorized network administrators. What type of prevention is this?

- Access Control Hardware: Controlling who has access to hardware involves locks on doors, key management, code access, etc.

Incorrect:
- Principle of Least Privilege: comes close but this has more to do with ACLs right and permissions
- Separation of Duties: Assigning different roles to different people in the organization regarding specific tasks.

# 

62. When data arrives at the entrance to a network, what device determines the next network point to send the data to?

- Router: Able to analyze the destination address and deteremines where to send the data next.

Incorrect:
- Hub: forward all packets to all the segments connected to it within the local network
- switch: only forward packet to the segment on the local network containing the node with the recipient MAC address contained in the packet.
- NIC card: only send the data in or out of the node in which the NIC is installed.

#

73. A home user is experiencing performance issues with her wireless network. She has checked the following issues: - Checked to make sure the laptop is within the appropriate wireless network range - Checked the connected SSID and wireless channel - Checked that the laptop is the only device connected to the wireless network Which is the MOST likely cause for the performance issues?

- There are other wireless device in the area that operate on the wireless band and on the same wireless channel.: The user's WAP may be on the right channel, but if other WAPs are on the same channel, their signals can interfere with other, causing slowdowns.

Incorrect:
- Wrong TKIP password: would prevent a conntectionm not poor performance
- IP addresses won't affect performance.

#

86. Which of the following is most likely to effect your company's IP-based surveillance cameras?

- Man in the middle attack: could happen because these are IP based cameras. An attacker could eaves drop on a connection and start seeingwhat you are seeing.

Incorrect:
- FTP bounce: legacy man in the middle style attack used on FTP servers where an attacker uses the port command to request access to ports indirectly gaining access to a vitcim's FTP server.

#

87. Which of the following methods of authentication will also provide AAA and uses UDP?

- RADIUS: runs at Appliation layer (7), uses UDP port number 1812 and 1813 to transport packets, Centralize AAA.

Incorrect:
- TACACS+ = TCP and AAA port 49 to transport packet.
- RAS = authentication service primarily used dial up services. Not AAA
- Kerberos = authentication protocol used in Microsoft base network. Separate method of authentication altogether and no AAA.

#

4. What would you use to create a direct connection between two client 10/100 network workstations?

- Crossover Cable: To directly connect two workstations, you must use a crossover cable. This type of UTP cable crosses the transmit and receive wires so each workstation receives on the other workstation's transmit wire.

#

10. Which series of Windows commands would an administrator use to reset the TCP/IP configuration of a system in order to ensure the system changes its configuration for a new DHCP server?

- ipconfig / release, then ipconfig /renew

#

19. Which of the following is the oldest routing protocol, rarely used anymore?

- RIP (Router Information Protocol)

#

21. Which IT changes should be documented by the change-management team? (Select three.)

- Additions to the network
- NEtwork Configuration
- Physical location changes

#

25. Ripley is a corporate network tech. She receives a report in the morning about Internet service being down at the site. Ripley got an e-mail yesterday that there was a water main break in front of the site, and repair work was going to be performed. On arrival at the site, she sees that there are workers performing repairs to the water system. She performs a test to make sure there are no internal network issues. The internal network is functional, but the laptop fails to connect to the Internet. Which of the following should be performed according to the network troubleshooting methodology?

- Notify employees of the outage and contact the service provider of the demarc: We know the problem, now we have to get help from someone with expertise to fix it.

#

30. If John's boss asks him to install the networking technology defined by IEEE 802.3, what is he asking him to install?

- Ethernet: IEEE 802.3 = Ethernet

#

48. Which of the following attacks enables a malicious person to view network traffic if the attacker is on the same network as the users?

- Man in the middle

Incorrect: 
- DoS, Smurf, and Xmas attacks are denial of service attacks designed to disrupt services.

#

58. What elements would be found in a change request? (Select three.)

- Notification, Rollback process, Configuration procedures: affected users should be included in a change request.

Incorrect:
Funding Mechanisms and Change team members = change mangement team/senior management.

#

59. You are concerned with security at your company and want to implement a technology that requires no configuring on the user's side and will filter out specified port ranges. Which technology will enable this?

- Network based firewall: you can block or allow all the port under the rainbow without your users having to notice or configuring a single thing.

Incorrect:
- Network based IDS: something great that the user will never have to mess with, but since it is only a detection system, you wont have much protection going on.
- Host base: instantly rules out beause we want network based.

#

64. Which of the following ports are MOST commonly used by communications applications to interactively manage network devices? (Select TWO.)

- 22 and 23: SSH and Telnet respectively are typically used to remotely configure device.

#

67. A network administrator for a small Internet café has one switch, but wants the public computers to be separated from the back office machines. What feature would help her achieve her goal?

- VLAN: use VLAN to splot her single switch into multiple switches and keep everything separate.

#

72. Which is the best description of a VLAN?

- Group of port that behaves as an independent switch

#

78. Connie has a typical home network that consists of a Linksys WRT54G wireless router and two systems: one is wirelessly connected, and the other is wired. The internal network ID is 192.168.16.0/24. Both systems can access the Internet. While trying to determine why she cannot access a known Web site, Connie decides to run a tracert. The tracert stops at a particular router: 14.21.343.6. She tries to ping the router but gets no response. Which of the following is the most likely problem?

- Router is down

# 

83. Network administrator Kwan suspects that one of the copper network cables is faulty. When examining the suspect cable, Kwan notices that some of the pairs are untwisted too much. This is MOST likely causing which of the following?

- Cross Talk: Twisting wires around each other helps prevent the signal from bleeding between wires.

#

85. Which elements would you expect in an acceptable-use policy? (Select three.)

- Network Access
- Equipment ownership
- illegal use
