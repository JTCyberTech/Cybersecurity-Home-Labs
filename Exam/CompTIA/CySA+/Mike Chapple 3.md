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

#

## Post-Incident Activities

#

## Incident Response Exercises

#

# Attack Frameworks

## MITRE ATT&CK

#

## Dimonad Model of Intrusion Analysis

#

## Cyber Kill Chain Analysis 

#

## Testing Guides

#

# Incident Investigation 

## Logging Security Information

#

## Security Information and Event Management

#

## Cloud Audits and Investigations

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
