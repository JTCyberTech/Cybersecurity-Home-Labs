# Given a scenario, use appropriate tools or techniques to determine malicious activity.

# Tools and Techiques

Protocol Analyzer Uses
- Troubleshoot network issues
- Investiage security incidents
- Eavesdrop on confidential communications.

tcpreplay:
- Allow editing and replaying traffic

Account Monitoring Issues:
- Inaccurate Permission: Block work and/or violates least privilege
  - Privilege creep: condition occurs when user switch jobs and gain new permissions but never have old permission revoked.
 
Protect against Inaccurate Permission:
- User Account Audits: Pull listing of account permissions and review with managers to see if the permission is appropriate for user's role, make adjustments, prioritize reviedw of user with job changes.
- Attestation: Formal approval of user privileges
- Unauthorized Use: illegitimate actions by legitimate users.
- Continous Account Monitoring: watch for suspicous activity, alert admin to anonmalies
  - Access Policy Violations.
 
Geotagging:
- Tags logs with user location

Geofencing:
- Alert admin to devices leawving defined boundaries


#

## Packet Capture: Wireshark

- Open-Source
- built on libpcap library.

#

## Tcpdump

- Open source command line sniffing tool, protocol analyzer
- `tcpdump -n -i eth0` = capture all traffic
- `tcpdump -n -i eth0 'tcp port 22'` = capture all traffic with port 22 SSH
- built on libpcap library.


#

## Domain name service (DNS) and Internet Protocol (IP) reputation:

DNS (Domain Name Syste):
- Domain Name Server
- Info = very valuable to security analysts.
- DNS translates between domain names and IP addresses

Dig command:
- performs DNS lookup on Mac and Linux systems.
- `dig linkedin.com`
  - Answer Section; tells IP address of the domain name

Nslookup command:
- Performs DNS lookup on Windows systems
-`nslookup linkedin.com`

### WHOIS

- Discovers ownership info about domain and IP addresses.

Reverse WHOIS:
- Discovers domain assoicate with name or email address.
- ViewDNS.info

### AbuseIPDB

- IP reputation service.
- Check if the IP address has been assoicated with malicious activity.

# 

## SIEM (Security Information Event Management) 

- Security tool provide important insight into endpoint behavior.

User awnd Entity Behavior Analytics (UEBA)
- Compares user activity to indivduals baselines.
- Use Machine Learning to build models of normal user behavior patterns, flags any deviations from those patterns for review.


#

## Endpoint Detection and Response (EDR)

- Goes beyond basic signature detection and perform deep instrumentation of endpoints.
- Offer advanced real time protection against malware security threat.
- Using agents installed on endpoint devices watching malicious activity.

#

## File Analysis

Executable Analysis
- Static Analysis: Examine file for signs of malicious activity without actually executing file.
- Dynamic Analysis: Executes files in sandbox environment and monitors it for signs of malicious activity.


### VirusTotal:

Easiest way to check if the file is malicous 

### String:

- Digging in to the content of the file.
- Sysinternals tool, free downloads.
- Scans thru Windows executable file and extracts all text from file for your review.
- Help to find process names, domain names that mean clue you in to the file's purpose.

`strings splwow64.exe`
- String search thru file, locates all text elements that appear in file.

#

## Sandboxing - Cuckoo Sandbox

- Malware analyst tool
- Test suspicious file to determine whether it might display malicious activity.
- Open source.

Cuckoo Can Analyze:
- Executables
- Documents
- Email Messages
- Website URL

Cukcoo Features:
- API call tracing
- Use Tcpdump to capture network traffic
- Can perform deep memory analysis
- Windows, macOS, Linux, Android analysis.

#

## Sandboxing - Joe Sandbox

Performs analysis of submitted malware files



















