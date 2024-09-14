# Firewall Logs

4 types of useful security data:
- Connections that are permitted or denied
- Port and protocol usuage in Network
- Bandwidtth utilization with duration/volume of usage.
- Audit log of network or port address translations (NAT/PAT) that occurred

iptables:
- Linux firewall that uses syslog  file format for its logs.
- Timestamp, Device ID or hostname, facility (kernel), log prefixed value or log level
- Inbound and Outbound
- Mac address
- Source address, Destination address
- Info about packet: Length, TOS, precedent, TTL, Protocol, source port, destination port

CIS log value:
- 0 to 7
- 0 = Emergency
- 1 = Alert
- 2 = Critical
- 3 = Error
- 4 = Warning
- 5 = Notice
- 6 = Informational
- 7 = Debug
- "Every Action Can Earn Wins, Not Immediate Defeats."


Window Firewall:
- Window firewall uses W3C Extended Log File Format
- Easier to read
- Software, Version, Date, Field
- Last line = Log file itself

Employ log collection tool to gather large volume of firewall logs for later analysis:
- How much you want to log?
- What is important thing to log?
- Where you going to place sensors/firewall to collect information and provide best protection?
- Log retention, how long you going to retent these logs.
  - Detemine by number of events generated and available storage capacity.  

Blinding Attack:
- Condition occurs when firewall is under resourced and cannot log data fast enough, therefore some data is missed.

#

# Firewall Configuration

Screen Subnet:
- Physical or logical subnetwork that contains and exposes an Org's external facing services to an untrusted network likew the Internet.
- Used to be called DMZ

ACL:
- Firewall rule sets
- Processed from top to bottom, most specific rules = top.
- Block incoming request from internal or private loopback and multicast IP address ranges.
- Block incoming requests from protocols that should only be used locally (ICMP, DHCP, OSPF, SMB)
- Configure IPv6 to either block all IPv6 traffic or allow it to only authorized hosts and ports.

Drop Vs. Reject:
- Deny rule can either drop a packet or explicity reject it by sending a TCP EST or ICMP port/protocol unreachable to the requester.
- Dropping traffic makes it harder for an adversary to identify port states accurately.

Firewalking
- Reconnaissance techni to enumerate firewall config and attempt to probe host behind it.
- Occur when attacker can find an open port on firewall, then sends a packet with TTL of one past the firewall to find its host.
- Prevent: Block outgoing ICMP status messages.

Egress Filtering:
- Applies ACL rules to outgoing traffic to prevent malware from:
  - Communicating to C2 servers
  - Fingerprinting our network
  - Firewalking our network
  - Stopping anything frome leaving our network.
 
Best practices for config egree filter:
- Only allow whitelisted application ports and destination addresses.
- Restrict DNS lookups to trusted and authorized DNS services.
- Block access to known bad IP address range (Block list)
- Block all internet access from host subnets that do not use it (ICS/SCADA)

Black Hole:
- Mean of mitigating DoS or Intrusion attacks by silently dropping (Discarding) Traffic
- More efficient at router level instead of firewall level.
- Can stop DoS attack at the routing layer by sending traffic to null interface.
  - Drop any traffic that comes to it.
- Good case: Use against dark nets.

Dark Nets:
- Unused Physical network ports or usused IP address space within locawl network often used by attackers.
- Example: /16 network, might use 1000 - 2000 out of the 16000 IP. Route the extra IP into a black hole.

Sinkhole:
- DoS attack mitigation strategy that directs traffic ethat is flooding a target IP address to different network for analysis.
- Different: instead of dropping traffic (black hole), send it to another network for analysis (sinkhole)
- Better than black hole if you want to know the cause of the DDoS attack

CloudFlare or Akamai:
- Solution to implement Blackhole and Sinkhole
- Large ISPs that specialized in DDoS mitagation service.

#

# Port Security

- The blocking of unauthorized application service ports on hosts and firewalls, or the physcial/remote access ports used to allow a host to communicate on local network.

Best practices to secure Network Appliances:
- Use ACLs to restrict access to designated host devices.
- Monitor number of designated interfaces
- Deny Internet access for remote management


Three Types of Port Security:
- Physical Port Security
- MAC Filtering
- Network Access Control (NAC)

Physical Port Security:
- Physical Access to switch ports and switch hardware should be restricted to authorized staff.

MAC Filter:
- Applying Access control list to a switch or access point so that only clients with approved MAC addresses can connect to it.

Network Access Control (NAC)
- Collective Protocol  policies  hardware that authenticate and authorize access to a network at the device level.

#

# Network Access Control Configuration

NAC 
- Provides means to authenticate users and evaluate device integrity before a connection is permitted.

802.1X
- Standard for encapsulating EAP (Extensible Authentication Protocol) communication over a LAN or wireless LAN and provies port-based authentication

Port-based NAC:
- Switch or router that performs some sort of authentication of the attached device before activating port.

#

# Blocklist and Allowlist

Software Restriction Policies (SRP)
- Create an allow list file for different system locations where your executable and scripts are allowed to be launched from.

AppLocker:
- Used to improve the configuration options and defaults of the SRP

Windows Defender Application Control (WDAC)
- Allows to create a code integrity policy, and this can be used on its own or in conjuction with AppLocker.

Configuration Management
- Allows for having a process in place of how we're going to update all of our block lists and our allow lists for any of those changes.

