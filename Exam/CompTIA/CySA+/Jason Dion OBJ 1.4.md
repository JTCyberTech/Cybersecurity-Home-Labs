# Security and Threat Intelligence

Security Intelligence:
- Process where data is generated and is then collected, processsed, analyzed and disseminated to provide insights into security status of info systems.

Example: 
- System Admin: log things on their system, and they review those logs.

#

Cyber Threat Intelligence:
- Investigation, collection, analysis, dissemination of info about emerging threats and threat sources to provide data about external threat landscape.
- Thinking outward; attacker groups, malware outbreaks, zero day exploits.

Have two forms:
- Narrative Reports
- Data Feeds

Narrative Reports:
- Gives analysis of certain adversary group or a certain type of malware,
- Get written report based on that.
- Created by threat analyst.

Data Feeds:
- List of known bad indicators
  - Indicator of Compromise --IoC
  - Domain names, IP addresses, hashes of exploit malware code.
- Tactical Level information
- Example: If known bad IP address, we can just block it.

#

# Intelligence Cycle

1. Requirement (Planning and Direction)
2. Collection and Processing
3. Analysis
4. Dissemination
5. Feedback

## 1. Requirement (Planning and Direction)

Sets out goals for intelligence gathering effort.
- Figure out:
  - What we want to collect?
  - What we care about?
  - What do we want to spend time, money and resources?


 ## 2. Collection and Processing

Implemented by software tools to gather data which is then processed for later analysis
 - SIEM, where we gather all data.
 - All data can be coming from different format
   - Processing = Normalize theat data
   - Convert all data into standard format for SIEM to use.

  
## 3. Analysis

Performed against the given use case afrom planning phase and may utilize automated analysis, AI and machine learning.
- Too much data coming in, people can't read it and analyze it fast enough.
- Have to use automation
- Have to separate data into three buckets.
  - Known good = Allow
  - Known bad = Block
  - Not sure = Analysis


## 4. Dissemination

Publishes information produced by analysts to consumers who need to act on insights developed.
- Can have Oral reports, Written reports, PowerPoint Presentation, Email.
- Three most common ways to break up dissemination:
  - Strategic
  - Operational
  - Tactical
 
Strategic Intelligence:
- Address broad themes and objectives
- Affects projects/business priorities over weeks, months, years.
- Done as report to Executives or PowerPoint presentation to a large group.

Operational Intelligence:
- Address day to day priorities of managers and specialists.
- Checklist of things should be worried/focus today.

Tactical Intelligence:
- Real time decisions made by staff as they encounter different alerts and system indications.
- SOC seeing alert pop up on screen

## 5. Feedback

Aims to clarify requirements and improve collection, analysis, and dissemination of info by reviewing current inputs and outputs.
- Goal: how to do things better.
- Example: Lesson Learning by figuring out what incidents occurred during intelligence gathering this cycle so can be avoid in the future.

#

# Intelligence Sources

Dive deeper into collection and processing

## Timeliness

Ensures intelligence source is up to date.
- Over time info is not as valuable.

Example:
- If I know somebody is attacking your network today and tell you 3 years later, it's not going to be useful.
- Once adversary understands they've been identified, they will change their tactic.
  - So report you wrote today might not be useful in a week because things changes.

## Relevancy

Ensures intelligence source mataches its intended use case
- Need to think what affect me and my Org, so I can defend against it.


## Accuracy

Ensures intelligence source produces effective results.
- Info needs to be valid and true.
- Elminate as many false positive as possible with automated software/machine Learning/Artifical Intelligence.

## Confidence Levels

Ensures intelligence source produces qualified statements about reliability.
- When analyst publish report, don't have 100% of the facts.
- Need to guess with different pieces, need to figure out: Are they reliable? accurate? relevant? Timely?
- Putting a grade on how good we think info is.

Source reliability:
- Letter grade from A to F

Information Content:
- Scale grade of 1 to 6 (confirm, probably true, possibly true, doubtfully true, improbable, cannot be judge)

#

Three places to get information from:
- Proprietary
- Closed-Source
- Opened Source

## Proprietary

Threat intelligence comes as commerical service offering.
- Pay for access to updates/research based on subscription fee.

## Closed-Source

Data derived from provider's own research and analysis efforts; data from their own honeynets and info mined from their customers' systems on anonymous fashion.
- 100,000 users will be data for sharing for each others.

## Open- Source

Data available without subscription, may include: threat feeds, reputation lists, malware signature databases.
- OSINT: method to get info about person/Org thru public record, websites, social media.

#

# Information Sharing and Analysis Center (ISACS)

