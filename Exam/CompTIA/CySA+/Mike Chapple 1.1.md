# Operating System Security

## Goals of Information Security

CIA 

## Roles of Cybersecurity Analyst

- Responsible for proactively defending and continuously improving sescurity.

5 Core task for Cybersecurity Analyst:
- Leverage intelligence and threat detection
- Analyzse and intercept data
- Identify and Assess Vulnerabilities
- Suggest preventative measures
- Respond to and recover from incidents

## Operating System Security

### System Hardening

Analyzing the default settings of your OS and removing services that are not required to meet your business needs.
- Remove unnecessary software and OS components.
- Lockdown the host firewall config
- Disable default accounts and passwords.
- Confirm Windows Registry and Linux config settings match best practices.

### Windows Registry

Database of configuration information and settings
- Crucial to cybersecurity.
- Organized into five major categories: Root Key or Hives.

![image](https://github.com/user-attachments/assets/a9f47dbd-03d0-4d34-8750-bf8d3f6378b9)


### Configuration files location - File Structure

Operating systems store configuration files in different locations on disk.

- Linux Configurations Files: `/etc Directory`
- Mac Configuration Files: `/Library/Preferences`
- Windows Configuration Files: `C:\ProgramData\` or `C:\Program Files\`

### System Processes

Software supporting the running operating System.
- Windows can use Task Manager to see what processes are running.

Exam Tips:
- Understand that system processes are critical parts of OS.
- Attacker often name processes to look similar to legit processes to help hideing malicious software
- Attacker often target these processes to try to gain privileged access to the OS.

### Hardware Architecture

Instruction set supported by a computer.
- x86 Architecture: Used on majority of modern computer systems on chips manufactured by Intel and AMD
- ARM Architecture: Used on mobile devices and in Apple M-series processors.

Exam Tips:
- Software compiled for one hardware architecture won't run on systems using a different architecture.

#

# Logging Security Information

Log and Data Sources
- Network or NetFlow logs: tells about systems on network that communicated with each other and amount of info they exchanged.
- DNS logs: Provides info about network name lookups, offering insight into which systems may have communicated with external systems
- System logs: provide insights into inner workings of the OS, recording security events and other activity on system that might reveal details of an attack
- Application logs: provides info about activity that occurred at application level. Including application login, access to data.
- Web Application logs: Tell about SQLi attacks or other malicious activity.
- Authentication logs: help us determine who may have used a centralized authentication service and what internal and external systems and applications they accessed thru that service.
- VoIP logs: provide insight into nature of traffic on networkw using SIP (session intiation Protocol)
- Dump files: From network traffic  memory analyzer of raw security info.
- Vuln scan output: Can assist in incident response, providing clues about vuln attackers may have targeted on system.

Syslog:
- Provides a logging standard

Syslog Message Components:
- Header (timestamp, source address)
- Facility (source of message on sending system)
- Severity (importance value from 0 to 7)
- Message (details of situation)

Syslog Severity Levels:

![image](https://github.com/user-attachments/assets/2838082a-7924-4e4a-9263-717fe559b509)


Tag Facilitate Searching, Filtering and Analyssis.

#

# Security Information and Event Management

Systems generate far too many log records for manual analysis.
- AI can help solve security data overload

Security Information and Event Management (SIEM)
- Central secure collection point of logs
  - All systems send log entries directly to SIEM.
- Source of AI
  - SIEMs detects patterns that other system might miss
 
SIEMs have access to log entries from across the Org.

SIEM dashboard:
- Provide centralized view of security information
- Generate alerts for unusual activity.
- Facilitate trend analysis.
- Offer adjustable sensitivity

## Security Orchestration Automation and Response (SOAR)

- Enhanced version of SIEM
- Not only correlate security information but also automatically response to specific circumstance
  - By facilitating two different types of response
 
Playbooks:
- Process focused responses to security events, including both human and automated actions

Runbooks:
- Completely automated steps to SOAR platform perform when triggewred by an event.
- Gathering information for analysis, augmenting log entries, isolating suspect systems, notifying admin of an activity.
- Execute automatically and quickly to rapidly faciltate response and aid human investigators. 

#

# Tuning and Configuring SIEMs

SIEM Performance Tuning:
- Customize the configuration for your environment to show useful info for yourself.
- Modify rules to prevent false positive alerts
- Block Trivial and irrelevent SIEM alerts

## Time Synchronization

Synchronizing System Clocks:
- Enables consistent analysis
- Use a centralized time server: NTP (Network Time Protocol)

#

# Continous Security Monitoring

Continuous security monitoring facilitates real-time response

Continuous Monitoring
- Maintaining ongoing awareness of information security, vuln, and threats to support organizational risk management decisions.

Monitoring Process:

![image](https://github.com/user-attachments/assets/02b0ca59-818f-4d77-9a01-1eaa33eb7a7e)

Anomaly Analysis (Heuristic Analysis):
- Detect outlier data points

Trend Analysis:
Detect changes over time 

Behavioral Analysis:
- Detect unusual user activity and identify suspicious action

Availability Analysis:
- Provides uptime information

#

# Infrastructure Concepts

## Virtualization

- Host machines run on physical hardware
- Host machines provides services to several virtualized guest machines
- Hypervisor trick each guest into thinking it is running on dedicated hardware

2 Types of Hypervisor:
- Type 1 Hypervisor (Baremetal): runs directly on top of the hardware, then hosts guest OS on top of that.
- Type 2 Hypervisor: Physical machine run an OS of its own and hypervisor runs as a program on top of OS. (Commonly used on Personal Computers)

Virtualization Security:
- Virtual machine isolation is critical
- Each server must have access to only its own processor and memory
- VM escape attacks attempt to break out of the guest environment

VM Sprawl:
- Unused and unmaintained Servers
- Not properly maintain, can accumulate security vuln

#

## Severless Computing - Cloud infrastructure Components

- Severless Computing: Provides customer with ability to execute function in variety of progrtamming lanuages
- Containers: next level virtualization, allow customer to design portable computing environment that easily be moved between different platforms and OS.
- PaaS and SaaS: rely upon computing hardware, bujt also make hardware invisible to the end users.

Management Plane:
- Dedicate network for infrastructure admin

#

## Containers

- Lightweight application virtualization
- Easily moved between hardware platforms

VM runs its own OS that runs the same hypervisor
- Each one have to have their own operating system and components
- If running 10 different Windows Vitual server on hypervisor, you have run 10 different copies of  Windows at the same time.

![image](https://github.com/user-attachments/assets/444f7ae9-4646-4041-9fd7-4af4937484e3)

Containerization reduce this burden by building lightweight packages:

![image](https://github.com/user-attachments/assets/51ba875b-bb33-4db8-b7ce-8e8c7f9f88d3)


Container:
- Contain application coded and dependencies only
- Run on containerization platform
- Don't have their own OS
- Use the host's operating system

Container security:
- Isolation is the most critical issue.

#

# Network Security

## Network Architecture

- Defines structure of a network.
- on-premises, cloud, hybrid

## On-premises

- Composed of routers, switches, security devices, cablings
- Network security soluition:
  - Firewalls
  - IPS/IDS
  - Content filtering and caching
  - Network Access Control
  - Network Scanners
  - Unified Threat Management (UTM)
 
## Cloud  

- The use of cloud computing requires a different approach to network security.
- SaaS or PaaS, vendors handle network security issues by including language in your contract
- IaaS; AWS, Microsoft Azure, Google: provides more access to infrastructure, only need to handle some network security config yourself.

## Hybrid

- Combine on-prem and cloud networking.
- Need to secure each environment separately and in coordination.

#

# Security Zones

## Network Segmentation

Network Border Firewall:
- 3 network interfaces, connecting 3 different security zones 
  - interface 1 connects to internet or another untrusted network.
  - interface 2 connects to Org's intranet zone; divides into endpoint network, wireless network, guest network, data center network
  - interface 3 connects to the DMZ, where you place system that must accept connections from the outside world; mail and web servers
 
## Zero Trust

- System gains no trust based solely upon network location.

Extranet: 
- Intranet segments extended to business partners

Honeynet:
- Decoy network designed to attract attackers.

Ad Hoc Network:
- Temporary network that may bypass security control

East West Traffic:
- Network traffic between systems located in data center.

North South Traffic:
- Network traffic between systems in the data center and systems on the internet.\

# VLAN and network segmentation

- Used to connect people who are on differnt part of network to each other and separate them from other users.

VLANs extend broadcast domain
- Users on same VLAN will be able to directly contact each other as if they were connected to the same switch
- Layer 2

Configuring VLANS
- Enable VLAN trunking allowing switches in different locawtions on the network to carry the same VLANs
- Assign swaitchports to VLANs

#

# Zero-Trust Networking 

Approaches to security place trust in individuals rather than networks.
- Identity and Access Management (IAM) platforms are the foundation of zero trust approaches.
- SIEM and SOAR platforms facilitate monitoring.

Cloud Access Security Brokers (CASB) enfore security policies in the cloud
- Allow to create a set of coherent security policies in central location then automatically apply those policies to cloud services used by Org.
- Allow to monitor use of those cloud services, watching for indications of unauthorized activity.

Endpoint Detection and Response (EDR)
- remediate endpoint security issues.

Geofencing
- Alerts when device leaves an area.

#

# Secure Access Service Edge (SASE)

Network security arhitecture are shifting awsay from permeter focus.
- Zero-Trust Network Access (ZTNA)
- Secure Access Service Edge (SASE)

ZTNA:
- No user or device should ever be granted access to resources based solely upon their location on network.
- Zero Trust relies on strong authentication and identity management practices.
- Medium term objective

SASE:
- Delivers fully integrated network with ZTNA
- long term goal.

SASE Component:
- Software defined Netwoking (SDN)
- Zero trust Network Access (ZTNA)
- Cloud access security broker (CASBs)
- Firewall as Service (FWaaS)

#

# Software-Defined Networking (SDN)

- Technology that allows network admin to treat the functionality and implementation detail of a network as separate and distinct function
- Separates the control plane from the data plane.
- Makes the network programmable.
- Disadv: increase network complexity; need a strong access control.

SDN Security Benefits:
- Allows granular network config
- Facilitates faster response to security incidents.

Control Plane:
- Responsible for making routing and switching decisions, determine how data flows around network.

Data Plane:
- Responsible for carrying out the instruction of the control plane.

#

# Identity and Access Management

- Identification: Individual makes claim about their identity. Person doesn't have any proof at this point. (Can be making a false claim)
- Authentication: During authentication step, the individual proves their identity
- Authorization: Prove that you are allowed to enter the system.

Concept in digital world example:
- Identification: Identify ourselves using a username.
- Authentication: Password.
- Authorization: Access control list.

Triple A:
- Authentication, Authorization, Accounting



False Acceptance
- System misidentify you as authorization user
- Measured by False Acceptance Rate (FAR)

False Rejection
- System fail to recognize authorized user
- Measured by False Rejection Rate (FRR)

Crossover Error Rate:
- Admin tune the system to have equal false acceptance and false rejection rates.

Password Authentication Protocol (PAP)
- Does not use any encryption for protection

Challenge Handshake Authentication Protocol (CHAP)
- Alternatikve to PAP but with more protection
- Use hash value for response for the password instead of checking if password is the same.

#

## Multifactor Authentifcation (MFA)

Authentication Factors:
- Something you know
- Something you are
- Something you have

Combine Authentication/Multi Authenication:
- Use two or more techniques for authentication.

#

## Single Sign On

Authentication system that shares a single authentication session across multiple systems, avoiding asking user to log in mutli times.

#

## Federated Identity Management

FIM = Federated Identity Management

- Individual may have accounts across multiple systems
- Federated identity management systems share identity information
- This reduces number of individual identities a user must have.

Example of Federated Identity:
- Google Federation
- Facebook Login
- Twitter Login

Shibboleth:
- Designed to work in federated situations
- For students and facilities.

#

## Passwordless Authentication

Replaces passwords with more secure authentication techniques.
- No need password, relies on Biometrics or cryptographic keys.
- Cryptographic keys: Randomly generated string of characters used to authenticate users, stored on stored device or USB security token.
- Generally one factor approaches rely single authentication mechanism.
- **Passwordless approach doesn't mean multi-factor authetication**.

#

## Privileged Access Management (PAM)

Solutions safeguard administrative Accounts.
- Monitor privileged Users.

Password Valuting 
- Store Admin passwords
- Nobody knows the actual password for the previlieged accounts.
- User logs in privileged acc > logs in the password vault > password vaults logs into target system.

Command Proxying:
- Eliminates needs for direct server access

Monitoring:
- Logs admin user activity.

Credential Management:
- Rotates passwords and access keys

Provides emergency access workflow:
- Some cases, user needs to bypass privilieged account manager and access system directly withj admin right.

#

## Cloud Access Security Brokers

Use of cloud services makes it difficult to track sensitivew information.

Issue of using cloud services:
- Service Use: employees may use cloud services without the knowledge of or approval from IT and security teams.
  - Can transfer sensitive info into the cloud account without knowing.
- Service Configuration: Employees might config security settings that violate Oeg security policies.
  - Employee using an approved cloud storage service might share a file with personal email or make file public.
 
Cloud Access Security Brokers (CASB)
- Enforce security policies across cloud services.
- Tech solution that insert themselves between end user and cloud services and inject security controls enforce Org's security policy.
- Allow IT team enforce internal requirements for access control, authentication, encryption, firewall, malware protection, monitoring, DLP, Content filtering.

CASB Soltions:
- On Premises CASB: Intercepts network traffic headed to cloud services.
- Cloud-Based CASB: Uses APIs to interact with cloud services.

CASB imporatant roles:
- Provides visibility into cloud use, provide Org's technology team insights into how employees/users using cloud.
- Offers Data Loss Prevention (DLP) capabilities, extends Org's DLP policies into cloud by examining data placed into cloud and monitoring sensitive data for DLP violations.
- Injects encryption into the cloud, encryption before data reaches the cloud services and handling key management.
  - Config CASB to intercept and encrypt all files heading to cloud then transparently decrypt data return from cloud.
  - Provide end user with seamless experience, decrease breach possibility.

#

# Encryption

Cryptography:
- Use of mathematical algorithm to transform info into an encryption form that is not readable by unauthorized individuals.

Two Basic operation for Cryptoagraphy:
- Encryption: Convert info from plaintext form into ciphertext
- Decryption: Perform reverse transformation, using algorithm to transform encryption information back into plaintext.

Symmetric Encryption:
- Shared Secret Encryptoin Algorithm.
- Encryption and Decryption use same secret key.
- Shared secret key = password to a message.
- 3 people that wants to communicate, needs 3 keys.
- Formula for computing the number of symmetric keys required for a group to communicate:
  - n(n-1)/2
- Get too large, too many keys when number of people gets bigger. (Unmanagable; 10000 people = 50 mil keys)

![image](https://github.com/user-attachments/assets/2f3874aa-8472-4b9b-a810-7bf35283aef7)


Asymmetric Encryption:
- Public key cryptography
- Encryption and Decryption use different keys from the same pair.
- Solve the unmanagable key distribution problem by using keypairs.
- Each users gets 2 keys:
  - Public key: freely distributed to anyone that wants to communicate.
  - Private key: Kept secret
- Anything encrypted with one key from a pair can be decrypted with other key from same pair.
- Sender would encrypt with recipient's public key; Publicity known.
- Recipient use their own private key to decrypt.
- Slower than symmetric cryptography

Exam Tip: Keys used to encrypt  and decrypt using asymmetrtic cryptography must be from the same pair.


![image](https://github.com/user-attachments/assets/07771b1d-19d8-45e5-9b49-a5a60b3b657d)


Five Goals achieve by using Cryptography:
- Confidentiality: No unauthorized access for Data at Rest, Data in Transit, Data in Use.
- Integrity: No unauthorized change
- Authentication: Proof of identity claim
- Obfuscation: Hide sensitive data
- Non-Repudiation: Reciption of message can prove to an independent third party that the message actually came from alleged sender, Verification of Origin.
  - Digital Signatures provide Non-repudiation
  - Only possible with Asymmetric Cryptography.

Trust Models:
- Personal Knowledge
- Web of Trust (WOT)
- Public Key Infrastructure (PKI)

Web of Trust:
- Recognize simply isn't possible for you to personally meet everyone that you want to exchange message with.
- Relies on indirect relationships; LinkedIn, Third party level connection.
- Participants digitally sign the public keys of people they know personally.

Web of Trust Issues:
- Decentralized approach, makes it difficult to manange
- High barrier to entry for new people.
- Requires technical knowledge on behalf of user.

#

## Public Key Infrastructure (PKI)

Builds upon the Web of Trust
- Solves many of the practical issues associated with Web of Trust by introducing the concept of certificate authorities.
- Rely on the trust the participants have in highly trusted centralized service providers.
  - Provider = Certificate Authories form basis of PKI
 
Certificate Authories (CA)
- Trusted third party Org
- Verify identity of individuals or Org then issue digital certificates containing:
  -  identity info and copy of subject's public key.

Digital Certificates:
- identity cards of the digital world.
- Approach Certificate Authority to obtain
- CA will ask to prove your identity for different standard for different individul/Org.
  - Verify ownership of Domain name
- CA satisfied by the proof, then provide CA with your public encryption keyt over secure channel.
  - CA uses this info to create digital certificate that contain info about your identity and public key.
  - CA digitally sign the certificate.

#

## TLS and SSL

Transport Layer Security (TLS)
- Uses CA's Certificate to facilitate securew communication over public networks.

Example of TLS: Two systems follow when they wish to set up an encryptin session protected by TLS.
- Client sends a request to server asking server initiate a secure session. This request includes list of cipher suites supported by client
- One server receives that request from client, it analyze the list of cipher suites that client proposes and compares it to list of algorithms support by server.
- Send a message back to client with two pieces of information:
  - Tells client which cipher suites it would like to use for communication.
  - Server sends the client the server's digital certificate, contain server's public encryption key.
- When Client receive the server's digital certicate, client check what CA isses the certificate and uses the CA's public key to verify the signature on the certificate
- When Client satisfied with server's identity, client creates  random encryption key called session key (symmetric key used for this one communication session)
- Client uses server's public key to encrypt the session key and send that encrypted key to server.
- Server will use their own private key to decrypt the session key.
- When session is closed, session key is destroy.


Exam Tips: 
- TLS is only a protocol that uses other cryptographic algorithms
- TLS is not a cryptographic algorithm itself.
- Can't encrypt something with TLS
- Can use TLS to apply other encryption algorithm.
- Session key = Ephemeral Keys

Secure Socket Layer (SSL)
- Insecure predecessor to TLS

#

# Sensitive Data Protection

Data Classification Policies:
- Assign info into categories; classifications that determines storage, handling, access requirements
- Sensitivity of info, Criticality of info

Classification Levels:

![image](https://github.com/user-attachments/assets/4b92a2ba-b682-4ebb-9b16-2b3aab7d8729)

#

## Personally Identifiable Information (PII)

- Traceable to specific person

Protected Health Information (PHI)
- Covered by medical record; HIPAA

Payment Card Information (PCI)
- Coverd by PCI DSS; Credit card and debit card numbers

#

## Data Loss Prevention (DLP)

Provide tech that helps Org enforce info handling policies and procedure to prevent data loss and theft.
- Search system for stores of sensitive information that might be unsecured.
- Monitorw network traffic for potential attempts to remove sensitive info from Org.

Host-Based DLP
- Uses software agent installed on single system
- Search that system for presence of sensitive info; SSN, credit card numbers
- Can secure it by removing it or encrypting it.

Network-Based DLP
- Monitor outbound network traffic watching transmission contain unencrypted sensitive info
- Block those transmission
- Block transmission that violate Org's policies or might encrypt it (email)

Pattern Matching:
- Recognizes known pattern of sensitive info: SSN
- Trigger if they see terms: Top secret, business confidential.

Watermarking:
- System or admin apply electronic tags to sensitive doc
- DLP system monitors systems and networks for unencrypted content containing those tags.

DLP can also operate as cloud based managed security services
















































