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

