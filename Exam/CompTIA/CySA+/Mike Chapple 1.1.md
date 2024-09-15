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

