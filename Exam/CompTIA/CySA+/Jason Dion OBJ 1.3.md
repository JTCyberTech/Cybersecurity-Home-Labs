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


#

# Intrusion Detection System (IDS) 

- Software/Hardware system that scans  audits  monitors the security infrastructure for signs of attacks in progress.
- IPS = IDS that can actively block an attack.

Three common software that can config IDS or IPS:
- Snort
- Zeek (Bro)
- Security Onion

Snort:
- Open Source software available for Windows and Selected Linux that can operate IDS or IPS mode.
- Use Oinkcode that gives you all the latest security threats.

Zeek:
- Open Source IDS for Linux platforms that contains a scripting engine which can be used to act on significant events (notice) by generating alert or implementing some sort of shunning mechanism.

Security Onion:
- Open Source Linux platform for security monitoring, incident response, threat hunting that bundles Snort, Suricata, Zeek, Wireshark, NetworkMiner.

#

# Endpoint Analysis

Five endpoint protection tools:
- AntiVirus (AV)
- HIDS/HIPS
- EPP (Endpoint Protection Platform)
- EDR (Endpoint Detection Response Platform)
- UEBA (User and Entity Behavioral Analytics)

Anti-Virus (AV)
- Software that detects and removes virus infections and malwares: worms. trojans, rootkits, adware, spyware, password crackers, network, mappers, DoS tools.

Host-Based IDS/IPS:
- Type of IDS or IPS that monitors a computer system for unexpected behavior or drastic changes to the system's state on an endpoint.

Endpoint Protection Platform (EPP):
- Software agent and monitoring system that performs multiple security tasks such as anti-virus, HIDS/HIPS, firewall, DLP, file encryption.

User and Entity Behavior Analytics (UEBA):
- System that can provide automated identification of suspicious activity by user accounts and computer hosts.
- Heavily dependent on adv computing techni (AI and ML)
- Microsoft and Splunk

## Endpoint Detection and Respnse (EDR):

- Software agent that collects system adata and logs for anlysis by monitoring system to provide early detection of threats.

#

# Sandboxing

- A computing environment isolated from host system to guarantee the enviornment runs in controlled, secure fashion and that communication links between sandbox and host are usually completely prohibited.
- Allows quickly test malware in multi environments
- Should not be used for any other purpose except malware analysis

Flare VM:
- Allow to run Window binary on system and see what the status is and all the different changes the malware is doing.

## Cuckoo Sandbox

- Allow to automatically run different malware samples and see what they do inside of a Linux, Windows or Mac Environment.

## Joe Sandbox

- Allow a security research or cybersecurity analyst to analyze and understand behavior of malware sample in a safe and controlled environment.
- Emulate the environment of a real computer and allows malware samples to be run and analyzed in a safe and isolated environment.
- Provides a user-friendly interface to easily view and analyze collected data from these malware samples.

#

# Reverse Engineering

- Process of analyzing the structure of hardware or software to reveal more about how it functions.
- Java is easily decomplied back into source code.
- Attempt to identify malware by finding strings to use as a signature for rule based detection.

Malware writers often obfuscate the code before it is assembled or complied to prevent analysis


Disassembler:
- Computer program that translates machine language into assembly language.

Machine Code:
- Binary code executed by the processor, typically represented as 2 hex digits for each byte.

File Signature (Magic Number):
- First two bytes of binary header that indicates its file type.
- Hackers can put .exe at the end of a .png file, but the magic number will always tell what type of file it is.

- When reading first two bytes of Windows portable executable file (EXE  DLL  SYS  DRV  COM), it will always start with 4D 5A in HEX, MZ in ASCII or TV in Base64 encoding.

Assembly code: 
- Native processor instructions used to implement the program

Decomplier:
- Software that translates binary or low level machine language code into higher level code.

High-level Code:
- Real or Pseudocode in human readable form that makes it easier to identify functions, variables, and programming logic used in the code.
- C, Java

Program Packer:
- Method of compression in which executable is mostly compressed and part that isn't compressed contains code to decompress the executable.
- type of self-extracting archive

## String

- Any Sequence of encoded charawcters that appears within executable file.
- If malware contain string with function called InternetOpenUrl,  another string that is a URL probably attempts to download something from that web address.
- Tool: dump all strings with over 3 characters in ASCII or Unicode encoding to a text file or to your screen to analyze.

#


# Malware Exploitation

Exploit Technique:
- Specific method by which malware code infects a target host.
- Fileless techniques: Avoid detection by signature based security software.

1. Dropper or downloader
- Run lightweight shell code on your system
- Trick user into clicking on something or running the code, and that way, they are infecting their own machine.

2. Maintain Access
- Malware is on the system, will install stage downloader, download something like remote access Trojan. 


3. Strength Access
- Use remote access tool, start looking around and identify and infect other system.
- System that have higher values (Servers or Domain Controller)


4. Actions on Objectives
- Copying/Stealing files
- Encryping files 


5. Concealment
- Maintain their tool access, might start hiding themself, covering their track/ deleting logs.


Dropper:
- Malware designed to install or run other types of malware embedded in a payload on infected host.

Downloader:
- Code that connects to internet to retrieve additional tools after initial infection by a droppper.

Shellcode:
- Any lightweight code designed to run an exploit on the target which may include any type of code format from scripting language to binary code.

Code injection:
- Exploit techni that runs malicious code with the identification number of legitimate process.

Living off the Land:
- Exploit techni that uses standard system tools and packages to perform intrusions


# Behavior Analysis

Sysinternals:
- Suite of tools designed to assist with troubleshooting issues with Windows and many of the tools are suited to investigating security issues.

System Idle (PID 0)/ System (PID 4)
- Kewrnel level binaries that are used  as parent of the first user-mode process (Session Manager SubSystem - smss.exe)

Client Server Runtime SubSystem (csrss.exe)
- Manage low level Windows functions and it is normal to see several of these running (as long as they are launched from %SystemRoot%\System32 and have no parent)

WININIT (wininit.exe)
- Manage drivers and services and should only have a single instance running as process

Services.exe 
- Host nonboot drivers and background services and should only have one instance running as a child of wininit.exe
- Services will be started by the SYSTEM, LOCAL SERVICE or NETWORK SERVICE accounts.

Local Security  Authority SubSystem (lsass.exe)
- Handles authentication and authorization services for system and should have a single instance running as child of wininit.exe

WINLOGON (winlogon.exe)
- Manage access to the user desktop and should have only one instance for each user session with Desktop Window Manager (dwm.exe) as a child process in modern versions of Windows.

USERINIT (userinit.exe)
- Set up the shell (typically explorer.exe) and then quits, so you should only see this process briefly after log-on.

Explorer (Explorer.exe)
- Typcial user shell launched with the user's account privilieges rather than SYSTEMS's which is likely to be the parent for all processes started by logged on user.

```
Single idle and system PIDs
One wininit.exe
One services.exe others should be children of services.exe or svchost.exe (just a wrapper)
System services should be digitally signed
Services should be launched by either the SYSTEM, LOCAL SERVICE, or NETWORK SERVICE accounts
One lsass.exe
One winlogon.exe
Userinit.exe should not persist
Explorer.exe file manager and parent process
```

Found a suspicious process? Check the following:

```
Read/write file access
Launch location
Obfuscated/compressed
Parent process
Try killing it
Network traffic
Sysinternal Process Explorer
Tasklist command
Sysinternals Autoruns
```






















