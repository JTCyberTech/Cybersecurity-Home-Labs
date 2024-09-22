# Compare and contrast threat-intelligence and threat-hunting concepts

# Threat Actors 

Understanding attacker skills and motivations is crucial to building effective defenses.

## Script Kiddies: 
- Novice attackers who reuse tools created by others.

## Sophisticated Attackers:
- Sponsored by gov't

## Organized Crime:
- Have tremendous technical and financial resources.

## Hacktivists:
- Use hacking to advance their own ideals.

## Insider threat:
- Intentional or unintentional

#

# Zero days and APT

Patches protect against many cybersecurity vuln

Ethical Disclosure:
- Notify vendor of vuln
- Provide vendor reasonable amount of time to create patch.
- Disclose vuln publicly.

What if vuln is kept secret?
- Zero-Day vuln: vuln in product that has been discovered by at least one researcher but has not yet been patched by vendor.

Window of vuln:
- Time between discovery of zero day vuln and release of security update.

Exploiting zero day is difficult:
- Need to know about the vuln + have the tools and skills required to exploit it.

## Advanced Persistent Threats (APTs)

- Well-funded and highly skilled
- Typically gov't sponsored
- Have access to zero days and other sophisticated weapons.
- Work methodically to gain access to a target.

Defending against APTs is difficult:
- Build a strong security foundation
- Implement strong encryption
- Use rigorous monitoring.

#

# Supply Chain Vulnerability

Vendors may fail to provide adequate support for existing products. 
- Vendors may not disclose the use of embedded systems.
- Mitigate riska assoicated with data storage and other vendor dependencies.

Security issues may araise in supply chain
- Running products that lack vendor support introduces significant security risk.

End-of-sale:
- Product will no longer be offered for purchase, but the vendor  will support existing customers

End-of-support:
- Vendor will reduce or eliminate support for existing users of product.

End-of-life:
- Vendor will no longer provide any support or updates for the product.

#

# Threat Classification

Threat Analysis:
- Develop a list of threats
- Assess threats based on likelihood
- Assess threats based on impact
- Create a threat register

Johari Window:

