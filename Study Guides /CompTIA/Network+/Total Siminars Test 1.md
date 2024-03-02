# Attempt 1

1. Router that sends a packet down a particular path that think is correct but the packet ends up back at a router that it already passed thru

- Routing Loop: Generally misconfiguration problem between routers, and different routing protocol have different feature that attempt to keep these loops from developing in the first place.

Incorrect:
- Hop count: number of hops a packet takes from source to destination
- Missing Route: Make a destination unreachable
- Asymmetrical routing: When packet takes one path to the destination but the response package takes a different path.

#

2. To accommodate a growing department, a new switch was installed with little configuration. Hosts attached to the new switch sometimes connect to the network and sometimes they don’t. There is no discernable pattern to whether a node will successfully connect to the network. Which selection is the most likely cause of the problem?

- Misconfigured DHCP Server: An enterprise grade switch comes with built in DHCP server usually. Unless it is configured correctly or disabled altogetherm it can generate conflicting or non conforming IP Address.

Incorrect:
- Switch is a wired device, does not impact by saturated WAP (Wireless Access Point)
- Misconfigured DNS server would cause **consistent** problem for any node that used it.
- Switches reduce the number of collision, not cause or make worse collision.

#

3. What is used to measure the **Relative signal strength coming out of a directional Antenna** comparing the strong end signal with an omnidirectional antenna?

- Effective Isotropic Radiated Power (EIRP): EIRP can measure a diretional antenna's signal strength by comparing to an omnidirectional antenna

Incorrect:
- Received signal strength Indication (RSSI): Shows the signal between WAP and a receiver.
- Site Survey: Identifies other wireless network or objects that may cause interference and helps you to determine the best location for your WAPS.
- Multimeter: Used to test voltage levels.

#

4. what is the purpose of MAC address Table?

- Table that store all MAC addresses of each connected computer on the switch: Switch operates at Layer 2, therefore stores any information related to MAC address.

Incorrect:
- Table that stores all MAC address of each connected computer on **Router**: Router operates at Layer 3 and uses IP Address, not MAC Addresses.
- Table that stores all MAC address of each connected computer on **Firewall**: Firewall don't store MAC address information.
- Randomly generated table on an IPS: An IPS is a security prevention device and operate at Layer 3.

#

5. Which technology enables data to be transported over wiring that carries cable television signals?

- DOCSIS: Data Over Cable Service Interface Specification

Incorrect:
- IEEE 1901: Standardizes the transmission of data over home electrical wiring
- EIA 568B: RJ-45 wiring
- Ethernet over HDMI: Supports ethernet over HDMI interconnecting cables.

#

## Second Attempt

1. What is used to measure the relative signal strength coming out of a directional antenna, comparing the “strong” end signal with an omnidirectional antenna?

- EIRP: Effective Isotropic radiated power

#

2. A private network has which of the following traits?

- IP Addresses are not exposed to the Internet: A private network's IP Address is not exposed to the Internet, and as a result is not assigned by an organization.

Incorrect:
- IP Addresses mut be assigned by IANA, Only uses static IP Addresses, Exposed to the internet are all Public Network.

#

3. Which of the following Ethernet standards use UTP cable? (Select two.)

- 100BaseTX and 1000BaseT: Both uses UTP cable

Incorrect:
10GBaseLW, 10GBaseSW, 10GBaseER are all Fiber Optic Cabling.

#

4. A school decides to issue Chromebooks to all of its students, but allows the option of students using their own laptop for schoolwork. However, a very watered-down plan is put in place for the students that use their own laptop. One day, you notice several students with their own device are trying to access inappropriate Web sites. What category does this fall under?

- BYOD Challenge; Bring Your Own Device: need to be addressed before allowing students or employees to connect to the network with their device.

Incorrect:
- AUP challenge (Acceptable Use Policy): Agreement that needs to be signed whether students/employees bring their device or not.
- Licensed feature issues: happens when company decides to use features from a licensed vendor without obtaining proper authorization.
- Network Performance issues: plain wrong.

#

5. Which Cisco IOS command shhows the statistics for network interfaces?

