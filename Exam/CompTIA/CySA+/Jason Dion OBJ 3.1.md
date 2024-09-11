# Malwares

## Command and Control (C2)

- C2 node: Any infrastructure of hosts and services with which attackers direct distribute or control malware over botnets.
- Different zombie machines that connects back to bot master that controls the C2 network, then they can issue a comnmand to use those machines.
- Single point of contact that can use to talk to every machines in network.
- APT use C2 a lot.

#

# Attack Frameworks

- Lockheed Martin Kill Chain
- MITRE ATT&CK Framework
- Diamond Model of Intrusion Analysis

#

## Cyber Kill Chain

Describe stages by which threat actor progresses a network intrusion. Linear Process

7 steps methods
- Reconnaissance
- Weponization
- Delivery
- Exploitation
- Installation
- Command and Control (C2)
- Action and Objectives

Remember own phrase: **Reverse With Data Expolitation In Complete Access**

Kill Chain analysis can be used to identify defensive courses of action to counter progress of an attack at each stage.
- Ways somebody can break into my system
- Run malicious code
- Gain persistence
- Do C2 on server.

Can try to:
- Detect
- Deny
- Disrupt
- Degrade
- Deceive
- Destroy

#

### Reconnaissance

Attacker determines what methods to use to complete the phases of attack.
- Sneaky; Use open source and passive info gathering
- Goal: Get info on type of software, vuln etc.

Remember: **Reverse**

#

### Weaponization

Attacker couples payload code to enable access with expolit code, use vulnerability to execute on target system.
- Basically coding or creating malware or exploit you want to run, but not running yet.
- Creating the malware on your own lab.

Remember: **With**

#

### Delivery

Attacker identifies a vector to transmit the weaponized code to the target environment.
- By: Email, dropping USB drive with loaded malware.

Remember: **Data**

#

### Exploitation

Weaponized code is executed on target system.
- The code has been run on target system.

Remember: **Exploitation**

#

### Installation

Enables weaponized code to run remote access tool and achieve persistence on target system.
- Want the malware to run remote access so we can remote in the system.
- Want to stay persistence so we can come back anytime.

Remember: **In**

#

### Command and Control (C2)

Weaponzied code establishes an outbound channel to remote server that can then be used to control remote access tool and possibly download additional tools to progress the attack.
- Have access to the system and can remote into system.

Remember: **Complete**

#

### Action on Objectives

Attacker typically uses access he has achieved to collect info from target systems and transfer it to remote system (data exfiltration) or achieve other goals and motives.

Remember: **Access**

#

## MITRE ATT&CK Framework

Knowledge base that lists and explation specific adversary tactics, techniques, common knowledge or procedures. Matrix Model

- Heavily focused on exploitation phase.
- For reconnaissance phase > Pre-ATT&CK tactic matrix


#

## Diamond Model of Intrusion Analysis

Framework for analyzing cybersecurity Incidents and Intrusions by exploring the relationship between four core features:
- Adversary
- Capability
- Infrastructure
- Victim

Remember: All Control In Vulnerabilities

#

# Indicator Management

- STIX
- TAXII
- OpenIOC
- MISP

Structured Threat Information eXpression (STIX):
- Standard terminology for IoCs and ways of indicating relationships between them that is included as part of OASIS Cyber Threat Intelligence (CTI) Framework
- Sharing info between systems and expressed in JavaScript object notation or JSON format.
- **JSON format = STIX**

- Observed Data
- Indicators
- Attack Pattern
- Campagin and Threat Actors
- Course of Action (COA)

Trusted Automated eXchange of Indicator Information (TAXII):
- Protocol for supplying codified information to automate incident detection an analysis.
- Transmit data back and forth between servers and clients over secure connection like HTTPS using REST API.

OpenIOC:
- Framework by Mandiant that uses XML formatted files for supplying codified information and automate incident detection and analysis.
- Open Source tool: different info for each entry.
  - metadata: author, category info, confidence level, usage license.
 
Malware Information Sharing Project (MISP):
- Provides server platform for cyber threa intelligence sharing, proprietary format, supports OpenIOC definitions and can import/export STIX over TAXII
- Open Source.
