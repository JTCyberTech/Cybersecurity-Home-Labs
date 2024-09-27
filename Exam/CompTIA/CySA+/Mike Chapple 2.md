# Given a scenario, implement vulnerability scanning methods and concepts. 

# Creating a vulnerability Management Program

## What is Vulnerability Management?

- Complexity of Modern Software: Modern software, like the Linux kernel, contains millions of lines of code, making it prone to vulnerabilities.
- Vulnerability Management Process: This involves scanning systems for vulnerabilities, applying patches, tracking remediation, and reporting results.
- Regulatory Requirements: Various regulations, such as PCI DSS and FISMA, mandate specific vulnerability management practices.

Vuln Patching Process:
- Company learns of a vuln.
- Developers analyze issue and develop a patch.
- Company release patch to customers.
- Customers apply patch to remediate vuln.

Vulnerability Management:
- Detects, remediates, report vuln

Why Manage Vulnerabilities?
- Maintain system security.
- Comply with corporate policy
- Comply with regulatory requirements

PCI DSS Requirements:
- Conduct quarterly internal and external vuln scans.
- Repeat scans after any significant change
- Use an approved scanning vendor (ASV)
- Remediate and rescan until you achieve a clean report.

FISMA Requirements:
-  Federal Information Security Management Act
-  NIST Special Publication 800-53
-  Conduct Vuln scans regularly
-  Analyze results of scans
-  Remediate legitimate vuln
-  Share info with other agencies

Industry Frameworks:
- Center for Internet Security (CIS) Benchmarks: Guide to securely config many common OS, devices, and applications.
- Open Web Application Security Project (OWASP) references: Produce industry standard that describes common web security vuln/ best practices for developing secure softwares.
- International Organization for Standardization (ISO) standards: Produces ISO 27001 standard for info security programs.

#

## Identify Scan Target

- Develop Requirements: Start by understanding the reasons behind your vulnerability management program, whether it's for security improvement, regulatory compliance, or corporate policy.
- Asset Inventory: Ensure you have a reliable asset inventory. This can come from existing asset management tools or a lightweight network scan.
- Prioritize Assets: Prioritize assets based on their importance, risk exposure, and criticality to operations. This helps in focusing your vulnerability management efforts effectively.

 Asset Inventory:
 - Provides the starting point for vuln scanning

After having Asset Inventory, need:
- Impact: What is the highest data classification handled by system that is stored, progressed, transmitted?
- Likelihood: What is the network Exposure? What service are exposed?
- Criticality: What impact does system  have on business operations?

#

## Scan Frequency

After Asset Inventory to develop a list of systems you like to scan, need to figure out how often you like to scan them.

- Regulatory and Policy Requirements: Scanning frequency may be dictated by external regulations (e.g., PCI DSS) or internal corporate policies.
- Risk Appetite: Determine how long your organization is willing to go without detecting new vulnerabilities, considering the criticality of different systems.
- Technical and Business Constraints: Factors like scanner capacity, network bandwidth, and business operations can limit how often scans can be performed.
- Continuous Monitoring: Some organizations adopt continuous monitoring for ongoing vulnerability detection, though it requires significant resources.

Regulatory and Corporate Requirements:
- May influence your scanning schedule, PCI DSS need to run scan at least quarterly.
- Consider your Org's risk appetite when designing scanning schedule.

Licensing issues:
- May limit your ability to run scans.

#

# Network Mapping

## Network Scanning

- Network Mapping: It's essential for maintaining situational awareness of systems and devices on a network, especially in large organizations.
- Tools: Nmap is the most common network mapping tool, used to scan IP addresses and identify open ports. Angry IP Scanner is another tool mentioned, though less popular.
- Purpose: Network mapping helps in detecting rogue systems and provides a glimpse of network activity, despite some systems ignoring unsolicited connection attempts.

### Angry IP Scanner

Performs Port scans form Windows Mac Linux systems.

#

