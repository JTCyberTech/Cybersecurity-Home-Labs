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

Practice of identifying, classifying, priortizingm, remediating and mitigating software vuln
- Identify unrecognized source of vuln that we may not have thought of.

## Detection and Monitoring

Practice of Observing activity to identify anomalous patterns for further analysis.
- Need threat intelligence to tune our sensor better.
- Add more rules/definitions based on different incidences.
- To have more true positives. Less false positive.

# Quiz 3

1. Which of the following factors evaluates a source to ensure it matches the use case?
- Relevancy
  - Relevancy ensures that a source matches its intended use case. Timelines ensures an intelligence source is up-to-date. Accuracy ensures an intelligence source produces effective results. Confidence Level ensures an intelligence source produces qualified statements about reliability.

2. In which phase of the security intelligence cycle is input collected from intelligence producers and consumers to improve the implementation of intelligence requirements?
- Feedback
  - The final phase of the security intelligence cycle is feedback and review, which utilizes the input of both intelligence producers and intelligence consumers. The goal of this phase is to improve the implementation of the requirements, collection, analysis, and dissemination phases as the life cycle is developed.

3. Which level of intelligence is directly used by Security Operations Center (SOC) staff to make real-time decisions in response to system alerts?
- Tactical
  - Tactical intelligence refers to the immediate, actionable information necessary for frontline staff, such as SOC analysts, to make decisions about real-time security threats and alerts.