- Show interface command provide the status of all network interface

Incorrect:
- show route command display every known connected and destination network
- show config command display current configuration
- show IP is not a command

#

6. Which technology is an authentication solution that uses TCP and also provides AAA?

- TACAS+ uses TCP to perform AAA functions

Incorrect:
- Radius uses UDP to perform AAA
- RAS provides authentication
- Kerberos doesn't provide authorization

#

7. Which technique would be used to test the network security of a particular network by allowing it to accept security attacks?

- Honeynet: Draws attackers so their method and location can be determined and subsequently protect against without jeopardizing vital information

Incorrect:
- Honeypot: single machine
- Vulnerability scanner and Network Based IDS: Very Helpful but don't want them to receive security attacks

#

8. Which command will show you the name of the current system you are working on?

- hostname: will show current name of the system. Useful for running a script on many systems that needs access to each system's hostname.

Incorrect:
- netstat: utility display information on the current state of all the running IP processes on system
- route: utility display and edit the local system's routing table
- showhost: does not exist

#

9. In order to broadcast to all nodes on a LAN, which MAC address will be used?

- FF:FF:FF:FF:FF:FF : When a packet needs to be sent to all the nodes on LAN = Broadcast, MAC address used as the destination MAC address in packet is FF:FF:FF:FF:FF:FF (Broadcast address)

Incorrect:
- 00:00:00:00:00:00 : is a valid MAC address but not broadcast.
- 127.0.0.1: Address used for loopback test
- 255.255.255.255: not valid subnet mask.

#

10. Your network administrator has decided to remove WINS from the network and replace it with DNS. Your WINS server resolves requests to 20 address locations on your network segment. What's the BEST way to ensure that users can reach those addresses by host name automatically?

- Request that the hostnames and addresses be added into DNS: best way = add entries to the DNS server.

Incorrect:
- Adding entries to the HOSTS files would work but this would need to be done on every workstation.
- Adding WINS proxy is not an option since the WINS server is being taken out of the network.
- Entering hostnames into the LMHOSTS file wouldn't do much because LMHOSTS is for NetBIOS resolution, not DNS.

#

## Attempt 3

1. Which of the following would fall under licensed feature issues?

- Ensuring that you can use OSPF on a non-Cisco router: OSPF is a Cisco routing protocol. OSPF needs licensing.

Incorrect:
- Ensuring that you can install more than a certain amount of Cisco Switches in your equipment rack: As long as you have the funds, you can purchase as many Cisco switch as you want.
- Ensuring that you are paying the correct monthly fees for using DNS and DHCP within Microsoft Windows Server: There are no fees for DNS and DHCP, built in tools for Windows Servers.
- Encuring that you when implementing BYOD policy, all employees sign the AUP (Acceptance User Policy): BYOD policy, employee must sign AUP but have nothing to do with licensing.

#

2. MU-MIMO is a feature of the 802.11ac wireless standard. What does it provide?

- Simultaneous transmission to multiple users: MU in MU-MIMO stands for multiple users.

Incorrect:
- Maximum Unified signal is not real term
- Multiple Antennas on the workstation wireless card: Multiple Antennas are required to achieve MU at the Access Point. Not Workstation.

#

3. Which layer of the OSI model ensures packets are delivered in sequence, error free, and without losses?

- Transport Layer: Layer 4 handles the sequencing and error detection of the packet.

#

4. Which type of backup data contains customized settings for a router or switch?

- Configuration: Configuration data is stored in a text file so settings can be quickly recovered.

Incorrect:
- State: State data would be convergence for a router, or Active Directory on a server.
- Standard and System do not apply in this scenerio.

#

5. Which technique would be used to test the network security of a particular network by allowing it to accept security attacks?

- Honeynet

#

6. Governments strictly regulate which bands, and which channels within each band, that Wi-Fi systems can use. What is this called?

- Regulatory Impact: applies rather specifically to the channels in 2.4 GHz range and more generally to the other ranges.

#

7. Which table maps a destination MAC address to a port within a switch?

- MAC address lookup table: maps destination MAC addresses to ports within a switch.

