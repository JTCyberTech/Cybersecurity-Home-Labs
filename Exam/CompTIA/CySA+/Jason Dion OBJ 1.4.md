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

## Timeliness

Ensure an intelligence source is up to date
