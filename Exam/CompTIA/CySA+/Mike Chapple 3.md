# Incident Response Program

## Building an Incident Response Program

- Importance of Incident Response Plan
   - **Cybersecurity incidents** are inevitable despite preventive measures.
   - A **structured incident response plan** is crucial for effective crisis management.

- NIST Standard
   - The incident response process follows the **NIST Computer Security Incident Handling Guide (NIST SP 800-61)**.
   - This guide is a widely used standard in the cybersecurity field.

- Elements of an Incident Response Plan
   - **Statement of Purpose:**
      - Reasons for creating the plan.
      - Scope of the plan (e.g., cybersecurity incidents, sensitive information loss).

   - **Strategies and Goals:**
      - Prioritization of containment over evidence preservation if necessary.

   - **Responsibility and Authority:**
      - Clear roles and responsibilities for incident handling.

   - **Communication:**
      - **Internal team communication.**
      - Communication with other organizational groups and third parties.

   - **Senior Management Approval:**
      - Ensures authority for taking necessary actions during incidents.

- Preparation and Documentation
   - **Prior planning and documentation** are essential for effective incident response.
   - Avoiding a "seat-of-the-pants" approach to incident handling.

- Consulting NIST SP 800-61
   - Use **NIST SP 800-61** as a guide for developing the plan.
   - Review incident response plans from other organizations for reference.

#

## Creating an Incident Response Teawm

- Importance of the Incident Response Team
   - **Essential** for handling security incidents.
   - Should be **available 24/7** with primary and backup personnel.

- Team Composition
   - Include **management**, **cybersecurity personnel**, **technical subject matter experts** (e.g., DBAs, developers, system engineers, virtualization experts).
   - **Legal counsel**, **public affairs**, **marketing staff**, **human resources**, and **physical security team members**.

- Team Activation
   - Not all members need to be activated for every incident.
   - Representatives should be **trained and ready** to participate before an incident occurs.

- Regular Training and Testing
   - Provide the team with **Incident Response plan documentation**.
   - Conduct **regular training and testing** to ensure readiness and effective teamwork.

- External Incident Response Providers
   - Consider retaining **external providers** for capabilities your team lacks (e.g., forensic investigations).
   - **Plan and negotiate contracts** in advance, not during an incident.

- Preparation and Planning
   - **Design and train** your team in advance.
   - Ensure the team is **ready to respond** effectively to cybersecurity incidents.

#

## Incident Communications Plan

- Importance of Communication Plan
   - A critical component of the incident response plan, covering both **internal** and **external communications**.

- Internal Communications
   - Ensures appropriate people within the organization are informed at the right time with the right information.

- External Communications
   - **Limit communication** of sensitive information to trusted parties.
   - Involve the **public relations team** for communications with customers, media, or the general public.
   - Avoid **unauthorized leaks** to prevent media exposure and alerting attackers.

- Legal Obligations
   - Generally, no legal obligation to report incidents to law enforcement unless there's a **safety threat** or **specific legal requirement**.
   - Reporting to law enforcement can make details public and requires higher standards of evidence gathering.
   - **Legal team** should guide on laws and regulations requiring notification.

- Privacy Laws:
   - Most states require timely notification of individuals if personal information is compromised.

- Communication Plan Details
   - Specify **who to communicate with** during an incident.
   - Describe **how to communicate**, ensuring secure communication paths are in place.
   - Use **confidential mechanisms** to share information with trusted employees and third parties.

#

## Incident Identification

- Perpetual Monitoring
   - Incident response involves **continuous monitoring** for signs of security incidents.

- Key Data Sources
   - **Intrusion detection/prevention systems**, **firewalls**, **authentication systems**, **system/file integrity monitoring**, **vulnerability scanners**, **system event logs**, **NetFlow records**, and **anti-malware packages**.

- Role of SIEM Systems
   - **SIEM (Security Information and Event Management)** systems centralize log data and assist in analysis, detecting incidents based on rules and algorithms.

- External Incident Reports
   - Sometimes incidents are identified by **external sources** like customers or employees noticing unusual activity.

- First Responder Responsibilities
   - The first person to identify an incident should act **quickly to contain damage**, often by isolating compromised systems.

- Containment Techniques
   - **Quarantine systems** by removing them from the network while keeping them running to preserve evidence.

- Integration with Threat Intelligence
   - Strong **threat intelligence programs** help in rapid and effective incident identification.

- Counterintelligence
   - Programs designed to thwart adversaries' intelligence-gathering efforts by **denying access** or **feeding misinformation**.

#

## Escalation and Notification

- First Responder Mode
   - Security professionals should immediately **isolate affected systems** and contain damage when a potential incident is detected.

- Escalation and Notification Process
   - **Evaluate Severity:** Assess the incident's potential impact on the organization.
   - **Escalate Incident:** Move the incident to an appropriate level of incident response.
   - **Notify Stakeholders:** Inform management and other stakeholders about the incident and the path to resolution.

- Triaging Process
   - Identify the potential impact of the incident using the organization's incident response procedures.
     - **Low Impact Incidents:** Minimal or no potential to affect confidentiality, integrity, or availability. Typically resolved by first responders without additional resources.
     - **Moderate Impact Incidents:** Likely to significantly impact security posture. Triggers partial or full activation of the incident response team and prompt notification of management.
     - **High Impact Incidents:** May cause critical damage. Justifies an immediate, full response with senior executives notified and the entire incident response team mobilized.

- Notification and Escalation Process
   - Must be **clearly thought out** with appropriate tools in place.
     - **Access to Contact Information:** First responders should have access to the cell phone numbers of anyone who may need to be notified.
     - **Technology Solutions:** Organizations may use technology solutions to **automate team responses**.

#

## Mitigation

- Transition from Isolation to Mitigation
   - The incident response team moves from **initial isolation and quarantine** to full incident mitigation.

- Goals of Mitigation
   - **Control the damage and loss** by performing a range of containment activities.