Incorrect:
- ARP cache table is found within a host, not a switch.
- Nslookup is a tulity that maps DNS name against IP address.
- DNS cache table hold DNS-to-IP mapping within a Windows host.

#

8. What kind of malicious attack creates a buffer overflow to prevent regular users from accessing a system?

- DoS: Denial of Service attack typically involves overwhelming a system with low-level requests (like pings) so that the system doesn't have time or resources to respond to real user requests.  

Incorrect:
- Blue Jacking: involves sending unsolicited messages over Bluetooth to device (mobile phone, laptop)
- Man in the Middle: involves intercepting network traffic between 2 or more systems.
- Netstat: What we use to tell us about the current sessions we have running on our computer.

#

9. Which type of contingency plan will detail risks to critical systems, cost to replace or repair such systems, and how to make those replacements or repairs happen in a timely fashion?

- Business Continuity Plan: (BCP) helps organization to stay afloat by assessing the risk and cost.

Incorrect:
- Disaster recovery plan: plan in place in case a disaster occurs.
- Recovery point objective: (RPO) sets a upper limit to how much lost data the organization can tolerant if it must restore from a backup.
- Backup plan: General term.

#

10. What is the purpose of the MAC address table?

- Table that stores all MAC addresses of each connected computer on the switch.

#

11. You just installed some new cable segments in the network. Which document would you update?

- Wiring diagram: Show any number of types of wiring, to a detailed layout of the physical space with drops to each workstation and full cable runs.

Incorrect:
- Baseline: shows how a netowrk operates at optimum potential
- Site survey: Used for wireless networks
- Statement of work: Understanding of the work to be performed.

#

12. Which of the following is a valid IPv6 address?

- FEDC:BA98:7654:3210:FEDC:BA98:7654:3210 : IPv6 each group is a hexadecimal between 0000 and FFFF.

#

13. Which routing protocol allows a gateway host to send its entire routing table to the next closest host?

- RIP v2: Routing Information Protocol is oldest routing method used for dynamic routing. It said entire routing table would be sent indicates that it is a Distance Vector Routing Protocol not Link State Routing Protocol.

Incorrect:
- OSPF, IS-IS, EIGRP is all Link-State or Hybrid Routing Protocols.

**Need to Remember what is the Routing protocols**

# 

14. Which of the following Ethernet standards use UTP cable? (Select two.)

- 100BASETX and 1000BASET

#

15. What is used to measure the relative signal strength coming out of a directional antenna, comparing the “strong” end signal with an omnidirectional antenna?

- EIRP (Effective Isotropic Radiated Power)


#

16. You are looking to switch to a cloud-based storage service for the files in your organization. That means getting rid of the outdated storage server in your telecommunications room. What is the FIRST step to take when disposing of the hard drives in the old server?

- Take the necessary steps to perform a full factory wipe on the drives: Factory wipe using the proper tools/services will ensure that all data is removed.

Incorrect:
- A simple format in Windows can leave remnants on the hard drives that can be recovered.
- Hard drives should never just be thrown in the trash.
- Dumpster divers can get them and find ways to recover them.  You should research local ordinances, but not until you perform a factory wipe on the drives.

#

17. Which technology enables data to be transported over wiring that carries cable television signals?

- DOCSIS (Data Over Cable Service Interface Specification)

#

18. A router sends a packet down a particular path that it thinks is correct, but the packet ends up back at a router that it already passed through. What is this called?

- Routing loop

#

19. What technology passes IP data over home-entertainment-device interconnect cables?

- Ethernet over HDMI: enable devices like televisions and video player to communicate using standard network protocols.

Incorrect:
- 10Base2: not an entertainment device interconnection cable.
- Power lines are not entertainment device interconnection cable.
- IEEE 1901 refers to Ethernet over home electrical wiring.

#

20. A private network has which of the following traits?

- IP Addresses are not exposed to the Internet.

#

21. Which command will show you the name of the current system you are working on?

- hostname

#

22. You have 20 new employees that need e-mail accounts. Which of the following protocols do you need to set up the e-mail accounts? (Select two.)

