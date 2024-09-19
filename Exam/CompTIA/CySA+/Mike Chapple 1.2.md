# Given a scenario, analyze indicators of potentially malicious activity

# Network-Related (Network Symptoms)

Endpoint Symptoms:
- Some signs of endpoint compromises are obvious.
- Monitor network for symptoms of security incidents




## Bandwidth consumption 

Valuable data source for network traffic analyze.
- Netflow records tells which systems communicated with each other and how much info they exchanged.
- Bandwidth data can't diagnose whats happening, but can be helpful in:
  - Identifying potential incident
  - Identifying systems involved in incident

Bandwidth records can help rule out data exfiltration.
- If file is 1 GB, data exfiltration is less than 1 GB, then hacker didn't steal that file but steal something else.

#

## Irregular Peer to Peer Communication

- indicate a compromised systesm attacking another system. (Lateral Traffic)

#

## Beconing

- May incident malware command and control traffic. Sending messages back to the Command and control server.
- Can use IDS to watch for beconing traffic that's recognizable from the contents of traffic or known bad IP addresses.

#

## Scans/Sweeps

- May indicate a compromised system searching for other targets.

#

## Rogue Devices on Network

Monitor your network for presence of rogue devices.
- If you use network access control solution, should be fairly easy to detect unapproved devices.'

Rogue Access Points:
- Occurs when someone connect unauthorized wireless access point to enterprise network.

Risk of Rogue Access Point:
- Bypass Authentication, Rogue AP config to avoid encryption can bypass WP3.
- Interference: Limited number of wifi channels avaialble

Rogue Access Point Detection:
- Enterprise-grade wireless has built-in intrusion detection capabilities.
- Unknown radios on the network can be identified.
- Handheld tools can also help pinpoint them and d/c them.

Evil Twins Attack:
- Hacker set up a fake AP with the SSID of legit network
- Lure users to automatically connect when they are in the area.
- Hacker controls the network, they can use DNS poisoning to redirect user to phishing websites.

Karma Toolkit:
- Search for legit network in area
- Create an evil twin network, build fake websites to capture credential from user of the evil twin network.

#

# Host-Related

## Processor Consumption

CPU utilization:
- Can point to application with abnormal processor consumption.
- Hackers made use your PC for crypto mining, making your CPU consumption would be a good giveaway.

#

## Memory Comsumption

Provides valuable insight into system activity.
- Slow memory leak that grabs and more memory over time without ever releasing any > Cause DoS

#

## Abnormal OS process Behavior

Unusual processor and memory consumption may point to Abnormal OS process Behavior
- Common indicator of Compromise.

#

## Drive Capacity Comsumption 

If drive suddenly begin to fill up in unexpected way.
- Attacker might be using storage to stash illegal contect or host file sharing service.

#

## Unauthorized Software

Application control and configuration management tools
- Can help  identify and block unwanted software.

#

## Malicious Processes

Running on system after receiving antivirus alerts.

#

## Unauthorizad Changes

System integrity monitoring tools
- Tripwire: can help you in finding unauthorized and anomalous changes to your file system and registries as they occur.

#

## Unauthorized Privileges

User account review might detect accounts and suddenly have new unauthorized privileges 
- Sign of privilege escalation attack.

#

## Unauthorized ScheduleD Tasks

- Watch for the presence of unauthorized scheduled tasks on system.
- Attacker can use job scheduling mechanisms to maintain a persistent presence on system to evade detection.

#

# Application-Related

Applications may show signs of malicious activity.
- Watch for unauthorized application accounts and privileges.

#

## Anomalous Activity

### Unexpect Outputs

Can be SQLi or memory overflow.
  - If application normally retrieves one record from database at a time, that establishes baseline of activity.
  - If that application suddenly retrieves entire database table > IoC 

### Unexpect Outbound communications
  - If application is meant for internal use only, suddenly communicating to system located around the world.

#

## Service Interruption

Service disruptions may be the result of compromise
- Can be result from DoS
- Misstep from intrusion, accidentally took down a service, drawing unwantewd attention.

#

## Application Logs

Augment Security Information from networks, endpoints and other sources.

#

# Other

## Obfuscated Links

Link that won't appear on the content filters block list, but redirect to malicious site.
- Content filters often block emails and webpages containing links to known malicious sites.  
- Attacker try to bypass content filters by using obfuscated links

URL Redirection
- Replacing URLs with shorter links
- Modern content filter detect URL redirection.

#

## Social Engineering

- Authority
- Intimidation
- Consensus: herd mentality
- Scarcity
- Urgency
- Familiarity

































 