- Critical Infrastructure
- Government
- Healthcare
- Financial
- Aviation

#

# Threat Intelligence Sharing

Dissemination: 
- Risk Management
- Security Engineering
- Incident Response
- Vulnerability Management
- Detection and Monitoring


## Risk Management

Identifies, evaluates and prioritizes threat and vuln to reduce their negative impact.
- Tell how risky a thing is based on outside threats,
- Because we already knew our own vuln by using vuln scanning.

## Security Engineering

Recongize what threat is the most popular to prevent them from attacking us.


## Incident Response

Org approach to addressing/managing aftermath of cybersecurity breach or attack. 
- Tactical Level Intelligence; need to know where the attack is coming from: IP address

## Vulnerability Management

Practice of identifying, classifying, priortizing, remediating and mitigating software vuln
- Identify unrecognized source of vuln that we may not have thought of.

## Detection and Monitoring

Practice of Observing activity to identify anomalous patterns for further analysis.
- Need threat intelligence to tune our sensor better.
- Add more rules/definitions based on different incidences.
- To have more true positives. Less false positive.

#

# Threat Classification

Known Threat:
- Can be identified using basic signature or pattern matching
  - Malware; Documented Exploits
  - Documented Exploit: software, data, or sequence of commands that takes adv of vuln to cause unintended behavior or gain unauthorized access to sensitive data.
  - Identify by vuln scanner.
- Easily detected using: signatures, hash values

Unknown Threat:
- Cannot be identified using basic signature or pattern matching
  - Zero day exploits
  - Obfuscated Malware code: execution malware author has attempted to hide thru various techniques such as compression, encryption, or encoding to avoid detection.
  - Behavior based detection: malware detection method that evalutes object based on its intended actions before it can actually execute that behavior.
    - Example: Opening an email on a sandbox to evaluated based on its behavior, see if its malicious.
    - Look at ports being opened, calls being made in software to determine if its good or bad.
  - Recycled threats: Process of combining/modifyingp parts of existing exploit code to create new threats thats hard to identify by automate scanning.
    - Put different pieces and parts of different malware code and put them together, can bypass signature based detection.  
  - Known unknowns: Classification of malware that contains obfuscation tech to circumvent signature matching and detection.
  - Unknown unknowns: Classification of malware that  contains cokmpletely new attack vectors and exploits 

#

# Threat Actors 

- Script Kiddie
- Insider threat
- Competitor
- Organized Crime
- Hacktivist
- Nation-State
- APT
- Supply Chain Threats

#

## Script Kiddle

Use other people's tools to conduct attack as they do not have skills to make their own tools
- Metasploit, aircrack-ng, John the Ripper
- For: profit, gain credibility, fun
- Low Orbit Ion Cannon to DDoS

#

## Insider Threats

People who have authorized access to Org's network, policies, procedures and business practices.

Example:
- Unskilled insider; copy Org's file onto thumb drive, not authorized to access those file, can post online and cause a data breach.
- Skilled insider; elevate their own user account permission to access data from across network as admin.

Prevention:
- Data Loss Prevention
- Internal Defenses
- SIEM search

Types of Insider Threats:
- Intentional
- Unintentional

Strategies to prevent:
- Employee Education and Training
- Access Control
- Incident Response Plans
- Regular Monitoring

### Intentional Insider Threat

Deliberately seeks to cause harm
- Stealing sensitive information
- Disrupting Operations
- Launch cyber attack on Org

### Unintentional Insider Threat

Causes harm because of carelessness
- Lack of knowledge
- Human Error
- Falling for Phishing emails
- Using weak passwords
- Accidentally sharing sensitive information with outside Org.

#

## Competitor

Rogue business attempint to conduct cyber espionage against Org.

- Focus on stealing proprietary data, disrupting business, damaging reputation.
- Seek to use employee as insider threat in your Org to steal data
- Break into your network over internet

#

## Organized Crime

Focus on hacking and computer fraud to achieve financial gains

- Use social engineering, ransomware to steal money.
- Well funded, use advanced attacks/tools.

#

## Hacktivist

Politically motivated hacker, target gov't or individuals to advance their poliical believes.

- Environmentalist, hack into a logging company because want to see company's stock price fall to drive their business out to save the forest.
- Can be individual or large group; Anonymous
- Highly structured, high level of advanced attacks
- Not well funded because most doing based of their believes.

#

## Nation-State

Group of attackers with exceptional capability  funding  Org  with intent to hack network or system.