- POP3 and SMTP: Post Office Protocol version 3 (POP3) for incoming e-mail and Simple Mail Transfer Protocol (SMTP) for outgoing e-mail are the two most common protocols you need to set up an e-mail account. 

Incorrect: 
- SNMP: enables communication with network devices such as a hub or router.
- FTP: is for uploading and downloading files.
- ICMP: is for error reporting. It is used in utilities such as ping.

#

23. Which command will display the current configuration for a switch?

- Show Config: will provide status of all configuration.

Incorrect:
- show route: command displays every known connected and destination network.
- show IP: command doesn't exist.
- show interface: command displays the status of all network interfaces.

#

24. A router has not been configured properly, and as a result, packets are not reaching their destination. What could be the cause of this?

- Missing Route: cause packets to not reach their destination.

Incorrect:
- route mismatch: is not the proper term for this.
- Asymmetric routing: is when a packet takes one path to the destination but the response packet takes a different path.
- routing loop: occurs when a packet takes a path that leads to a router it already visited.

#

25. Sherman has configured his network hosts to use DHCP. Now he wants to ensure that his users can use names like www.totalsem.com instead of IP addresses when using their Web browsers. He needs to install what kind of server?

- DNS Server: (Domain Name Service) resolves domain names such as www.totalsem.com into IP addresses.

Incorrect:
- WINS (Windows Internet Name Service) provides a similar function, but only for NetBIOS names like SERVER1.
- A DHCP server provides automatic TCP/IP configuration for nodes.
- An FTP server provides remote uploading and downloading of files.

#

#

1. Which of the following are benefits of patch panels? (Select two.)'

- Organizes the horizontal cabling
- Protects the horizontal cabling from over handling

Explaination:
- A patch panel allows the horizontal cabling to be organized while also protecting the horizontal cabling from over handling that can lead t ocable breakage.
- Patch panel do not offer any surge or ESD protection.

#

2. Theo must send highly sensitive data over his PPTP connection. What feature of PPTP will give him confidence that his data won't be stolen in route? PPTP = Point to Point Tunnel Protocol

- Encryption: PPTP's encrytion scrambles the data, making it unreadable to anyone but the client and server.

#

3. A chain-of-custody document includes what information? (Select three.)

- When was evidence taken into custody
- What was taken into custody
- To whom was evidence passed and when

Explaination: 

- Chain of custody is concerned with tracking evidence to avoid loss or tampering documents
  - what evidence was taken into custody
  - when it was collected
  - who was it passed on to

#

4. A router sends a packet down a particular path that it thinks is correct, but the packet ends up back at a router that it already passed through. What is this called?

- Routing loop

#

5. What is the technical term for an uplink port and the auto-sensing feature of ports in modern switches?

- MDI-X = new term for an auto sensing port

Incorrect:
- Trunk port is used to send data within the same VLAN across multiple switches.
- No shutdown port = used to enable a port as active.
- Native VLAN port = used as VLAN 1 by default and doesn't have t obe an uplink port.

#

## Attempt 4

1. E-mail programs and FTP work on which layer of the OSI 7-layer model?

- Application Layer: FTP and e-mail programs work on Layer 7, or the Application layer

#

2. Which command will show you the name of the current system you are working on?

- hostname: hostname = show surrent name of the system

#

3. As a network administrator, you notice that many employees have fallen victim to social engineering tactics. What is the BEST way to prevent more of these instances from happening?

- Employee Training: best way to mitigate social engineering threat.

#

4. Current versions of Windows Server can provide a secure tunnel via HTTPS for a Remote Desktop Connection (RDC) session. What does the server run to accomplish this?

- Remote Desktop Gateway (RDG): Uses TLS for security

Incorrect:
- Remote Desktop Protocol (RDP): Protocol used to remote into a computer and it is the predecessor of RDC.
- Border Gateway Protocol (BGP): routing protocol.
- Independent Computing Architecture (ICA): defined how terminal information was passed between the server and client.

#

5. What is the purpose of the MAC address table?

- Table that store all MAC address of each connected computer on a switch

#