- Criteria for Containment Strategy
   - **Potential for damage** and theft of resources.
   - Need for **evidence preservation**.
   - Impact on **service availability**.
   - **Time and resources** required for implementation.
   - **Expected effectiveness** of the strategy.
   - Duration the solution will **remain in place**.

- Balancing Needs
   - Select a containment strategy that **balances business needs** with security objectives.

- Attacker Awareness
   - Be aware that **attackers may detect containment actions** and react by speeding up activities or destroying evidence.

- Semi-Stable State
   - At the end of containment, the organization should be in a **semi-stable state**, ready to move to recovery and reconstitution.

#

## Containment Techniques

- Transition to Active Response Phase
  - Move from detection and analysis to containment, eradication, and recovery.
  - Shift from passive to active response actions.

- Containment Priorities
  - Limit future activity of the attacker.
  - Protect confidentiality, integrity, and availability of systems.

- Primary Containment Activities
  - **Segmentation:**
    - Divide networks into logical segments.
    - Create a quarantine VLAN for compromised systems.
    - Set up access controls to prevent communication with other systems.
  - **Isolation:**
    - Move compromised systems to a network disconnected from the main network.
    - Systems may still communicate with each other and the internet.
  - **Removal:**
    - Completely disconnect impacted systems from any network.
    - Prevents communication with other systems and the internet.
    - Alerts attacker to detection but stops further damage.

- Decision Making
  - Use professional judgment to choose the appropriate containment strategy.
  - Balance investigation needs, damage prevention, and business activity disruption.

#

## Incident Eradication and Recovery

- Goals of Eradication and Recovery:
  - **Eradication:** Remove all traces of the incident from systems and networks.
  - **Recovery:** Restore normal business operations.

- Eradication Steps:
  - Secure compromised user accounts.
  - Secure configurations of compromised systems or network devices.
  - Rebuild or re-image compromised systems to ensure no hidden back doors remain.
  - Apply missing security patches before bringing systems back online.
  - Deploy application whitelisting or blacklisting and quarantine technology.

- Recovery Steps:
  - Restore systems from backups, ensuring vulnerabilities are addressed.
  - Strengthen access control measures.
  - Make configuration changes to cybersecurity tools (e.g., firewall rules, mobile device management, data loss prevention, URL filtering).
  - Update or revoke compromised digital certificates.

- Media Sanitization Techniques (based on NIST guidelines):
  - **Clearing:** Overwrite sensitive data with new data.
  - **Purging:** Use advanced techniques like cryptographic functions or degaussing.
  - **Destroying:** Shred, pulverize, melt, incinerate, or otherwise completely destroy the media.

- Best Practices:
  - Understand how the system was compromised and address those vulnerabilities.
  - Use compensating controls if vulnerabilities cannot be fully remediated.
  - Follow NIST guidelines for secure media sanitization.

#

## Validation

- Validation Importance:
  - Final activity during containment, eradication, and recovery phase.
  - Ensures the incident is fully resolved before moving to post-incident activities.

- Validation Activities:
  - **System Security Check:**
    - Verify security of every system, focusing on those involved in the compromise.
    - Use configuration management tools for automation.
    - Ensure all systems are patched and protected against known vulnerabilities.
  - **Vulnerability Scanning:**
    - Use scanners to confirm no serious publicly exposed vulnerabilities.
    - Provides an attacker's perspective on the network.
  - **Account Review:**
    - Focus on systems involved in the incident.
    - Ensure only authorized accounts exist.
    - Check permissions match approved access authorizations.
  - **Logging Verification:**
    - Ensure systems and applications are logging security information.
    - Confirm logs are being collected and communicated with security monitoring tools.
    - Verify Security Information and Event Management (SIEM) solution is receiving log entries.
  - **Restoration Verification:**
    - Confirm restoration of capabilities and services.
    - Ensure readiness for normal business operations.

- Outcome:
  - Once validation efforts are complete, the incident can be resolved, and post-incident activities can begin.

#

## Post-Incident Activities

- Lessons Learned Process:
  - Reflect on individual roles and the team's overall response.
  - Improve processes and technologies for future incidents.
  - Conduct sessions quickly to capture accurate details.
  - Use a neutral facilitator to guide the session.
  - Document the lessons learned and suggested improvements.

- Root Cause Analysis:
  - Focus on identifying what went wrong initially.
  - Address technical, operational, and managerial causes.
  - Aim to improve the organization's security program.

- Evidence Retention:
  - Decide on retaining or discarding digital evidence.
  - Follow the organization's data retention policy.
  - Securely retain evidence with a well-documented chain of custody if needed.

- Generation of Indicators of Compromise:
  - Identify new indicators from the incident.
  - Add these indicators to the security monitoring program for better future detection.

- Incident Summary Report:
  - Prepare a technical document detailing the incident and response steps.
  - Use it for institutional knowledge and training purposes.

#

## Incident Response Exercises

- Read-throughs (Checklist Reviews):
  - Simplest form of incident response plan testing.
  - Involves distributing the current plan to all personnel for review.
  - Team members provide feedback on updates needed to keep the plan current.

- Walkthroughs (Tabletop Exercises):
  - Involves getting everyone together to review the plan simultaneously.
  - More effective than read-throughs as it allows team discussion.
  - Helps in identifying gaps and improving the plan collaboratively.

- Simulations:
  - Team discusses how they would respond to a specific incident scenario.
  - Can evolve into full-scale cybersecurity exercises with hands-on components.
  - May involve red and blue teams for a more realistic exercise.

#

# Attack Frameworks

## MITRE ATT&CK

- Introduction to MITRE ATT&CK Framework
  - Developed by the Mitre Corporation, a nonprofit think tank.
  - Focuses on cybersecurity research and development.

- Purpose of the ATT&CK Framework
  - Collection of knowledge about attackers from real-world organizations.
  - Helps understand adversarial tactics, techniques, and common knowledge.

