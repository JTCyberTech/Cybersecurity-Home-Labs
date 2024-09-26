# SCAP

Purpose of SCAP:
- SCAP (Security Content Automation Protocol) aims to create a consistent language and format for discussing security issues.
- Led by the National Institute for Standards and Technology (NIST).

Components of SCAP:
- **Common Vulnerability Scoring System (CVSS):**
  - Provides a consistent way to evaluate the severity of security vulnerabilities.
  - Widely used in vulnerability scanning products and reports.
  
- **Common Configuration Enumeration (CCE):**
  - Offers a consistent language for sharing system configuration information.
  
- **Common Platform Enumeration (CPE):**
  - Provides a common language for product names and versions.
  
- **Common Vulnerabilities and Exposures (CVE):**
  - Describes vulnerabilities in products using a standardized language.
  
- **Extensible Configuration Checklist Description Format (XCCDF):**
  - Creates and shares checklists and the results of processing those checklists.
  
- **Open Vulnerability and Assessment Language (OVAL):**
  - Describes testing procedures in a programmatic fashion.

### Importance of SCAP:
- Helps in automating vulnerability activities by ensuring systems "speak the same language."
- Reduces ambiguity and confusion in security terminology.




# CVSS 

- **Common Vulnerability Scoring System (CVSS):**
  - Assigns a score to each vulnerability on a 10-point scale.
  - Evaluates eight different metrics to determine the base CVSS score.

- **Exploitability Metrics:**
  - **Attack Vector:** Type of access required by an attacker (Physical, Local, Adjacent Network, Network).
 