![image](https://github.com/user-attachments/assets/763b4e67-32bd-453c-a8d7-7271bd7e8012)

#

# Threat Intelligence

Threat intelligence allows team to stay up to date on current risks.

Threat intelligence:
- Set of activities that an organization undertakes to educate itself about changes in cybersecurity threat landscape and adapt security controls based on that information.


## Open-Source Intelligence

Uses public information
- Security websites
- Vuln databases
- New media
- Social media
- Dark web
- Information-sharing Centers
- File and Code repositories
- Security Researchers

Email Address Harvesting:
- Search for valid addresses

Three criteria to evaluate threat intelligence source:
- Timeliness
- Accuracy
- Relevance 

#

## Timeliness

- How soon after a new threat arises, or evolves will threat intelligence source reflect this new information?
- How promptly is threat intelligence delivered?

## Accuracy

- Is the data correct?

## Relevance

- Is the information important?

#

# Managing Threat Indicators

Threat Indicators:
- Properties that describe a threat
- Might include IP address, malicious file signatures, communications patterns, other identifiers analysts can use to identify threat actors.

Threat info is only useful if we can share it among collabrators
- Cyber Observable eXpression (CybOX): provides standard schema for categorizing security observations.
  - helps us understand what properties we can use to describe intrusion attempts, malicious software, other observable security events
- Structured Threat Information eXpression (STIX): Standard language used to communicate security information between systems and organization
  - STIX takes the properties of CybIX framework and give a language that we can use to describe those properties in structured manner.
- Trusted Automated eXchange of Indicator Information (TAXII): set of services that actually share security information between systems and Org.
  - Provides technical framework for exchanging messages that are written in STIX language.

OpenIOC:
- Mandiant threat framework

#

# Threat Intelligent Sharing

TAXII, STIX, CybIX facilitate information sharing

ISACs:
- Information Sharing and Analysis Centers
- Bring together cybersecurity teams from competing Orgs to help share industry security info in confidential manner.
- Goal: Gather and disseminate threat intelligence without jeopardizing anonymity

## Incident Response

- Incident response team who are tasked with actively responding to security incidents

## Vulnerability Management 

- Team that must identify potential weaknesses that could lead to future incidents

## Risk Management

- Team who must understand the big picture of cybersecurity risk

## Security Engineering 

- Team who must design controls to combat emerging threats.

## Detection and Monitoring

- Team, SOC, who are responsible for actively monitoring the security enviornment for threat indicators.

#

# Threat Researchas

Threat research uses threat intelligence to get inside the minds of our adversaries
- Reputational Research: Identifies potentially malicious actors based on their use of IP add, email add, domains that were previously used in attacks. (Can use this to block future attack attempts)
- Behavioral Research: Identifies potentially malicious actors based on the  similarity of their behaviors to past attackers.

Research Sources:
- Social media
- Blogs/forums
- Government Bulletins
- Computer Emergency Response Team (CERT)
- Computer Security Incident Response Team (CSIRT)
- Deep/Dark web
- Paid feeds (closed Sources)
- Information sharing Org
- Internal Sources
- Adversary Tactics, Techniques, and Procedures (TTP)

#

# Identifying Threats

Threat modeling identifies and prioritizes threats
- Use a structed approach to threat management

Three ways that Org can use structured approach to threat identification:
- Asset Focus: Use asset inventory as basis for analysis.
  - Org's web presence, might identify the severing of a single fiber optic cawble as threat to continued availibilty of website.
 
- Threat Focus: Identify how specific threat may affect each info system.
  - They might list the threat of a hacker, then think thru all ways that a hacker  might try to gain access to their network
  - Threat to an Org may include wide spectrum of groups, ranging from known adversaries to contractors, trusted partners, rogue employees.
- Service Focus: Identify the impact of various threats on specific service.
  - Org that exposes an API to the public might think thru all interfaces offered by that API and threats that could affect each interface.
 
#

# Automating Threat Intelligent

Automate Blacklisting IP addresses from threat feeds.
- Automated blocking may cause service disruptions.
- Combine different threat feeds for more robust filtering.
- Incident response is a very manual process.

Data Enrichment:
- Automatically supplements incident data.

Sample Data Enrichment Tasks:
- Perform source address reconnaissance on source address of attack, including IP address ownership, geolocation information
- Retrieve related log records: based on SIEM query.
- Trigger vuln scan: assist determining whether attack had a high likelihood of success

## Security Orchestration, Automation, and Response (SOAR)

- Platforms enhance SIEM capabilities to facilities these automated responses.

Machine Learning allows automated creation of malware signatures.

#

# Threat Hunting

Cybersecurity professionals once saw their roles as building impenetrable defenses.
- In today's threat landscape, we make the assumption of compromise.

Threat Hunting:
- Organized systematic approach to seeking out indicators of Compromise on our networks using expertise and analytic techniques.
- Threat hunters need to think like their adversaries
- Begin by establishing a hypothesis.

## Indicator of Compromise

Might be associated with hypothesis
- Indicator could be anything unusual
- Unusal binary files
- Unexpected processes or resource consumption
- Unexpected accounts or permissions
- Deviations in network traffic
- Unexplained log entries
- Unapproved Config changes

## Focus Areas

- Configuration/Misconfigurations on devices looking for unauthorized changes
- Isolated networks: Containing sensitive systems.
- Business critical assets and processes.

#

# Deception Technologies

Deception technologies fool intruders
- It can be difficult to distinguish attacks from legitimate activity.

Darknets:
- Designed to assist with making distinction
- Unused but monitored IP address space

HoneyFiles:
- False stores of sensitive information

Honeypots:
- System designed to attract and trap attackers.

Honeynets:
- Large scale deployments of honewypots.

DNS Sinkhole
- Altered DNS records to reroute botnet traffic.'
- Are self-inflicted DNS poisoning attacks. 

#

Note:
- SIEMs: have a live dashboard that that turns information into charts as they aggregate and correlate data and alert on anomalies.
- SOAR: best assists with the automation of security workflows by automating routine work.
- Asset-focused approach to threat identification, an organization goes through their assets one-by-one and considers possible threats to each.
- Adversary TTP includes its tactics, techniques, and procedures.
- IP reputation services are not open source intelligence.
- DNS sinkhole, an admin can forward malicious DNS requests to another IP address to keep from harm.
- The basic principle underlying threat-hunting activities is an assumption of compromise, meaning that attackers may have already gained access to our network.
- Information Sharing and Analysis Centers (ISACs) facilitate cybersecurity information sharing among industry-specific communities.
- STIX is an XML language for cyber threat information.