6. While setting up your wireless network, you want to have certain users access the Internet, but block them from accessing other wireless clients or wired network itself. What do you need to setup?

- Wireless Client Isolation: Also called Guest Network Isolation, allows users to benefit of the internet without intruding on your network.

Incorrect:
- Wireless client separation: not a term
- MAC Address filtering: blocking hosts from the wireless network based on MAC Address
- Disabling SSID (Service Set IDentifier) broadcast: Will not let anyone see the wireless network unless they know the SSID name.

#

7. A standard user in a company receives an e-mail from what looks like her bank. It requests that she click on a link to fix her account information. What type of social engineering is this?

- Phising

#

8. Which layer of the OSI model ensures packets are delivered in sequence, error free, and without losses?

- Transport Layer

#

9. A router has not been configured properly, and as a result, packets are not reaching their destination. What could be the cause of this?

- Missing Route

#

10. Which term describes the orientation of radio waves of a Wi-Fi signal?

- Polarization: Polarization of Wi-Fi signals depends on the antenna.

Incorrect: 
- Gain = the ratio of increase in antenna strength
- Frequency hopping = method of transmitting radio signals by rapidly changing the carrier frequency among many distinct frequencies
- Geofencing = uses various wireless methods to create a perimeter around a certain area.

#

11. Which type of backup data contains customized settings for a router or switch?

- Configuration: Configuration data is stored in a text file so settings can be quickly recovered.

#

12. Theo must send highly sensitive data over his PPTP connection. What feature of PPTP will give him confidence that his data won't be stolen in route? PPTP = Point-To-Point Tunnel Protocol.

- Encrpytion

#

13. What type of sensor would show rising humidity levels in your equipment rack?

- Environmental Sensor: gauges temperature, humidity, electrical load.

Incorrect:
- Temperature sensor: falls under the job of an environmental sensor.
- Chassis Sensor: report any temperature changes to an individual system.
- Baseline: document that shows how the network is performing at optimal time.

#

14. What is the IPv6 version of ARP?

- Neighbor Discovery Protocol: NDP performs many of the same function as IPv4 ARP, but does more.

Incorrect:
- NTP: used to synchronize time for all devices on the network.
- DNS: resolves host name to IP address
- ARPv6: is not a term.

#

15. In order to broadcast to all nodes on a LAN, which MAC address will be used?

FF:FF:FF:FF:FF:FF : Broadcast address of all node on LAN.

#

16. Which of the following Ethernet standards use UTP cable? (Select two.)

- 1000BaseT, 100BaseTX

#

17. Which of the following are benefits of patch panels? (Select two.)

- Organize the horizontal cabling
- Protects the horizontal cabling from over handling

#

18. Governments strictly regulate which bands, and which channels within each band, that Wi-Fi systems can use. What is this called?

- Regulatory Impact: applies rather specifically to the chhannels in the 2.4 GHz range and more generally to the other ranges.

#

19. HTTP can be used to transfer files, but it is not as reliable or as fast as what protocol?

- FTP: can transfer files more quickly than HTTP.

#

20. You have 20 new employees that need e-mail accounts. Which of the following protocols do you need to set up the e-mail accounts? (Select two.)

- SMTP, POP3

#

21. Which of the following is good copper cabling for environments with heavy electrical interference?

- STP: Shield Twisted Pairs help reduce electrical interference which makes it the best choice of copper cabling.

Incorrect: 
- Fiber: might be better but not copper.
- UTP: lack of shielding make it susceptible to interference.
- Wireless networks rely on radio waves which are easily interfered with.

#

22. Which OSI layer adds unique identifiers to the packets, enabling the packets to be routed to the correct system?

- Network Layer: The Network layer (Layer 3) adds addresses (such as an IP address) to the packets.  These addresses uniquely identify devices on the network and are used by routers to make sure the packets are delivered to the correct systems. 

#

23. Something has changed and now no one within the organization can access the Internet. The ISP has checked everything beyond the demark and found no problems. Which are likely culprits for the outage? (Select three.)

