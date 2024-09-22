# Given a scenario, implement vulnerability scanning methods and concepts. 

# Creating a vulnerability Management Program

# What is Vulnerability Management?

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

# Identify Scan Target

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

# Scan Frequency

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