- Framework Structure
  - **Tactics:** General strategies attackers pursue (e.g., initial access, execution, persistence).
  - **Techniques:** Specific methods used to achieve tactics (e.g., access token manipulation).

- Example: Privilege Escalation
  - Techniques include manipulating access tokens, exploiting accessibility features, tampering with DLLs.
  - Detailed pages for each technique with sub-techniques, descriptions, examples, mitigating controls, and detection methods.

- Utility of the ATT&CK Framework
  - Helps understand the threat environment.
  - Provides insights into specific techniques used by adversary groups.

#

## Dimonad Model of Intrusion Analysis

- Core Features of the Diamond Model:
  - **Adversary:** The person or group attempting to compromise information or systems.
    - Can be an external threat (e.g., nation state, hacking group) or an internal threat (e.g., malicious insider).
  - **Victim:** The organization or specific system targeted by the attack.
  - **Capabilities:** The tools and techniques used by the adversary (e.g., manipulating access tokens, impersonating help desk staff, injecting SQL code).
  - **Infrastructure:** The physical and logical resources used by the adversary, which can include their own or stolen resources (e.g., systems, networks, email accounts, IP addresses).

- Relationships in the Diamond Model:
  - The adversary leverages infrastructure and capabilities to target the victim.
  - Victims can use observed elements of infrastructure and capabilities to learn more about the adversary.

- Meta Features of Intrusion Events:
  - **Time of Activity:** When the attack took place.
  - **Phase of Activity:** The stage of the attack.
  - **Result:** Whether the attack was successful.
  - **Directionality:** The path of the attack (e.g., infrastructure to victim or victim to infrastructure).
  - **Methodology:** Corresponds to the attack vector.
  - **Resources:** Information, software, hardware, funds, facilities, and access needed for the attack.

#

## Cyber Kill Chain Analysis 

- Cyber Kill Chain Overview:
  - Developed by Lockheed Martin to model the phases of an attack.
  - Focuses on activities of advanced persistent threats (APTs).

- Phases of the Cyber Kill Chain:
  1. **Reconnaissance:**
     - Gathering information about the target using active or passive techniques.
  2. **Weaponization:**
     - Creating a weapon to exploit a specific vulnerability in the victim’s environment.
  3. **Delivery:**
     - Delivering the weapon to the victim through vectors like email, infected websites, or storage media.
  4. **Exploitation:**
     - Exploiting the targeted vulnerability to gain access to the system.
  5. **Installation:**
     - Installing malware on the compromised system for remote command and control.
  6. **Command and Control (C2):**
     - Establishing a channel to remotely control the compromised resource.
  7. **Actions on Objectives:**
     - Using the compromised resource to achieve the attacker’s original objectives.

- Purpose:
  - Helps analysts reconstruct intrusions by understanding the attack phases.

#

## Testing Guides

- Role of Cybersecurity Analysts:
  - Responsible for investigating attacks and testing systems to prevent future attacks.

- Key Testing Standards:
  1. **Open Source Security Testing Methodology Manual (OSSTMM):**
     - Published by The Institute for Security and Open Methodologies.
     - Provides guidance on testing the security of physical locations, human interactions, and communications.
  2. **Open Web Application Security Project (OWASP) Web Security Testing Guide:**
     - Focuses specifically on testing the security of web applications.

#

# Incident Investigation 

## Logging Security Information

- System Monitoring:
  - Generates massive amounts of data.
  - Crucial for incident response efforts.

- Types of Logs:
  - **Network Logs:** NetFlow data shows systems that communicated and data exchanged.
  - **DNS Logs:** Provide information on network name lookups and external communications.
  - **System Logs:** Record security events and system activities (e.g., Windows Event Logs).
  - **Application Logs:** Track application-level activities, including logins and data access.
  - **Authentication Logs:** Show who used centralized authentication services and accessed systems.
  - **Specialized Logs:** Include VoIP and call manager logs for SIP traffic.

- Additional Data Sources:
  - **Dump Files:** From network traffic and memory analyzers.
  - **Vulnerability Scan Output:** Helps identify targeted vulnerabilities.

- Syslog Protocol:
  - **Components:** Header, Facility, Severity, and Message.
  - **Severity Levels:** Range from 0 (emergency) to 7 (debug).
  - **Versions:** Original Syslog, syslog-ng (1998), and Rsyslog (2004).
  - **Usage:** Supported by Linux systems for standardized log messages.

- Log Management:
  - **Retention:** Balance between security needs and storage costs.
  - **Tagging:** Use tags for easier sorting and filtering during analysis.
  - **Centralization:** Tools like NXLog for centralized logging across platforms.

#

## Security Information and Event Management

- Importance of Log Files:
  - Log files are crucial for detecting suspicious activities across systems, networks, and applications.
  - **Challenges:** Reviewing detailed logs manually is tedious and time-consuming due to the sheer volume of log entries.

- Role of SIEM Systems:
  - **Central Collection Point:** SIEM systems collect log entries from various sensors, storing them securely.
  - **Artificial Intelligence:** They use AI to correlate log entries and detect patterns of potentially malicious activity.

- Log Correlation:
  - SIEM systems can piece together different log entries to identify security incidents that might be missed if logs are siloed in different departments.

- Example of Log Correlation:
  - Intrusion detection system notices attack signature.
  - Firewall logs an inbound connection from an unfriendly country.
  - Web server reports suspicious queries.
  - Database server notes abnormal queries.
  - Router logs large data flow to the internet.

- SIEM Dashboards:
  - Provide centralized views of the network, generate alerts for unusual activities, and facilitate trend analysis.

- SOAR Platforms:
  - **Definition:** Stands for Security Orchestration, Automation, and Response.
  - **Capabilities:** Enhanced version of SIEM, automating responses to security events.
  - **Playbooks:** Process-focused responses that combine automated and human activities.
  - **Runbooks:** Fully automated responses triggered by specific events to aid rapid response and investigation.

#

## Cloud Audits and Investigations

