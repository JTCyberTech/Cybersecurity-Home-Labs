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

1. 
