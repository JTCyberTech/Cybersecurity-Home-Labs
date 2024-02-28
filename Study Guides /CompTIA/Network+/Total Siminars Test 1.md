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

10. Your network administrator has decided to remove WINS from the network and replace it with DNS. Your WINS server resolves requests to 20 address locations on your network segment. What's the BEST way to ensure that users can reach those addresses by host name automatically?

- Request that the hostnames and addresses be added into DNS: best way = add entries to the DNS server.

Incorrect:
- Adding entries to the HOSTS files would work but this would need to be done on every workstation.
- Adding WINS proxy is not an option since the WINS server is being taken out of the network.
- Entering hostnames into the LMHOSTS file wouldn't do much because LMHOSTS is for NetBIOS resolution, not DNS.