## Install Nmap On Windows

- Introduction to Nmap: Nmap is a popular, open-source network mapping tool that has been around for over 20 years. It's widely used in the security and networking communities and is regularly updated.


Nmap Benefits:
- Network mapping
- Time-tested security and networking tool
- Open source package with large community
- Available for most operating systems
- Source Code freely published


Installation Process:

1. Download Nmap: Visit the Nmap homepage at nmap.org and download the latest stable release of the Microsoft Windows binary.
2. Run the Installer: Launch the downloaded file to start the installation process. Accept the license agreement.
3. Installation Options: The installer presents several components:
 - Nmap Core Files: Essential for running any scan.
 - Register Name Path: Allows execution from any directory via the command line.
 - Npcap: Required for running Nmap scans.
 - Network Performance Improvements: Optimizes system for scans.
 - Zenmap: A graphical interface for Nmap.
 - Ndiff: Compares results of two Nmap scans.
 - Ncat: Reads and writes data to network connections from the command line.
 - Nping: Enhances the basic ping command.

4. Accept Default Options: It's recommended to install the entire Nmap suite by accepting the default options.
5. Npcap Installation: A separate installation process for Npcap will start. Accept its license agreement and default options.
6. Final Steps: Complete the installation by creating desktop icons and start menu entries if preferred.

Verification: Open a command prompt and type nmap -V to verify the installation. You should see the installed version number.

#

## Run and interpret a Simple Nmap Scan

- **Nmap Scan Results:**
  - Nmap provides a list of detected ports with state information.
  - Possible port states include:
    - **Open**: Listening for incoming connections.
    - **Closed**: Accessible but no service responding.
    - **Filtered**: Firewall interfered with the scan.
    - **Unfiltered**: Accessible but state undetermined.
  - Special cases:
    - **Open|Filtered**: Either open or filtered.
    - **Closed|Filtered**: Either closed or filtered.

- **Running a Basic Nmap Scan:**
  - Example command: `nmap scanme.nmap.org`
  - Results show open ports and their associated services.

- **Using IP Address Instead of DNS Name:**
  - Example command: `nmap 45.33.32.156`
  - Results are the same as using the DNS name.

- **Interpreting Scan Results:**
  - **Port 22**: Secure Shell (SSH) protocol, likely a Linux system.
  - **Port 80**: HTTP service, indicates a web server.
  - **Ports 9929 and 31337**: Unusual ports, require further investigation.
    - **Port 9929**: Associated with nping, an Nmap-related service.
    - **Port 31337**: Commonly used in compromised systems.
   
#

## Host Discovery with Nmap

- **Host Discovery Techniques:** Nmap uses various techniques to determine if an address is active before performing a port scan.
  - **ICMP Echo Request:** Similar to the ping command, it quickly checks if an IP address is active.
  - **Connection Requests to Ports 80 and 443:** If no ICMP echo reply is received, Nmap sends requests to these commonly used ports.
  - **ICMP Timestamp Request:** Another method to probe a host if previous methods fail.

- **Local Network Scanning:** Uses ARP discovery for faster checks on the same local network.
  - **ARP Discovery:** Utilizes the address resolution protocol to check the Ethernet address of a target system.

- **Customizing Host Discovery:** You can add flags to Nmap requests to customize the host discovery process.
  - **-Pn Flag:** Skips host discovery and performs a full scan.
  - **-PS Flag:** Sends a TCP SYN request.
  - **-PA Flag:** Sends a TCP ACK request.
  - **-PU Flag:** Performs a UDP scan.
  - **-PE Flag:** Sends an ICMP echo request.
  - **-PR Flag:** Conducts an ARP scan.
 