- Throttling policy: The organization may have instituted a throttling policy that shuts down access to the internet after a certain amount of trafic has been exceeded.
- Customer premises equipment: ISP reported everything beyond demark is okay meaning it must involve CPE or Customer premises equipement.
- router Configuration: Something changed - default gateway router,  the whole organization could lose access to the internet.

Incorrect:
-  Misconfigured Wi-Fi Channel: usually automatically negotated and self resolved.
-  Local Loop: part of the ISP/Telco equipment and it has been reported as okay.
-  Satellite latency would cause slowdown but not complete disconnect from the internet.

#

24. A technician needs to manage a multi-layer switch with a secure connection. Which protocol should she use?

- SSH: This protocol uses encryption to make a secure connection as either client or server.

Incorrect:
- HTTP, SMTP, Telnet -  all unsecuremeans of communication.

#

25. What is the purpose of a VPN concentrator?

- Secure Network Access: The Concentrator is what you connect to when you are away from your network and want to VPN in.

Incorrect:
- MAC/ Content filtering: Restricting techniques, not connection tools.
- Connectivity troubleshooting: process to find out why host or device cannont comunicate with a network.

#

26. Which UDP protocol allows you to transfer files from one computer to another?

- TFTP: allows for data transfer between computers, but it provides no protection.

Incorrect: 
- FTP: 20,21 TCP not UDP.
- HTTP: protocol used for internet.
- Telnet: TCP 23

#

27. Which standard is commonly used to control thin-client wireless access points?

- LWAPP: Light Weight Acess Point Protocol: the most common protocol to control thin client wireless access point.

Incorrect:
- Wi-Fi: trademarked term to describe 802.11x wireless networking.
- 802.11n: Wi-Fi signaling standard
- MIMO (Multiple In Multiple Out): A way to use multiple antennas on a WAP to achieve maximum bandwidth utilization.

#

28. What is the technical term for an uplink port and the auto-sensing feature of ports in modern switches?

- MDI-X (Auto-medium-dependent-Interface-Crossover): new term for an auto sensing port.

#

29. What is the scale manufacturers use to show the signal between a WAP and a receiver?

- Received signal strength Indication (RSSI): Scale manufacturer uses to show the signal between Wireless Access Point and Receiver, the closer to 0 dB, the stronger the signal.

Incorrect:
- Signal Strength Readout: not a term
- Heat map: shows signal strength in specific areas.
- Effective Radiated Power (ERP): measure of signal strength coming from an antenna.

#

30. You are setting up a wireless network for a rather large, open floor plan, one-floor office. There are only about 8 employees that need to connect to the wireless access point. Where would be the best place to install the access point and with which type of antenna?

- Omnidirectional antenna in the center of the office on the ceiling: An omnidirectional antenna will send the signal out in all directions so it is best to place one in the center of the office since it is an open floor plan.

#

31. Which table maps a destination MAC address to a port within a switch?

- MAC Address lookup table: The MAC address lookup table maps destination MAC addresses to ports within a switch.

#

32. You just finished installing the last WAP in your building. However, you notice that several users in the area are not recognizing it as an available network. You decide this is a wireless coverage issue, but users are in offices and cannot move closer to the access point. What would be the MOST efficient step to take next?

- Turn up the power on the WAP: turning up the power takes the least amount of time and effort and it can help with insufficient coverage.

Incorrect: 
- Replacing antenna works, but it more time consuming and money.
- Upgrading to a newer 802.11 standard would require all new wireless NIC and WAPs, exetremely costly.
- Users cannot simply move to another location.

#

33. What is the term for the scenario where packets take one path to a destination but the response packet takes a different path?

- Asymmetric routing: The term is called asymmetric because the paths are different. 

#

34. What kind of malicious attack creates a buffer overflow to prevent regular users from accessing a system?

- DoS: A denial of service attack typically involves overwhelming a system with low-level requests (like pings) so that the system doesn't have time or resources to respond to real user requests.

#

35. You are installing fiber-optic cable, and you need to combine two fiber-optic cables without losing quality. What would you need to do this?

- Fusion Splicer: Used to combine two fiber cables without losing quiality.