- Cloud Audit Challenges:
  - Virtualization and cloud computing introduce unique assurance issues.
  - Using service providers for data storage, processing, and transmission expands the audit scope.
  - Provider's security controls are within the audit scope.

- Auditing Cloud Providers:
  - Direct audits of cloud providers (e.g., Microsoft, Amazon, Google) are impractical due to global distribution and access restrictions.
  - Cloud providers conduct their own audits and share results with customers.

- SOC Reports:
  - **SOC 1:** Focuses on controls relevant to financial audits.
  - **SOC 2:** Evaluates confidentiality, integrity, and availability controls; contains sensitive information.
  - **SOC 3:** Similar to SOC 2 but designed for public consumption with high-level information.
  - **Type 1 Reports:** Describe controls and auditor’s opinion on their suitability.
  - **Type 2 Reports:** Include Type 1 details plus results of control testing.

- Audit Standards:
  - **SSAE 18:** U.S. standard by the American Institute of Certified Public Accountants.
  - **ISAE 3402:** International standard by the International Accounting and Assurance Standards Board.

- Security Investigations in the Cloud:
  - Challenges in accessing critical security information during incidents.
  - Regulatory and jurisdictional complexities with data breach notification laws.

#

# Forensic Techniques

## Conducting Investigations

- Types of Investigations:
  - **Operational/Administrative Investigations:** Focus on resolving issues related to the organization’s technology infrastructure (e.g., server errors, network congestion). Aim to restore normal operations and conduct root cause analysis.
  - **Criminal Investigations:** Conducted by government agencies to investigate violations of criminal law. Use the highest standard of evidence: beyond a reasonable doubt.
  - **Civil Investigations:** Investigate non-criminal offenses involving disputes between parties (e.g., contract disputes, employment law violations). Use a lower standard of evidence: preponderance of the evidence.
  - **Regulatory Investigations:** Conducted by government agencies or independent regulators to investigate violations of administrative law or industry standards. Use the appropriate standard of evidence based on the case type.

- Operational Investigations:
  - Aim to resolve technical issues and restore normal operations.
  - Conduct root cause analysis to prevent future issues.

- Criminal Investigations:
  - Conducted by government agencies.
  - Aim to investigate violations of criminal law.
  - Use the highest standard of evidence: beyond a reasonable doubt.

- Civil Investigations:
  - Investigate non-criminal disputes between parties.
  - Use a lower standard of evidence: preponderance of the evidence.

- Regulatory Investigations:
  - Conducted by government agencies or independent regulators.
  - Investigate violations of administrative law or industry standards.
  - Use the appropriate standard of evidence based on the case type.

- Interviews vs. Interrogations:
  - **Interviews:** Voluntary questioning to gather valuable information.
  - **Interrogations:** Questioning hostile subjects without consent, conducted by trained law enforcement officials.

#

## Evidence Types

- Types of Evidence:
  - **Real Evidence:** Tangible objects presented in court (e.g., a bloody knife in a criminal case or computer equipment in digital crimes).
  - **Documentary Evidence:** Written or digital information used to demonstrate facts (e.g., contracts, computer logs).
    - **Authentication:** Must be verified as legitimate.
    - **Best Evidence Rule:** Original documents are superior to copies.
    - **Parol Evidence Rule:** Written agreements are assumed to be the entire agreement unless modified in writing.
  - **Testimonial Evidence:** Information provided by a witness in court.
    - **Direct Evidence:** Witness describes their direct observations.
    - **Expert Opinion Evidence:** Experts interpret facts based on their expertise.

- Legal Rules for Evidence:
  - **Authentication:** Ensures the legitimacy of documentary evidence.
  - **Best Evidence Rule:** Prefers original documents over copies.
  - **Parol Evidence Rule:** Written contracts are considered complete and cannot be verbally modified.

- Testimonial Evidence:
  - **Direct Evidence:** Witnesses provide firsthand accounts.
  - **Expert Opinion Evidence:** Experts draw conclusions from evidence.
  - **Hearsay Rule:** Witnesses cannot testify about what others told them outside of court, with some exceptions.

- Application in Cybersecurity:
  - **Real Evidence:** Could include physical computer hardware.
  - **Documentary Evidence:** Might involve digital logs and records.
  - **Testimonial Evidence:** Cybersecurity experts may provide direct or expert testimony.

#

## Introduction to Forensics

- Digital Forensics Goal: Collect, preserve, analyze, and interpret digital evidence artifacts to support investigations.

- Types of Evidence: Includes data from smartphones, laptops, and network traffic logs.

- Guiding Principle: Investigators must avoid actions that alter evidence, similar to wearing gloves at a crime scene to avoid contamination.

- Volatility of Evidence: Digital evidence varies in permanence. Hard drives are less volatile than RAM, so more volatile evidence should be gathered first.

- Evidence Collection Order:
  1. Network traffic
  2. Memory contents
  3. System configuration and process information
  4. Files (temporary files first)
  5. Logs
  6. Archived records

- Time Sensitivity: Accurate timestamps are crucial. Investigators should record the current time from a reliable source and compare it to the device’s time (time offset).

- Non-Digital Evidence: Video recordings and witness statements can also be valuable.

- Resource Tracking: Track time and expenses for proper billing and resource management in investigations.

#

## Syestem and File Forensics

- Digital Evidence Sources: Computers, mobile devices, and digital media are common sources.

- Principle of Evidence Collection: Never alter the evidence to avoid misinterpretation.

- Working with Evidence: Forensic analysts create copies or images of physical evidence to avoid tampering.

- Use of Write Blockers: Devices that prevent any data from being written to the evidence during analysis.

- Hashing:
  - **Definition:** A unique signature of a file created using a mathematical algorithm.
  - **Purpose:** Demonstrates that evidence hasn’t been altered.
  - **Example:** Small changes in text result in completely different hash values.

- File Metadata: Includes details about the file’s creation, storage, and modification history.

- Additional Data Collection: Screenshots, system memory, process table, and system configuration can also be collected.

