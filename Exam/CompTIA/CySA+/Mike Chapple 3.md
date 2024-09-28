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

#

## Evidence Types

#

## Introduction to Forensics

#

## Syestem and File Forensics

#

## File Carving

#

## Creating Forensic Images

#

## Digital Forensics ToolKits

#

## Operating System Analysis

#

## Password Forensics

#

## Network Forensics

#

## Software Forensics

#

## Mobile Device Forensics

#

## Embedded Device Forensics

#

## Chain of Custody

#

## Edisovery and Evidence Production

#

# Business Continunity

## Business Continunity Planning

#

## Business Continunity Controls

#

## High avilaibility and Fault Tolerance 

#

# Disaster Recovery 

## Disaster Recovery

#

## Backups

#

## Restoring Backups

#

## Disaster Recovery Sites

#

## Testing BC/DR Plans

#

## After-Action Reports

#

# Quiz

## Incident Response Program

## Attack Frameworks

## Incident Investigation 

## Forensic Techniques

## Business Continunity

## Disaster Recovery 
