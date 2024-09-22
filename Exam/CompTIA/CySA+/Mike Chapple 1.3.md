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

#

## Email Analysis

SMTP: has very little built in security.
- Unencrypted email is prone to eavesdropping attacks

Digital Signatures:
- Use asymmetric cryptography to achieve integrity, authentication, non-repudiation.
- Signed Message Recipients knows:
  - Owner of public key is the person who signed the message (authentication).
  - The message was not altered after being signed (integrity).
  - The recipient can prove these facts to a third party (non-repudiation).
- Digitally signing messasges does not provide confidentiality.
 
Use of Digital Signatures depends Two important concepts:
- Hash functions are collision resistant. (can't have the same hash value)
- Anything encrypted with one key from an asymmetric key pair may only be decrypted with the other key from that pair.
  - Private key = encryption, Public key = Decryption.

![image](https://github.com/user-attachments/assets/ce08956f-623f-4c49-9136-98308b3c04a8)



### Impersonation

- Anyone can forge an email message impersonating the sender of their choice.

#

### Sender Policy Framework (SPF)

Provides domain owners with ability to list servers that are authorized to send mail from domain.
- Create a DNS record that lists the servers that is allowed to send email for domain.
- Those records are called SPF records

SPF = important tool:
- Helps to prevent forged email
- Doesn't prevent tampering email.

![image](https://github.com/user-attachments/assets/bcf2d721-4c8b-42cd-b60e-405f80abb11f)

### DomainKeys Identified Mail (DKIM)

Provides email authentication by allowing mail servers to digitally sign legitimate outbound email messages.
- Uses Public/Private Key Pairs
- Public keys are published thru DNS.
- Private key is kept secret.

![image](https://github.com/user-attachments/assets/5a21dc7c-25df-42f7-96f1-7372d4474730)

Dkim=pass: means the mail server that received this message verified the DKIM signature.

Valuable Tool:
- Protect email, used to combat spam/phish that sends spoofed email using domain names belong to someone else.

### Domain-based Message Authentication, Reporting and Conformance (DMARC)

Provies domain owners with ability to specify SPF and DKIM policies for their domains.


![image](https://github.com/user-attachments/assets/0982181b-a2ae-469d-94ca-f8866d535c9a)

- v=DMARC1: version 1 of DMARC being used.
- p=reject: policy that linkedin wants people to apply to email that they receive that does not pass DKIM and SPF checks. Reject those emails. (Can be set to Quarantine or None)
- rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; = DMARC feedback should be sent.
- pct=100": specification that policy should apply to 100% of email sent from the domain.

### Header

- Might be asked to analyze email header on CySA+ exam.

![image](https://github.com/user-attachments/assets/81bdb458-b733-4168-b564-78dedfc50279)

![image](https://github.com/user-attachments/assets/ed5695c2-2b6c-49e3-9f09-2715c67d4b3c)

#

## User Behavior Analysis

### Abnormal Account activity

- Unusual network location logins.
  - Users who always login in HR network, logging in guest network.
- Unusal time-of-day logins: mail clerk logging into system in middle of night.
- Deivations from normal behaviors: users accessing files that they don't normally access.
- Deivations in volume of data transferred: bulk downloading of sensitive info

### Impossible Travel

- Logon from strange geographic locations, user connecting from both home office and remote location in Eastern Europe at the same time.
- Risky logins.



