- Specialized Discipline: Only trained professionals should perform forensic investigations to avoid damaging evidence.

#

## File Carving

- File Deletion: Deleting a file using operating system commands doesn’t remove the file’s data; it only deletes the reference, leaving the data in unallocated disk space.

- File Carving: This technique allows recovery of files from unallocated space on a hard disk image, useful in forensic investigations.

- Bulk Extractor Tool:
  - **Usage:** A widely used file carving utility in the security community.
  - **Commands:**
    - `-o` option: Selects an output directory (e.g., `extracted_data`).
    - `-S jpeg_carve_mode=2`: Extracts JPEG images.
    - Disk image input: Uses a disk image file (e.g., `disk_image.dd`).
  - **Output:** Stores extracted data in the specified directory, including text files and a directory for carved JPEG files.

- Example Outputs:
  - `url.txt`: Contains URLs found on the disk image.
  - `windows.txt`: Lists Windows files retrieved from the disk image.
  - `jpeg_carved Directory`: Stores successfully restored JPEG files.

- File Recovery: Sometimes file names are found, but actual files may be unrecoverable if data has been overwritten.

- Forensic Importance: File carving is crucial for recovering temporary data stored during security incidents.

- Additional Tool: WinHex – A Windows utility for low-level data editing in forensics and data recovery.

#

## Creating Forensic Images

- Connecting and Imaging a Drive:
  - Use a write blocker to connect the drive.
  - Utilize disk acquisition tools to create a snapshot of the drive.
  - On Linux, use the `dd` utility to create images:
    - **Command:** `sudo dd if=/dev/sdf of=myImage.img status=progress`
    - This command creates an image file and shows progress.
  - Compute hash values for authenticity:
    - Use `md5sum myImage.img` for MD5 hash.
    - Use `shaum myImage.img` for SHA hash.
  - Print and store hash values with the image for chain of custody.

- Using FTK Imager on Windows:
  - Open FTK Imager and add the drive.
  - Right-click the drive and select “Export Disk Image.”
  - Choose the raw image format (dd).
  - Provide case information, destination, and start the image creation.
  - FTK Imager computes MD5 and SHA hash values during the process.
  - It also creates a directory listing for the image.

- Post-Image Creation:
  - Use the created images for forensic analysis with any forensic utility.
  - Maintain chain of custody and evidence log with hash values and case information.

#

## Digital Forensics ToolKits

- Digital Forensics Workstation:
  - Requires a system with substantial RAM and a powerful CPU for computational tasks.
  - Needs ample onboard hard disk space for intermediate analysis storage.

- Forensic Software:
  - Essential tools include EnCase, FTK, or Autopsy for robust forensic analysis.
  - Cryptographic tools like `md5sum` and `shaum` for hashing and encryption.

- Log Viewers:
  - Necessary for processing log files from various enterprise infrastructure components.

- Storage and Media:
  - Large removable media drives for storing drive images and forensic evidence.
  - Drives should be wiped clean before each use.

- Write Blockers and Adapters:
  - Write blockers to prevent accidental evidence corruption.
  - A variety of drive adapters, connectors, and cables for different devices.

- Documentation:
  - Include incident response plan, chain of custody forms, incident forms, and contact lists.

- Miscellaneous Items:
  - Office supplies, cameras for photographic and video evidence, crime scene tape, evidence bags, and tamper-proof seals.

#

## Operating System Analysis

- Live Analysis:
  - Interaction with a live system to collect volatile information.
  - Memory dumps are crucial for capturing the current contents of RAM.

- Memory Dump:
  - Use tools like FTK Imager to create memory dumps.
  - Store the memory capture file for offline analysis.

- Swap and Page Files:
  - Operating systems may write data from memory to disk, creating swap and page files.
  - These files can be useful for forensic analysis.

- Sysinternals Suite:
  - A collection of Windows utilities useful for forensic analysts.
  - Originally developed by Winternals, now maintained by Microsoft.

- Key Sysinternals Tools:
  - **AccessEnum:** Shows permissions assigned to users and groups.
 
#

## Password Forensics

- Password Cracking in Forensics:
  - Cybersecurity analysts use password cracking tools to retrieve passwords from password files during forensic analysis.
  - Password files contain password hashes, not plain text passwords, to enhance security.

- Password Storage:
  - On Linux systems, password files contain user credentials as hashes.
  - Hashes are computed using a one-way function and stored in a shadow password file, which is highly restricted.

- Hash Functions:
  - Hash functions convert variable-length input into fixed-length output.
  - Key properties: collision-resistant, irreversible, and any input change produces a different output.
  - Collisions can occur due to the birthday problem.

- Types of Password Attacks:
  - **Brute Force Attacks:** Guess all possible combinations; effective against short passwords.
  - **Dictionary Attacks:** Use common words to guess passwords.
  - **Hybrid Attacks:** Combine dictionary attacks with common variations (e.g., adding numbers).
  - **Rainbow Table Attacks:** Use precomputed hashes of common passwords to save computational steps.

- Practical Demonstration:
  - The instructor demonstrates adding user accounts with different password complexities on a Linux server.
  - Uses the `unshadow` command to combine password and shadow files for analysis.
  - Utilizes "John the Ripper" tool to crack passwords, showing effectiveness against simple and common passwords.

- Security Recommendations:
  - Ensure strong hashing algorithms and safeguard password files.
  - Use multi-factor authentication for enhanced security.

#

## Network Forensics

- Network Forensics Overview:
  - Forensic investigators analyze communications sent and received by targeted systems.
  - Network transmissions are digital, consisting of ones and zeros sent over various media (copper wire, fiber optics, wireless).

- Media Types and Eavesdropping:
  - Copper and fiber optic cables can be tapped.
  - Wireless signals can be intercepted.
  - Switches and routers can be compromised to eavesdrop on communications.

