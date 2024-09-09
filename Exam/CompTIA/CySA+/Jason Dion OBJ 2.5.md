# Cybersecurity Roles and Responsibilities

Cybersecurity Analyst Role:
- Senior position within Org security team with direct responsibility for protecting sensitive info/preventing unauthorized access to electronic data and systems protect it.

- Responsible: hardening/protecting network, servers, laptop, desktops, smartphones.

What are functions of Cybersecurity Analyst?:
- Implementing / Config security controls
  - Firewall  IDS  Threat management appliances/softwares
 
- Working in a Security Operation Center SOC or Computer Security Incident Response Team CSIRT.
- Auditing security processes and procedures
  - Performs due diligent on third parties Org working with
  - Provides training
  - Doing assessment on your own systems.
 
- Conducting risk assessments, vulnerability assessment, PenTest
- Maintaining up to date threat Intelligence awareness of all threat in the marketplace.

Cybersecurity should have Two Key features:
- Creative thinkers
- Problem Solvers

#

# Security Operation Center

SOC
- Location where security professional monitor/protect critical info assets in Org.
- Try to find the Indicator of Compromise --IoC

- Exist in larger Org, Gov't agencies, Healthcare Orgs.
  - A lot of cost to establish, maintain, run SOCs
 
- Small Org: out source, third party SOC team


Successful SOC:

1. Have authority to operate by getting thru Org's policies and procedure that gives authority to do their job and tell other parts of Org what needs to happen.
    - If doing instant respond, need to shut off server to stop infection; SOC empower to make those decision. '
  
2. Have motivated/ Skilled Professionals within SOC
    - Need to know what they are looking at, critcal think.
    - Need people to determine what is good/bad inside lots of collected data.

3. Incorpate Processes into Single Center
    - Mostly for Security processes and IT.
    - Make sure SOC doesn't become service desk, different job
    - SOC handles: Access management, identity management, Instant resoponse

4. Equipped into Perform Incident Response
    - Take in charge when bad things happens to get it resolve, getting network back to secure/ good known baseline.
  
5. Protect Itself/ Organization at large
    - SOC itself can become under attack; leading to not able to see Org's network.
    - Need to protect their own system too.
  
6. Can separate Signal from Noise
    - Need to know how to separate out what is known good/bad/not sure of.
    - Spent most time on "not sure of"
    - Bad = block, Good = allow; Not sure of = ?
  
7. Collaborate with Other SOCs for Data Sharing
    - Something bad happens at other company can happen to you as well
  

SOC should be single point of contact for:
- Security
- Monitoring
- Instant Response

Should have: 
- Good skilled Professionals to protect your Org.

#

# Security Control Categories

Security Controls:
- Migitates Vuln/risk to ensure CIA, nonrepudiation and Authentication of data. --CIA NA
- Good security control measured by how long we can use that control to delay an attack.

Use Risk Management Framework:
- Security controls should be selected/developed in structured manner using risk management framework.

Control Types:
- Technical
- Operational
- Managerial

## Technical (Logical) Controls

- Category of Security Control; implement as system (hardware  software  firmware)

Example:
- Take Firewall, install it in your network. -> Technical control.
- Take Antivirus, install it on your machine -> Technical Control.
- Patch OS -> Technical Control.

## Operational Controls

- Category of Security Control; implement primarily by people rather than systems.
- Try to solve using people.

Example: 
- Add more security guards
- Train employee to not fall for phishing scama from emails.

## Managerial Controls

- Catergory of Security Control; provides oversight of information system.

Example: 
- Risk identification
- Using different tools: vulnerability scan or remediations.

#

Operational Control + Managerial Control = Administrative Control
- Governed by Managerial Processes

Exmaple: 
- Vulnerability managerment program inside of your Org.
- Program such as Org framework of policies and procedures and all things it takes to do vulnerability management within given Org.

#

Functional Controls

- Preventative
- Detective
- Corrective

## Preventative Controls

- Control that acts to elminate/reduce likelihood that an attack can succeed.

Example: 
- Put Access Control List on Firewall; prevent attacker from accessing my network.
- Dealing with: ACLs, Firewalls, Antivirus, anti-malware solutions, IDS, IPS -> Perventative Categories.

## Detective Control

- Control that may not prevenmt or deter access, but will identify and record any attempted or successful intrusions.

Example:
- Logs; anytime log something that's happening, using detective control because can go back and review the logs.
- Security Camera; doesn't stop from breaking in, but can record you doing it.

## Corrective Control

- Control that acts to eliminate/reduce impact of an intrusion event.

Example: 
- Backup system that backups all files to offsite; even data stolen, data can be restored.
- Patch management system; once vuln is known out there and it's being exploited, can patch it.

#

Additional Controls:
- Physical
- Deterrent
- Compensating
- Responsive

## Physical Controls

- Type of security control that act against in-person intrusion attempts.
- Physical control can be: Detective control, preventative control or corrective control.

Example:
- Alarm, gateways, locks, bollards, lighting, security system, security guards.
- Preventative/Physical: lock on the front of house; acts both controls because it's protecting whats inside my house
- Detective/Physical: Security camera; monitoring your physical area. 


## Deterrent Control

- Type of security control that discourages intrusion attempts.

Example: 
- Sign saying "House protected by security".


## Compensating Control

- Type of security control that acts as a substitute for principal control.
- Best level of protection that you can afford because maybe you can't afford that best level of protection.

Example:
- Increasing security of your authentication systems and you want to make sure your password security is good.
- Can have different ways: Instead of just using very long and complex password, you can use MFA as a compensating control.

## Responsive Control

- System that actively monitors for potential vuln or attacks, and then takes actions to mitigate them beforfe they can cause damage.
- Can quickly identify and respond to different threats, reducing risk of successful attack.
- Can be a mixture of Technical, managerial, operational controls

Example:
- Network Firewall, IDS or IPS 

#

# Selecting Security Controls

- To select the best security control: Use the CIA
  - Encryption Hard drive = Confidentiality
  - Use Digital Signature on your email = Integerity
  - Using cloud product that is scalable = Availablity

- Confidentiality can be place:
  - Adding Access control system, can control which users can access backup.
  - Adding encryption, even if lost or stolen, no one can read them.