![image](https://github.com/user-attachments/assets/3944dbaf-3d89-4b44-8ae4-4b1a629ecbcd)


- **Example Scan:** Demonstrates scanning a local network for systems running an unencrypted telnet server using the **-PS** flag.
  - **Results Analysis:** Shows six active hosts, with only one having port 23 open (telnet).

- **Important Note:** Even if a specific port is used for host discovery, Nmap will scan all ports once a system is identified.

#

## Operate Systema Fingerprinting

- **Introduction to Nmap’s Operating System Detection:**
  - Nmap can perform fingerprinting of target systems to guess the operating system.
  - This is done by analyzing responses from various probes sent to the targets.

- **Activating OS Detection:**
  - Use the `-O` flag to activate operating system detection in Nmap.
  - Example command: `nmap -O scanme.nmap.org`.

- **Root Privileges Requirement:**
  - OS detection requires root privileges.
  - Use `sudo -i` to enter interactive mode with administrative privileges.

- **Example Scans:**
  - **Remote Scan:** Scanning `scanme.nmap.org` showed multiple Linux versions due to long network distance (16 hops).
  - **Local Scan:** Scanning a local network device identified an iPhone by its open port (62078).
  - **Another Local Scan:** Identified a device running Google Android 5.1, specifically an Amazon Echo speaker.
  - **Final Local Scan:** Identified a MacBook Air running Mac OS 10.11 (El Capitan) or iOS 12.4-13.0.

- **Accuracy and Limitations:**
  - OS detection is generally accurate but results should be taken with a grain of salt.
  - Works better on local networks compared to long-distance scans.

#

## Service Version Detection

Service Version Detection:
- Guesseds the service version running on open port.
- Activate service version detection with `-sV` flag.

#

# Configuring and Executing Vulnerability Scans

## Security baseline Scanning

Security baseline Scanning provides a picture of current state of your security environment.
- Understanding current state providdes realistic view of current level of risk facing the Org
- Understanding the state of the Org's security provides us with measurement stick we can use to evaluate our progress.

Use Baseline scans to identify the highest priorities for remediations.
- Compare future scans to baseline to meawsure progress.

#

## Scan Configuration

**Setting Up a New Scan:**
- Click the "New Scan" button in Nessus.
- Choose from a series of templates or select "advanced scan" for custom settings.
- Enter basic information like the scan name (e.g., "Mike's Scan") and targets (e.g., IP addresses or network ranges).

**Configuring Scan Scope:**
- Enter system names, IP addresses, or network ranges in the targets box.
- Option to upload a file with a list of systems from an asset management tool.

**Organizing Scans:**
- Create a series of scans based on data sensitivity (e.g., confidential, sensitive, highly sensitive).
- Set different schedules for each system group.

**Scheduling and Notifications:**
- Configure the scan to run at specific intervals (e.g., daily).
- Set up email notifications to receive scan reports.

**Discovery Options:**
- Configure network pings to determine if a system is alive.
- Handle devices like printers and network systems that might react negatively to scans.

**Port Scanning:**
- Set specific network ports and protocols for scanning.
- Default settings include commonly used ports, but custom ports can be configured.

**Assessment Settings:**
- Set scan sensitivity level (e.g., normal accuracy to balance false alarms and real vulnerabilities).
- Option to override normal accuracy for more detailed reporting.

**Advanced Settings:**
- Enable safe checks to avoid disrupting systems in a production environment.
- Adjust performance settings to stop scanning unresponsive hosts and slow down scans during network congestion.

**Plugins Tab:**
- Nessus uses plugins to perform vulnerability checks.
- Customize the scan by enabling or disabling plugins based on the types of systems in the network (e.g., disable AIX, Cisco, Debian Linux plugins if not relevant).

**Performance Optimization:**
- Disabling irrelevant plugins improves scan performance by reducing scan time.
- Create custom templates for reusable scan settings.

#

## Scan Perspective

**Importance of Scan Perspective:**
- The scanner’s location on the network relative to the systems being scanned is crucial.

**Different Network Locations:**

- **DMZ (Demilitarized Zone):**
  - Scanner in the DMZ has unrestricted access to the web server.
  - Provides the clearest picture of vulnerabilities as it bypasses the firewall.

- **Internal Network:**
  - Scanner’s traffic must pass through the firewall.
  - Firewall may drop connection attempts and filter traffic, potentially missing some vulnerabilities.

- **Internet:**
  - Scanner’s traffic is subject to strict firewall rules for inbound traffic.
  - Provides the attacker's view, showing vulnerabilities visible from outside.

**Server-Based vs. Agent-Based Scans:**

- **Server-Based Scans:**
  - Scanner reaches out over the network to probe systems.

- **Agent-Based Scans:**
  - Security agent installed on each server probes deeply into configurations.
  - Reports vulnerabilities back to the central management system.
  - Some organizations avoid this due to increased complexity.

**Credentialed Scanning:**
- Scanner uses provided credentials to log onto remote systems.
- Allows for deeper inspection without installing agents.
- Important to use read-only accounts to avoid unintended changes.

**Best Practices:**
- Mix different perspectives in scanning to get a comprehensive view.
- Use DMZ for detailed vulnerability insights.
- Use internet perspective for understanding external threats.
- Consider agent-based or credentialed scanning for deeper insights.

#

## Scanner Maintenance

- Scan Engine Updates: Software updates to the scanner itself that fix bugs and add new features
- Plugin Updates: Vuln feed updates that provide the scanner with information about current vulnerabilities.


**Regular Updates:**
- Vulnerability scanners require regular updates to maintain effectiveness.
- There are two types of updates: scanner engine updates (infrequent) and vulnerability feed updates (frequent).

**Configuring Updates in Nessus:**
- Navigate to the settings option in Nessus to view and configure updates.
- You can see the current version of the scan engine and the last update time for plugins.
- Options to configure automatic updates for both the scan engine and plugins.
- Update frequency can be set (e.g., daily) and an update server can be specified.

**User Permissions:**
- Managing user permissions on the scanner is crucial.
- Configure user accounts and set permissions, such as read-only access or limiting scan capabilities.
- Adjust permissions based on the specific needs of your environment.

**Practical Example:**
- The video demonstrates how to configure Nessus to automatically update itself daily.
- Shows how to manage user permissions and configure user accounts in Nessus.

#

## Vulnerability Scanning Tools

- Greenbone OpenVAS: Open source alternative to Nessus for people who does not have budget for commerical scanner.
- Arachni: open source tool that performs web application security tests
- Nikto: open source alternative

Basically:
- Neesus and OpenVAS: General purpose vulnerability scanners.
- arachni and Nikto: Open Source web app vulnerability scanners.

#

## Passive Vulnerability Scanning 

###Active Scanning:

- Probes systems for issues

Active Scawnning Drawbacks:
- Can be detected by admins
- May accidentally exploit vulnerabilities
- Will miss some vuln due to firewall settings, network segmentation, IPS deployments.

### Passive Scanning

- Observes network traffic

Passive scanning supplements, rather than replaces active scanning.

#

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

- Insecure Cipher Suites:
  - TLS provides a framework for encryption.
  - Ensure servers support only secure Cipher Suites.

- Digital Certificates:
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

#

# Software Security Issues

## OWASP Top 10 

- **OWASP Top 10 Overview**
  - The OWASP Top 10 is a list of the top web security vulnerabilities.
  - The current version was developed in 2021.

- **Top 10 Web Application Security Issues:**

  1. **Broken Access Controls** - Allows Unauthorized Access
     - Occurs when developers fail to check backend authorization.
     - Includes insecure direct object references.

  2. **Cryptographic Failures** - Allows Access to Sensitive Data
     - Exposure of sensitive information due to poorly configured cryptography.
     - Examples: Unencrypted customer files, failure to implement HTTPS.

  3. **Injection Vulnerabilities** - Insert Unwanted code
     - Attackers insert code into a request, tricking the website to execute it.
     - Common example: SQL injection attacks.

  4. **Insecure Design** - Fails to meet security requirements
     - Security issues from the initial creation of code.
     - Includes insufficient threat modeling and failure to follow best practices.

  5. **Security Misconfiguration** - Occurs in many possiblew locations
     - Errors in the security settings of web servers, application servers, etc.
     - Requires regular monitoring and patching of components.

  6. **Vulnerable and Outdated Components** - Can jeopardize Application Security
     - Use of components with known vulnerabilities.
     - Administrators must apply security patches promptly.

  7. **Identification and Authentication Failures** - Exploit Session management
     - Flaws in the mechanisms that provide user authentication.
     - Example: Session hijacking.

  8. **Software and Data Integrity Failures** - Allows insertion of insecure code
     - Lack of appropriate verification checks in the software pipeline.
     - Can lead to corrupted or malicious updates.

  9. **Security Logging and Monitoring Failures** - Can deprive analyst of needed data
     - Applications failing to create detailed log records.
     - Crucial for security investigations and troubleshooting.

  10. **Server-Side Request Forgery (SSRF)** - Tricks servers into requesting URLs
      - Attackers trick web servers into retrieving unvalidated URLs.

- **Additional Resources:**
  - SANS Institute: Top 25 Most Dangerous Software Errors.
  - Center for Internet Security’s system design recommendations and security benchmarks.
 
#

## Prevent SQLi

SQL Injection Attacks:
- Exploit the reliance of dynamic web applications on underlying databases.
  - Example: A web application retrieves unencrypted user passwords from a database for authentication.
- SQL (Structured Query Language) is used by relational databases to create, update, delete, and retrieve data.

How SQL Injection Works:
- A web application sends a SQL query to the database to retrieve a user's password.

- Example Query:
```sql SELECT username, password FROM users WHERE username = 'mchapple'; ```

- An attacker can alter the query by entering malicious input in the username field.

**Malicious Input Example:**

```mchapple'; DROP TABLE users; --```

- This input sends two separate SQL commands and a comment to the database:
  - Retrieve the password.
  - Change the password stored in the database.
 
Defense Techniques:

- Input Validation:
  - Ensure user input is in an appropriate format.
  - Example: Input should never contain a single quote.
  - Always perform validation on the server side to prevent attackers from bypassing checks.

- Parameterized Queries:
  - Use stored procedures where SQL statements are stored on the server in a pre-compiled format.
  - Input is plugged in after the SQL is already processed, preventing SQL injection attacks.

Key Takeaways:
- SQL injection attacks exploit database queries to manipulate data.
- Input validation and parameterized queries are effective techniques to prevent these attacks.

#

## Understand Cross-site Scripting

Definition of Cross-Site Scripting (XSS):
- XSS attacks trick a user's web browser into executing a malicious script.
- The attack can be stored on a site and executed when a victim visits the page.
- When victim visit the site, victim's browser unknowingly downaloads and runs the code.

Conditions for XSS Attacks:
- The website must have reflected or stored input.
  - There must be opportunity where attackers can provide text to site that will be displayed to other users.
- The input must be unvalidated, allowing the attacker to embed script commands.

Common Scenarios:
- Reflected input often occurs on message boards, user profiles, and other content submission areas.
- Attackers can slip in scripting tags that execute when viewed by another user.

Solution to XSS Attacks:
- Input Validation: Ensuring that user input is safe and does not include scripting tags.
- HTML Tags: Understanding how HTML tags work ```(e.g., <b>, <i>, <a>, <script>).```
- Legitimate Use of Scripts: Scripts are legitimate when written by the website creator but can be malicious if injected by an attacker.

Types of XSS Attacks:
- Stored (Persistent) XSS: Attack code is stored on a remote server and executed when a victim accesses it.
- Reflected XSS: Attack code is included in a link, executed immediately when the link is clicked.

Example Scenario:
- An online auction site allowing HTML in listings can be exploited if it doesn't validate input, leading to malicious scripts running in users' browsers.

#

## Request Forgery

Terminology:
- Cross-site request forgery (CSRF) is also known as XSRF or Sea surf.

Attack Mechanism:
- CSRF attacks exploit the fact that users often have multiple sites open and authenticated sessions persist across tabs
- Attackers trick a user's browser into sending unauthorized requests to another site without the user's knowledge.

Example Scenario:
- If a user is logged into multiple sites (e.g., LinkedIn, Wikipedia, Bank of America), an attacker can use one site to make unauthorized requests to another.
- This can be done by embedding a fake image tag in a webpage that executes a command, such as transferring funds from the user's account to the attacker's account.

Defense Mechanisms:
- Use cryptographically strong tokens in each exchange between authenticated users and the website.
- Avoid using HTTP GET requests for actions that can change the state of the server.
- Advise users to log out after using a site and implement automatic logouts after a short idle period.

Server-Side Request Forgery (SSRF):
- SSRF is a variant that targets the server, tricking it into retrieving malicious commands or destinations from what it believes is a trusted source.

#

## Privilege Escalation

Gain Admin Access

- Definition: Privilege escalation attacks transform normal user accounts into accounts with administrative rights.
- Risks: These attacks are particularly dangerous on systems with external exposures, allowing internet-based control of a server.
- Common Causes: Often arise from buffer overflow issues or other security vulnerabilities in code that allow arbitrary code execution.

Mitigation Strategies:
- Input Validation: Perform strict input validation to ensure inputs are in the expected format and length.
- System Updates: Ensure operating systems, platforms, and applications are current and have the latest security patches.
- Principle of Least Privilege: Service accounts should have the minimum privileges necessary for code execution.
- Preventive Controls: Use data execution prevention and address space layout randomization technologies to prevent privilege escalation attacks.





# Exam Note:

- Normally the frequency of scanning won't affect the cost of those scans. The organization has normally already made an investment in the scanning technology.
- The operating system is not necessarily a major factor in deciding whether a device should be scanned.
- Sales team requests are not a common source of requirements for developing a vulnerability management program.
- The Nmap -sV flag performs scans with service version detection and version information.
- Nmap requires root privileges to run OS detection.
- There is no ICMP reply request. There is an ICMP echo reply that is used to test for connectivity issues.
- Nmap scans a network to determine what hosts and services are running.
- The filtered port state is the result of Nmap being unable to find out if a port is open or closed due to a filter or a port block.
- On macOS, the Privacy & Security preferences can be set to allow applications to be downloaded from identified developers.
- Zenmap is a GUI for nmap.
- Snort is an intrusion detection and prevention system, not a vulnerability scanner.
- The vulnerability scanner uses the feed to learn about new vulnerabilities, and those should be updated at least daily.
- Placing the scanner on the screened subnet provides the most complete picture of vulnerabilities present on a public web server.
- The plug-ins settings in vulnerability scanners should be modified to limit the tests performed by vulnerability scanners to only those that affect the installed OS.
- Passive vulnerability scanners do not probe. They monitor the network and report on outdated OS and applications.
- Nikto is a web vulnerability scanner and does not perform general purpose vulnerability scans.

## Software Security Isues

Which of these is not a basic mitigation strategy to reduce the likelihood of successful privilege escalation attacks? 
- Fail-open: a protection strategy where a device does not perform any security filtering when it fails. This is not a strategy to prevent privilege escalation attacks.

Which of these is an ineffective defense against client-side XSRF attacks?
- Network segmentation: in physical form means each segment is isolated from other network segments, and in virtual form means VLANs are used to logically separate the network into functional subnets. However, network segmentation is ineffective against client-side XSRF attacks, which are on-path browser-based attacks on individual hosts with multiple browser tabs opened and logged into and with authentications crossing over browser tabs.

Which one of these tools is not an interception proxy?
- RStudio is an integrated development Environment (IDE) for the R interpretive language for statistical analysis.