- Tools for Network Forensics:
  - **Protocol Analyzers (e.g., Wireshark):**
    - Conduct full packet capture, grabbing every bit seen on a network.
    - Reconstruct packets to exchange data between systems.
    - Provide detailed information like timestamps, source/destination IP addresses, protocols, and packet contents.

- Challenges with Full Packet Capture:
  - Requires massive amounts of storage.
  - Filters can save relevant information if known in advance.

- NetFlow Data:
  - Captures high-level information about communications (source/destination IPs, ports, timestamps, data amount).
  - Similar to phone call records on a telephone bill.
  - Useful for understanding "who talked to whom" without storing full packet details.

- Other Data Formats:
  - **S Flow and IPFIX:** Provide similar data to NetFlow, depending on network device support.
  - **Bandwidth Monitors:** Offer insights into network utilization and traffic on different links.

#

## Software Forensics

- Definition and Uses:
  - Software forensics involves analyzing software code to render expert opinions.
  - Two major uses:
    - Resolving intellectual property disputes.
    - Identifying the origins of malware.

- Intellectual Property Disputes:
  - Common in civil disputes.
  - Example: A developer moves to a competitor, and the original company accuses the competitor of stealing code.
  - Forensic experts analyze the code to determine if the new features were independently developed or copied.

- Malware Identification:
  - Analyzing malicious code to compare it with known malware.
  - Example: UK, Canada, and US cybersecurity agencies released a report in 2020 accusing Russian Intelligence of hacking COVID-19 vaccine development efforts.
  - The report included code snippets to identify the Russian activity, dubbed Cozy Bear.
  - Publicly available signatures can be used to frame others, so they should be used cautiously.

- Email Header Analysis:
  - Email headers contain technical information useful for forensic analysis.
  - Example: Analyzing email headers in Gmail to see the path and technical details of the message.
  - Tools like MxToolbox parser can simplify the analysis of email headers.

- Application Metadata:
  - Web servers and other applications generate metadata useful for forensic analysis.

#

## Mobile Device Forensics

- Mobile Devices as Evidence:
  - Mobile devices contain a wealth of evidence, including emails, texts, voicemails, cloud-stored files, and GPS tracking data.
  - **Metadata Importance:** Metadata generated by mobile devices can provide significant insights.
  - **Encryption Challenges:** Strong encryption used by manufacturers protects private data, making forensic analysis difficult.
  - **Law Enforcement Insight:** Many devices are encrypted, limiting successful forensic analysis. However, some devices remain unencrypted or lack passcode protection, making them accessible.
  - **Specialized Tools Required:** Forensic analysis of mobile devices requires specialized tools and expertise.
  - **Niche Field:** Mobile device forensics is a specialized area, and expert help is often necessary for effective analysis.

#

## Embedded Device Forensics

- Definition of Embedded Devices: Special-purpose computer systems found in everyday objects and industrial settings, containing both hardware and software.

- Data Collection: Embedded devices collect large amounts of information valuable for forensic investigations.

- Examples of Embedded Devices:
  - **Cars:** Contain numerous embedded systems for various functions, such as climate control and GPS navigation. GPS data can be used to track a vehicle’s location over time.
  - **Homes:** Include security systems, smart thermostats, and smart lights, all of which can provide data on presence and movement within a building.
  - **Smart Home Assistants:** Devices like Amazon Echo and Google Home collect audio data and send it to the cloud for processing.

- Forensic Value: Information from embedded devices can help determine factors like location, presence, and even time of death.

- Case Example: In Bentonville, Arkansas, investigators used data from an Amazon Echo device in a murder investigation to gather background sounds relevant to the crime.

#

## Chain of Custody

- Chain of Custody Definition: The chain of custody, also known as the chain of evidence, ensures evidence has not been tampered with during collection, analysis, or storage.

- Importance: Critical for maintaining the authenticity of evidence, especially in court or formal settings.

- Initial Collection:
  - Place evidence in an evidence storage bag.
  - Label with date, time, location, collector’s name, and contents.
  - Seal with a tamper-resistant seal.

- Evidence Log:
  - Accompanies each piece of evidence.
  - Records events like collection, transfer, storage, and opening/resealing.
  - Must include the name of the person, date, time, purpose, and nature of the action.

- Breach of Chain of Custody:
  - Failure to maintain the evidence log can lead to a breach.
  - Evidence may become inadmissible in court if a satisfactory chain of custody is not proven.

#

## Edisovery and Evidence Production

- Electronic Discovery Process:
  - **Preservation:**
    - Issuance of a legal hold to preserve records relevant to potential litigation.
    - Suspension of automated processes that might destroy relevant data, especially log entries.
  - **Collection:**
    - Initiated by the legal team when deemed necessary.
    - Involves gathering documents from file servers, individual computers, email servers, enterprise systems, etc.
    - Utilization of electronic discovery management products for collection and organization.
  - **Production:**
    - Presentation of collected records to the other side in a legal dispute.
    - Attorneys review records for relevance and legal privileges.
    - Creation of an electronic file containing all relevant records for sharing.

- Role of Cybersecurity Professionals:
  - Support preservation by ensuring relevant logs are not purged.
  - Assist in the collection of electronic records across various systems.
  - Provide technical assistance throughout the e-discovery process.

- Common Outcomes:
  - Most litigation holds do not progress beyond preservation and collection.
  - Actual production of evidence is rare unless the organization frequently faces litigation.

#

# Business Continunity

## Business Continunity Planning

- Definition and Importance:
  - Business continuity planning involves activities to keep a business running during adversity.
  - Adversity can range from minor incidents (e.g., system failure) to major disasters (e.g., earthquakes, tornadoes).
  - It’s also known as Continuity of Operations Planning (COOP).

- Core Security Concept:
  - Business continuity is crucial for achieving the security objective of availability.
  - It supports the three main objectives of information security: confidentiality, integrity, and availability.

- Scope Definition:
  - Teams should define the scope of their business continuity plan early on.
  - Key questions include: What business activities and systems will be covered? What types of controls will be considered?

