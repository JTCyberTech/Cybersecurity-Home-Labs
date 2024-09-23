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