Incorrect:
- Fusion emitter, Fiber Coupler, Fiber combiner are not valid fiber optic tools.

#

36. Which technique would be used to test the network security of a particular network by allowing it to accept security attacks?

- Honeynet: A Honeynet draws in attackers so their methods and location can be determined and subsequently protected against without jeopardizing vital information.

#

37. Janet is entering sensitive information into a database. Tom passes by and notices what she is typing and decides to ask Janet a question about the company party coming up over the weekend. What social engineering tactic is Tom using?

- Shoulder Surfing: act of looking over another user's shoulder to see what they are entering into their computer in order to gain access to sensitive information

Incorrect: 
- Masquerading: pretending to be a figure of authority and creating urgency so a user gives up sensitive information.
- Eavesdropping: listening in on a conversation in an attempt to gain sensitive information.
- Tailgating: following an authorized person into a building or room.

38. A school decides to issue Chromebooks to all of its students, but allows the option of students using their own laptop for schoolwork. However, a very watered-down plan is put in place for the students that use their own laptop. One day, you notice several students with their own device are trying to access inappropriate Web sites. What category does this fall under?

- BYOD Challenge: need to be addressed before allowing students or employees to connect to the network with their device. 

#

39. You notice that there has been heavier traffic than usual this week. Network utilization has slowed down the network significantly. Which document would you refer to in order to see how the network normally operates?

- Network Performance Baseline: show how the network should be operating under normal conditions.

Incorrect: 
- Performance Monitor Output: Tool to show what is happening. So, the output would be the reason to check the baseline.
- Network Monitoring Log: not really a term
- Syslog: tool used to listen to traffic and create various type of logs.

#

40. Which technology encompasses video conferencing, real-time video, fax, messaging, and collaboration/workflow tools?

- Unified Communication Technology: Combines and manages a collection of otherwise independent communication tasks.

Incorrect: 
- Medianets: Optimized iterations of video teleconferencing but this is only one small aspect of unified communications technology.
- VoIP: just one of many aspects of unified communication technology.
- Border Gateway Protocol (BGP): large scale routing protocol that is not directly related to unified communication.

#

41. You notice that your server experiences severe slowdown when many different services and applications are running. What Performance Monitor metric would indicate this?

- Memory Usage: Memory stores all open applications and services running in the background. Odds are the slowdown is due to low memory.

Incorrect: 
- CPU usage: would show if certain processes are hogging CPU time.
- Network usage: show bandwidth issues such as jitter and latency.
- Disk usage: show read/write activity.

#

42. To accommodate a growing department, a new switch was installed with little configuration. Hosts attached to the new switch sometimes connect to the network and sometimes they don’t. There is no discernable pattern to whether a node will successfully connect to the network. Which selection is the most likely cause of the problem?

- DHCP server misconfigured: Many times, an enterprise-grade switch comes with a built-in DHCP server.  Unless it is configured correctly or disabled altogether, it can generate conflicting or non-conforming IP addresses. 

#

43. Which would be the most effective solution when disaster planning?

- Cloud Site: ost effective because it is the fastest to get up and running again

Incorrect: 
- hot site: has everything a warm site does, but includes recent backups.
- warm site: is like a cold site, but has computers with software and functioning servers
- cold site: is a location that consists of everything that a business needs...except computers. A cold site generally takes more than a few days to bring online.

# 

44. Which would be the MOST secure way for an administrator establish a connection to a remote UNIX server?

- SSH: Secure shell, as the name implies, is an encrypted connection similar in function to Telnet.

Incorrect: 
- FTP, Telnet, and PPP are all sent in the clear, and therefore are not secure.

#

45. Before an Ethernet NIC may transmit data onto a medium, it must check to see if another NIC is transmitting data. What is this checking process called?

- Carrier Sense: Also known: Carrier detect, test that NIC perform prior to transmitting on a network medium.

Incorrect:
- Multiple Access: When the station transmit, all station on the segment will hear the transmission.
- Collision Detection: A station sending data can tell when another station transmits at the same time.
- Collision Avoidance: technique used by a network interface to recover from or prevent a collision.