- Business Impact Assessment (BIA):
  - A BIA helps in making prioritization decisions.
  - It identifies mission-essential functions and traces them to critical IT systems.
  - The assessment includes identifying potential risks and conducting a risk assessment.

- Prioritization and Control Selection:
  - The BIA results in a prioritized list of risks.
  - Planners use this list to select controls that mitigate risks within acceptable expense limits.
  - Example: Investing in a $50,000 flood prevention system to reduce hurricane damage risk.

- Cloud-Centric Environment:
  - Business continuity planning in cloud environments involves collaboration between service providers and customers.
  - Risks can be mitigated by service providers (e.g., building flood prevention systems) or by customers (e.g., replicating services across data centers).

#

## Business Continunity Controls

- Redundancy in Systems:
  - Ensuring systems are designed to continue operating despite the failure of a single component.
  - Example: Replacing a single web server with a clustered farm of servers to avoid a single point of failure.

- Single Point of Failure Analysis:
  - Identifying and removing single points of failure in systems.
  - Example: Replacing a single firewall with a pair of high-availability firewalls.

- Network Redundancy:
  - Introducing redundancy in internal and external network connections to maintain service if one link fails.

- Cost-Benefit Analysis:
  - Balancing the cost of addressing single points of failure with the potential benefits.

- Comprehensive IT Contingency Planning:
  - Considering various risks beyond single points of failure, such as vendor bankruptcy, utility service failures, and capacity issues.

- Personnel Succession Planning:
  - Identifying essential team members and their potential successors.
  - Providing professional development opportunities for successors to ensure smooth transitions.

#

## High avilaibility and Fault Tolerance 

- High Availability (HA):
  - Uses multiple systems to protect against failures.
  - Example: Cluster of web servers or a pair of firewalls.
  - Geographic dispersal to protect against facility damage.

- Fault Tolerance (FT):
  - Makes a single system resilient to technical failures.
  - Example: Dual power supplies in servers.

- Load Balancing:
  - Spreads the burden of providing a service across multiple systems.
  - Different from HA but often used together.

- Common Points of Failure:
  - **Power Supply:**
    - Dual power supplies, separate power sources, UPS, and generators.
  - **Storage Media:**
    - RAID technologies (mirroring and striping with parity).
    - RAID is not a backup strategy; regular data backups are necessary.
  - **Networking:**
    - Redundancy with multiple internet service providers and NIC teaming.
    - Multi-path approaches for critical network paths.

- Diversity in Environment:
  - Use diverse technologies and vendors to avoid simultaneous failures.
  - Diversify cryptography and other security controls.

#

# Disaster Recovery 

## Disaster Recovery

- Definition: Disaster recovery is a subset of business continuity activities designed to restore normal operations quickly after a disruption.
- Triggers: Can be activated by natural disasters (e.g., hurricanes) or man-made disasters (e.g., ransomware attacks).
- Initial Response: Focuses on containing damage and restoring immediate capacity, which may involve:
  - Activating alternate processing facilities
  - Containing physical damage
  - Engaging emergency contractors

- Staffing: Employees may take on temporary roles different from their usual duties; flexibility is crucial.
- Communication: Secure, reliable communication mechanisms are essential for:
  - Activating the disaster recovery process
  - Regular status updates
  - Ad hoc tactical communications

- Assessment Phase: Post-initial response, the focus shifts to:
  - Triage damage
  - Implement functional recovery plans
  - Intermediate steps for temporary restoration

- Recovery Metrics:
  - **Recovery Time Objective (RTO):** Targeted time to restore service after disruption.
  - **Recovery Point Objective (RPO):** Maximum acceptable data loss period.
  - **Recovery Service Level (RSL):** Percentage of service that must be available during a disaster.

- Execution: Plan execution involves restoring operations in an orderly fashion.
- Training and Awareness: Regular training and awareness programs are critical to ensure all personnel are prepared for their roles in disaster recovery.

#

## Backups

- Importance of Backups:
  - Essential for disaster recovery and data protection.
  - Critical for businesses reliant on data, such as proprietary designs or customer lists.

- Backup Methods:
  - **Manual Copying:** Simple but error-prone.
  - **Tape Backups:** Traditional method, still common but unwieldy.
  - **Disk-to-Disk Backups:** Modern method, often using separate facilities for disaster protection.
  - **Cloud Backups:** Provides geographic diversity and additional protection from cloud providers.

- Types of Backups:
  - **Full Backups:** Complete copy of all data.
  - **Snapshots:** Quick full backups using hardware platform capabilities.
  - **Differential Backups:** Copies data changed since the last full backup.
  - **Incremental Backups:** Copies data changed since the last full or incremental backup.

- Restoration Process:
  - **Differential Backup Strategy:** Restore the last full backup and the most recent differential backup.
  - **Incremental Backup Strategy:** Restore the last full backup and all incremental backups in sequence.

#

## Restoring Backups

- Common Reasons for Restoring Backups:
  - Correcting human or technical errors.
  - Restoring accidentally deleted files.
  - Recovering crashed servers.

- Disaster Recovery Planning:
  - Prioritize restoring the most important services first.
  - Focus on crucial business processes before less important services.

- Non-Persistence Goal:
  - Back up critical data, not entire systems.
  - Use infrastructure as code to rebuild servers and recover data.

- Partial System Restorations:
  - Revert to a known state or last known good configuration to fix configuration errors.

- Live Boot Media:
  - Use USB drives with live boot media to recover data from storage media without using the device’s operating system.
  - Boot a server or endpoint system from an operating system on a USB drive.
  - Recover data from the device’s storage media without using the device’s operating system.


#

## Disaster Recovery Sites

- Disaster Recovery Sites: Alternate processing facilities for use when the primary site is unavailable.
  - **Hot Sites:** 
    - Fully operational data centers.
    - Ready to run with all necessary equipment and data.
    - Can be activated immediately, often automatically.
    - High cost, similar to running the primary data center.
  - **Cold Sites:** 
    - Essentially empty data centers.
    - Have core infrastructure but lack servers and data.
    - Lower cost but require significant time to activate (weeks or months).
  - **Warm Sites:** 
    - Have necessary hardware and software but not running in parallel.
    - Moderate cost and activation time (hours or days).