![image](https://github.com/user-attachments/assets/e4d7c226-4670-4fa8-b250-c57e766ceb2a)

  - **Attack Complexity:** Difficulty of exploiting the vulnerability (High or Low).
  - **Privileges Required:** Level of access needed (High, Low, None).
  - **User Interaction:** Degree of human involvement required (Required or None).

- **Impact Metrics:**
  - **Confidentiality:** Impact on information confidentiality (None, Partial, High).
  - **Integrity:** Impact on information integrity (None, Low, High).
  - **Availability:** Impact on system availability (None, Low, High).

- **Scope:**
  - Determines if the vulnerability affects other components beyond the initial target (Changed or Unchanged).

![image](https://github.com/user-attachments/assets/68e56572-ebd0-4a0f-b1ed-47cb982b28b3)

#

- **CVSS Base Score Calculation:**
  - Combine individual CVSS metrics to determine the Base Score.
  - Example: Vulnerability report from Nessus detecting outdated SSL Protocol.

- **Interpreting CVSS String:**
  - **AV:N:** Access Vector is Network (remotely exploitable).
  - **AC:L:** Attack Complexity is Low (easy to exploit).
  - **PR:N:** No special privileges required (attacker does not need an existing user or admin account).
  - **UI:N:** No user interaction required (attacker can carry out the vulnerability on their own).
  - **Scope Rating:** Unchanged (exploit cannot access systems outside the same security control).

- **Impact Ratings:**
  - **Confidentiality:** High risk (attacker might eavesdrop on sensitive communications).
  - **Integrity:** None (no risk indicated).
  - **Availability:** None (no risk indicated).

- **Using NIST Calculator:**
  - Input values for individual metrics to get the Base Score.
  - Example values: Network (AV:N), Low (AC:L), None (PR:N), None (UI:N), Unchanged (Scope), High (Confidentiality), None (Integrity and Availability).
  - Result: Base Score of 7.5.

- **Severity Scale:**
  - 0: None
  - 0.1 - 3.9: Low
  - 4.0 - 6.9: Medium
  - 7.0 - 8.9: High
  - 9.0 - 10: Critical

- **Practical Application:**
  - Review and interpret your own scan results.
  - Practice interpreting CVSS scores for exam preparation.

#

- **Primary Responsibilities:**
  - Analyzing reports from vulnerability scans.
  - Presenting information to engineers, developers, administrators, business leaders, and security management.

- **Key Factors for Interpreting Scan Reports:**
  - Severity of the vulnerability.
  - Criticality of the systems affected.
  - Sensitivity of the information involved.
  - Difficulty of remediation.
  - Exposure of the system with the vulnerability.

- **Validation Process:**
  - Confirm the vulnerability exists as stated in the report.
  - Check for false positives by reviewing the details of the scan report.
  - Validate the vulnerability by logging onto the system and confirming the affected version.

- **False Positives:**
  - Vulnerability scanners may produce false positives due to undefined signatures or undetected security controls.
  - *Example*: A report showing a critical vulnerability in the Ubuntu Linux kernel should be validated by checking the specific package causing the issue.

- **Handling Known Vulnerabilities:**
  - Track exceptions in the scanner or configuration management database to avoid redundant reports.
  - Ensure thorough screening to maintain credibility with engineers and developers.

- **Importance of Accurate Reporting:**
  - Avoid escalating false positives to maintain credibility.
  - Ensure engineers and developers take vulnerability reports seriously.

#

- **Consult Industry Standards and Compliance Obligations:**
  - Use industry standards, best practices, or compliance obligations to guide vulnerability remediation.
  - *Example*: PCI DSS requires no high-level vulnerabilities in the cardholder data environment, with a CVSS base score equal to or higher than 4.0.

![image](https://github.com/user-attachments/assets/0168026b-6ce5-4d23-9e39-d4e057eb0424)


- **Leverage Internal Technical Information:**
  - Utilize configuration management systems, log repositories, and other internal data sources.
  - These sources help in detecting and eliminating false positive reports.

- **Correlate Vulnerability Scan Information with Itself:**
  - Monitor historic trends in scan results to identify recurring vulnerabilities.
  - *Example*: Consistent cross-site scripting vulnerabilities in new web applications suggest a need for developer security training or standard input validation libraries.

- **Address Root Causes:**
  - Prevent vulnerabilities by addressing root causes, such as providing developer training or creating standard libraries.
  - It’s more effective to stop vulnerabilities before they enter the environment than to remediate existing ones.

# 

# Common Vulnerabilities

## Server Vulnerabilities


Make this into markdown for my github so i can copy and paste:

Importance of Hands-On Experience:

-  Practical hands-on experience is crucial for passing the exam. 
-  Run vulnerability scans in a test environment and interpret the results. 
 
Common Issues in Scan Reports:

- Out-of-Date Software: 
    - Missing patches on operating systems, applications, or firmware. 
    - Keeping devices patched is essential to avoid security vulnerabilities. 


Unsupported Operating Systems:
- Running outdated OS versions poses high security risks. 
- Example: Windows Server 2003 no longer supported by Microsoft since 2015. 



Buffer Overflow Vulnerabilities:

- Occur due to improper memory management. 
- Integer Overflow: 
    - A specific type of buffer overflow using an integer variable. 
    - Example: Vulnerability in Mozilla Firefox allowing arbitrary code execution. 

- Privilege Escalation: 
   - Attackers exploit vulnerabilities to gain administrative privileges. 



Insecure Protocols:

- Systems using protocols that exchange sensitive information in clear text. 
- Example: Remote management service accepting unencrypted credentials. 
- Solution: Apply encryption to prevent plain text logins. 


Debugging Modes:

- Servers configured with debugging modes can leak sensitive information. 
- Example: Microsoft ASP.NET package providing detailed error messages. 
- Solution: Disable debugging mode on production servers. 


Critical Skills for Cybersecurity Analysts:

- Understanding the nature of vulnerabilities. 
- Assessing vulnerabilities and developing remediation plans.

#

## Endpoint Vulnerabilities

Endpoint Configuration:

- Endpoints should be more locked down than servers.
- Common issues include missing security patches and outdated signature files for security tools.

User Behavior:

- Users often decline software updates to avoid reboots, leading to missing security patches.
- Allowing users to install their own software adds complexity and increases security risks.

Non-Computer Endpoints:

- Security updates and vulnerabilities also apply to smartphones, tablets, and other devices.

Patch Management:

- Effective endpoint patch management is crucial.
- Automatic updates can resolve many vulnerabilities.

Example of Vulnerability Scan:

- Unpatched endpoints often show numerous critical vulnerabilities, mostly due to missing Microsoft security updates.
- Enabling automatic updates can address these issues.

Key Takeaway:

- Proper care and management of endpoints are essential for maintaining good security.

#

## Network Vulnerabilities


Common Network Vulnerabilities:
- Failure to apply encryption to sensitive data.
- Misconfigurations in handling encryption.

SSL and TLS Issues:
- Outdated Protocols:
  - SSL is fundamentally broken and insecure.
  - Use at least TLS 1.2.

Insecure Cipher Suites:
- TLS provides a framework for encryption.
- Ensure servers support only secure Cipher Suites.

Digital Certificates:
- Certificates should not be expired.
- Must be signed by a reputable certificate authority.
- Must match the server names.


Example of SSL Issues:
- Untrusted SSL certificate.
- Use of self-signed certificates.
- Supporting SSL Version 2 and 3.
- Weak Cipher Suites.
- POODLE vulnerability.
- Weak hashing algorithm for certificate signing.

VPN Encryption Settings:
- Ensure VPN devices support strong encryption protocols.
- Regularly patch VPN devices and network appliances.

Domain Name Service (DNS) Vulnerabilities:
- DNS servers accepting queries from unknown outsiders.
- Patch DNS servers with recent security updates.

Interconnected Networks:
- Understand vulnerability management of interconnected networks.
- Use firewalls and protections to limit exposure.
