# Harvesting Techniques

## WHOIS  

A public listing of all registered domain and their registered admins.

#

DNS Zone Transfer:
- Method of replicating DNS database across a set of DNS servers that is often used during reconnaissance phase of attack.

DNS Harvesting:
- Uses OSINT to gather info about a domain

Website Harvesting:
- Technique used to copy source code of website files to analyze for information and vuln

#

# AbuseIPDB

Community driven database that keep track of IP addresses reported for abusive behavior.
- Enables Org to take proactive approach to its cybersecurity.


#

# Tcpdump

Data network packet  analyzer that runs under CLI and displays TCP/IP that is transmitted or received on a network.



#

# Wireshark 

Free/Open Source GUI based packet analyzer used for network troubleshooting, analysis, software and communications protocola development and education.

#

# Flow Analysis

Full Packet Capture (FPC):
- Captures entire packet, including header, payload for all traffic.

Flow Collector:
- Means of recording network traffic's metadata and statistics about network traffic, rather than recording every frame.
- Capture info about flow instead of data itself
- save a lot of space.
- Won't have the contents of what was going over network. Just info about it.
- Can help us to highlight trends and patterns in traffic being generated.
- Allow us to get alerts based on anomalies, different patterns and triggers.

#

# IP and DNS Analysis

Malware used to be configured to contact specific static IP or DNS name as part of its code.


Known bad IP Address
- IP addresses or range of addresses that appears on one or more block lists.
- Reputation-based risk intelligence is used to create IP/URL Blocklist.

Bypass:
- Attacker use domain generation algorithms to overcome blocklist.

Domain Generation Algorithm (DGA)
- Method used by malware to evade blocklists by dynamically generatingw domain names for C2 network.

1. Attacker sets up one or more Dynamic DNS services
- Allow attacker to be able to have domain name that can automatically generate anytime.
- Attacker sign up with service using fake payment/credentials.

2. Malware code implements a DGA to create a list of new domain names.
- Algorithm that uses some kind of seed or random number or time based.
- A start date = seed, going to create output of a bunch of cryptic strings that basically have numbers and letters to make up domain names.


3. Parallel DGA is used to create name records on the DDNS service
- Need the  DDNS service to have it so those two can match up.
- If they both use the same seed, they're going to have same matching names.

4. Malware tries a selection of domains it has created to connect to C2.

5. C2 server communicates with a new seed for DGA to prevent being blocked

DGA: dynamic list that is constantly changing.
- Constantly chaning architecture, also known as fast flux network.

Fast Flux Network
- Method used by malware to hide presence of C2 networks by continually changing host IP addresses in domain records using domain generation algorithms.

How can DGA be detected?
- See a lot of call outs from your systems to random IP addresses that looks: `A1ZWBR93.com` `94ZGYS9.com`
  - Random series of letters/numbers.com
- If you get high rate of NXDOMAIN errors when resolving the DNS, it could be an indicator of DGA.
  - Site error: `DNS_PROBE_FINISHED_NXDOMAIN`
 
Migitation for DGA:
- Use Secure Recursive DNS Resolver

Secure Recursive DNS Resolver
- Allow one trusted DNS server to communicate with other trusted DNS server to search for IP address and return it to client.

#

# Proxy Logs

Proxy server:
- Act as a gateway between you and internet.
- Intermediary server that separates end users from websites they are trying to browse.

Forward Proxy: 
- Server that mediates the communication between client and another server, can filter or modify communications and provides caching services to improve performance.
- Go from me > Proxy Server > website I want to connect.

2 ways to classify proxies:
- Non-Transparent
- Transparent

Non-Transparent Proxy:
- Server that redirects request and responses for clients config with proxy address and port.

Transparent Proxy (Forced or Intercepting Proxy):
- Server that redirect requests and responses without client being explicity config to use it.
- Used to make sure your employees aren't turning off your proxy.

Proxy log are very similar to Window Firewall logs.


Reverse Proxy:
- Type of proxy server that protects servers from direct protects servers from direct contact with client request.
- Provide for protocol specific inbound traffic.
- Get request from internet > Proxy server > Proxy create appropriate request to internal server (mail server or web server) > external client.
  - External client never directly touches your server, only touches proxy server
  - Help protect things from malicious traffics.
 
- Logs from reverse proxy:
  - Can be analyzed for indicators of attack or compromise (malicious code in HTTP request header/URLs)

#

# Web Application Firewall (WAF)

- Firewall designed to protect software running on web servers and their backend databases from code injection and DoS attack.
- Prevent web-based exploits and vulnerabilities like SQLi, XMLi, Cross-site scripting (XSS) attacks.














