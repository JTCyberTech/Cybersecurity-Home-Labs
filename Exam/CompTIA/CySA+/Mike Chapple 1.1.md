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
















