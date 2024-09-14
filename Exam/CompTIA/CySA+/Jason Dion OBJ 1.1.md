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