- One of most skilled type of threat actors.
- Group with skilled people, well Funded
- Do not attack randomly. Determine specific target to achieve their political motives.
- Almost all Nation State = APT (Advanced Persistent Threat) but,
  - Not all APT is Nation State.
  - Inside a system/network 6 to 9 months before network defenders discover them.


Nation state actor refers to Gov't or Gov't affiliated group that conducts cyber attacks.
- Used for: espionage (spyinhg), sabotage, intelligence gathering.

#

## Supply Chain Attack

Normally conducted by Nation state actor.
- Hacker hacks into a third party software company that Org uses. Creates a backdoor into the software, which compromise all Org that uses the third party software.
- Attack is directed at the third party company's customers instead of the third party company.

#

## Advanced Persistence Threat  (APT)

An attacker establishes long term presence on a network in order to gather sensitive information.
- Nation-States, Criminal Organizations, Individual hackers
- Well-funded, organized, high persistence, determination in achieving their goals.
- Living off the land: Using tools that already existed in the targeted network to blend in.

Goal: Harvest sensitive data, intellectual property and other sensitive info.


Difference:
- Nationa-State: Affiliated with Gov't
- APT: Type of cyber attack that establish long term presencewwwwon given network.

Almost all Nation-State are APTs but NOT all APT are Nation-State Actors.

#

# Threat Research 

- Reputational Threat Research
- Indicator of Compromise (IoC)
- Behavioral Threat Research


Reputation Data
- Blacklists of known threat sources; malware signature, IP address ranges, DNS domains
  - Known things that are bad. See in Talos intelligence.
 

Behavioral Threat Research
- Term refers to correlation of IoCs into attack patterns.


## Indicator of Compromise (IoC)

A residual sign that an asset or network has been successfully attacked or is currently under attack.
- Can be: hash value, IP address, file being left on system.
  - Anything that gives clue that something has happened on the system.
- IoC = evidence that attack was successful
- IoA = Indicator of Attack
  - Term used for evidence of an ongoing intrusion attempt.
 
Indicator of Compromise Lookout:
- Unauthorized software and files
- Suspicious Emails
- Suspicious registry and file system changes
- Unknown port and protocol usuage
- Excessive bandwidth usage
- Rogue hardware
- Service Disruption and defacement
- Suspicious or unauthorized account usage

#

## Tactics, Technique and Procedure (TTP)

Behavior patterns used in historical cyberattacks and adversary actions
- Knowing this, will understand how adversary thinks and get one step ahead of them on defending.

#

Port Hopping:

APT's C2 application uses any ports to communicate and jumps between different ports.
- Using port 22, but detected then will jump to port 53 to evade detection.


Fast Flux DNS:

Rapidly changes IP address associated with a domain
- One domain name but multiple IP addresses
- Even if blacklisting IP addresses, hackers can change backend IP address and still route their communication to C2 server.
- Detect: look at communication pattern emerge as changes keep happening with proxy logs.

Data Exfiltration:

Unauthorized transfer of data from computer or other device.
- File types or compression or encryption being used on data.

#

# Threat Hunting

Cybersecurity technique designed to detect presence of threat that have not been discovered by normal security monitoring.

- Less disruptive than PenTest.
- Relies on tools developed for regular security monitoring and incident response.
- Need to assume existing rules have failed when threat hunting. (Looking for things that is not detected by SIEM)

Establishing a Hypothesis
- Hypothesis: derived from threat modeling and based on potential events with higher likelihood and higher impact.
- Think: who might want to harm us? break into our network? How they can do that?

Profiling Threat Actors and Activities
- Involves creation of scenarios that show how a prospective attacker might attempt an intrusion and what their obj might be.'

Helps:
- Improve detection capabilities
- Integrate Intelligence
- Reduce Attack Surface
- Block Attack Vectors
- Identify Critical Assets

#

## Analyze Network Traffic

Determine if there is any outgoing traffic to some sort of suspicious domain or C2 server based on our threat research/reputational databases.
- Gives a list of diffewrent hosts to investigate.

## Analyze Executable Process list

See what programs/services are running and which ones were opening the network connection.
- See if it's something that's suspicious that needs to be investigate further.

## Analyze other Infected hosts

See similarities between other infected hosts.
- Are they running sawme malicious process, using diffewrent things to avoid detection?

## Identify how the malicious process was executed

What allowed it to start up? Is there a way we can block the attack vector in future?
- Can use whitelisting system, blacklist that vuln application until patch

#

# Open Source Intelligent (OSINT)

The use of publicly available information, plus tools used to aggregate and search for it.
- Publicly information
- Social Media
- Dating Sites
- HTML Code
- Metadata
