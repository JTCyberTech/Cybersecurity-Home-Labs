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























Note:
- SIEMs: have a live dashboard that that turns information into charts as they aggregate and correlate data and alert on anomalies.
- SOAR: best assists with the automation of security workflows by automating routine work.