- Offsite Storage:
  - Used for storing business data backups.
  - Provides geographic redundancy to protect against localized disasters.
  - Backups can be transported physically or digitally (site replication).

- Backup Storage Formats:
  - **Online Backups:** Available for immediate restoration, higher cost.
  - **Offline Backups:** Require manual intervention, lower cost.

- Alternate Business Processes:
  - Organizations may use alternate processes, like paper-based systems, during extended downtime.

#

## Testing BC/DR Plans

- Purpose of Disaster Recovery Testing:
  - Validates that the disaster recovery (DR) plan functions correctly.
  - Identifies necessary updates due to technology or business process changes.

- Types of Disaster Recovery Testing:
  - **Read-throughs (Checklist Reviews):**
    - Simplest form of DR testing.
    - Staff review the current plan and provide feedback on updates.
  - **Walkthroughs (Tabletop Exercises):**
    - Team reviews the plan together.
    - More effective as it allows discussion and collaboration.
  - **Simulations:**
    - Team discusses how they would respond to a specific emergency scenario.
    - Involves designing a simulated emergency situation.
  - **Parallel Tests:**
    - Activates the DR plan and runs the DR environment in parallel to the primary site.
    - Does not switch operations to the backup environment.
  - **Full Interruption Tests:**
    - Most effective but potentially disruptive.
    - Shuts down the primary environment and operates out of the DR environment.
    - Highlights deficiencies but may affect normal operations.

- Testing Strategy:
  - Organizations often use a combination of different test types.
  - Regular read-throughs and walkthroughs supplemented with periodic simulations and parallel tests.
  - Each test type offers different advantages to prepare for actual disasters.

#

## After-Action Reports

- Purpose of After-Action Reports:
  - Create a formal record of the incident.
  - Document circumstances surrounding the event.
  - Identify opportunities for future improvement.

- Importance:
  - Facilitate recognition of lessons learned.
  - Allow continuous improvement of processes.
  - Should be written after every activation of business continuity or disaster recovery plans.

- Content of After-Action Reports:
  - **Executive Summary:** 
    - Brief overview of the event and major findings.
    - Written for an audience that may only read this section.
  - **Background Information:** 
    - Details about the operating environment and external factors.
  - **Detailed Summary of Facts:** 
    - Explanation of what happened.
    - Key questions: Who, What, When, Why, Where, and How.
  - **Lessons Learned:** 
    - Performance evaluation: what went well and what didn’t.
    - Suggestions for improvement.
  - **Next Steps:** 
    - Clear outline of actions based on lessons learned.
    - Assign responsibilities and timelines for implementing changes.

- Continuous Improvement:
  - Ensures the organization learns from each incident.
  - Helps in refining disaster recovery and business continuity processes.

#

# Quiz

## Incident Response Program

You should rebuild any system that may have been compromised during a security incident.?
- TRUE: You should rebuild any system that may have been compromised during a security incident.

What should responders do after containing an incident?
- Begin a triaging process: A triaging process rates incident severity and identifies the potential impact of the incident.

During an incident response, what is the highest priority of first responders?
Contain the damage: During an incident response, the highest priority of first responders is containing the damage.

What containment strategy moves compromised systems to a separate VLAN attached to the enterprise network?
- Segmentation: When you divide networks into logical segments, grouped by types of users or systems, you have performed segmentation.
      - Isolation: When you move compromised systems to a network that is completely disconnected from the rest of the network, you have performed isolation. That is not the case in this scenario.

Which one of the following is not a suggested criteria for evaluating containment strategies?
- identity of the attacker: The identity of the attacker is not normally very relevant to determining how to contain an incident.

During which incident response exercises are team members asked to review their role in the plan individually?
- Read-through: During a read-through, IR team members are asked to review their roles in the plan individually.

Which of these is not one of the incident response plan elements?
- Board approval: Board approval is not one of the incident response plan elements. Incident response plans are normally approved by senior management, not the Board.

Who is the most effective person to lead a lessons learned review?
- an independent facilitator: The most effective person to lead a lessons learned review is an independent facilitator. This individual is impartial and trained to lead constructive conversations.

You are normally required to report security incidents to law enforcement if you believe a law may have been violated.?
- FALSE: While you may believe a law has been violated, you do not typically have an obligation to report this to law enforcement.

Which one of the following individuals would not normally be found on the incident response team?
- CEO: The CEO would not normally be part of an incident response team. They should be informed of serious incidents but would not normally directly participate.

## Attack Frameworks

Which of these provides guidance on testing the security of physical locations, human interactions, and communications?
- OSSTMM: The Open Source Security Testing Methodology Manual (OSSTMM) provides guidance on testing the security of physical locations, human interactions, and communications.

What company developed the Cyber Kill Chain?
- Lockheed Martin: Lockheed Martin developed the Cyber Kill Chain.

Which of these is not a core feature of the Diamond Model?
- Exploit: Exploit is not a core feature of the Diamond Model.
      - Infrastructure: The infrastructure is one of the core features of the Diamond Model.

What do the columns in the ATT&CK matrix represent?
- Tactics: The columns in the ATT&CK matrix represent tactics which are the attacker's ultimate objectives in carrying out the attack.

## Incident Investigation 

Which type of Service Organization Controls audit is designed for public consumption?
- SOC 3: SOC 3 provides high-level, public reporting of confidentiality, integrity, and availability controls.

SIEMs apply artificial intelligence techniques to log entries.
- TRUE: SIEMs apply artificial intelligence techniques to log entries.

Which of these syslog severity levels equates to an emergency?
- 0: A syslog severity level of 0 equates to an emergency.

## Forensic Techniques

## Business Continunity

## Disaster Recovery 
