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
