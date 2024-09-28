# More Cybersecurity Tools

## Exploitation Frameworks

- **Exploitation Frameworks Overview:**
  - Security professionals use exploitation frameworks to test vulnerabilities using the same tools as attackers.
  - Metasploit is the most common exploitation framework, functioning like a hacker's Swiss Army Knife with modular plugins.

- **Metasploit Versions:**
  - **Metasploit Framework Edition:** Free and open-source.
  - **Metasploit Pro Edition:** Commercial product with additional features.
  - Feature comparison available on the Metasploit website.

- **Using Metasploit:**
  - Available for both Windows and Linux systems.
  - Accessed via a web browser.
  - Steps to create a new project and restrict network range to prevent unauthorized access.

- **Metasploit Console Sections:**
  - **Discovery:** Run scans (e.g., using Nmap).
  - **Penetration:** Execute exploits.
  - **Evidence Collection and Cleanup:** Gather information and restore systems.

- **Example Workflow:**
  - Importing a pre-run Nmap scan.
  - Identifying hosts and services (e.g., SSH on port 22).
  - Using modules to search for vulnerabilities (e.g., SSH username enumeration).

- **Practical Application:**
  - Example of finding a valid username (e.g., "Mike") for potential brute force password attacks.

- **Importance of Controls:**
  - Restricting Metasploit to specific network ranges to avoid unauthorized testing.

#

## Cloud Auditing Tools

- **Scout Suite:**
  - Multi-cloud auditing tool.
  - Uses APIs to run security assessments on cloud provider accounts.
  - Supports AWS, Microsoft Azure, Google Compute Platform, Alibaba Cloud, and Oracle Cloud Infrastructure.
  - Runs as a Python script.
  - Generates reports indicating the level of concern with green checks, yellow exclamation points, or red exclamation points.
  - Useful for penetration tests or security assessments.

- **Pacu:**
  - Exploitation framework for AWS.
  - Designed for attackers to determine actions with hijacked AWS accounts.
  - Follows the Metasploit paradigm with modular exploits.
  - Capable of reconnaissance, enumeration, escalation, lateral moves, and various exploit techniques.
  - Includes techniques to avoid security detection.

- **Prowler:**
  - Security assessment tool focused specifically on AWS.
  - Runs as a command-line tool.
  - Provides a checklist of security findings to investigate.
  - Highlights issues like password policies and multifactor authentication settings.
  - Helps remediate cloud environment security.

#

## Debuggers

- **Role of Debuggers:**
  - Debuggers support developers in troubleshooting their work.
  - They allow testers to perform dynamic analysis of executable files.

- **Common Debugging Tools:**
  - **Immunity Debugger:**
    - Designed specifically for penetration testing.
    - Useful for reverse engineering malware.
  - **GNU Debugger (GDB):**
    - Widely used open-source debugger for Linux.
    - Supports a variety of programming languages.

- **Decompilation Process:**
  - Penetration testers may use debuggers to decompile code.
  - This process converts executable files back into source code.
  - Decompilation is quite difficult and rarely successful.

#

## Open-Source Reconnaissance

- **Maltego:**
  - Open-source tool for intelligence gathering.
  - Connects data points through a graphical user interface.
  - Helps understand and document correlations and hierarchies.
  - Uses "transforms" to provide additional data or processing about objects and entities.

- **Recon-ng:**
  - Module-based reconnaissance tool.
  - Uses a command line interface built into Kali Linux.
  - Provides access to a marketplace of plugin modules for specific tools.
  - Example modules:
    - Interface to Shodan open-source intelligence search engine.
    - Interface to Nmap for active information gathering.

#

## Control Frameworks

- **Purpose of Control Frameworks:**
  - Assist in designing, implementing, and managing security controls.
  - Ensure comprehensive coverage of risks and protection of confidentiality, integrity, and availability.

- **Common Control Frameworks:**
  - **COBIT:**
    - Developed by the Information Systems Audit and Control Association.
    - Focuses on linking business goals with information security functions.
    - Covers six principles: stakeholder needs, holistic approach, dynamic governance, separating governance from management, tailoring to enterprise needs, and end-to-end coverage.
    - Includes implementation guidance.

  - **ISO Standards:**
    - **ISO 27001:** Covers information security management systems with generalized control objectives.
    - **ISO 27002:** Provides specific controls to achieve security goals.
    - **ISO 27701:** Focuses on privacy management.
    - **ISO 31000:** Provides guidance for risk management programs.

  - **NIST Standards:**
    - **NIST Special Publication 800-53:**
      - Mandatory for federal agencies but used by other organizations.
      - Over 400 pages covering multi-tiered risk management, security control structures, and more.
    - **NIST Cybersecurity Framework:**
      - Free to use, provides a common language for managing cybersecurity risks.
      - Divided into five functions: identify, protect, detect, respond, and recover.
      - Each function is broken into categories and subcategories with detailed references.

- **Framework Benefits:**
  - Provide a structured approach to building security programs.
  - Help organizations identify and prioritize actions to reduce cybersecurity risk.
  - Facilitate productive conversations with external partners like auditors and government agencies.

#

# Software Developement Lifecycle

## Software Platformsw

- **Software Execution Environment:**
  - Software runs within a platform that hosts the operating system.
  - The platform is a crucial component of the software security environment.

- **Basic Software Execution:**
  - Simple endpoint devices run software entirely on a desktop or laptop without interacting with other systems.
  - Example: Running the calculator application on a laptop.

- **Client/Server Environment:**
  - Most business applications operate in a client/server model.
  - The endpoint acts as the client, interacting with software on a server.
  - Example: Using Microsoft Excel linked to a database server.

- **Web Applications:**
  - End users run web browsers as clients on their devices.
  - Web browsers interact with web servers globally to gather information.

- **Mobile Endpoints:**
  - Mobile devices run their own operating systems (iOS, Android).
  - Applications on mobile devices can be simple endpoint applications or use a client/server model.

- **Specialized Endpoint Devices:**
  - Includes embedded devices and systems on a chip for vehicles, industrial control systems, and IoT applications.
  - These devices often store software applications in firmware for quick access.

#

## Developement Methodologies

- **Requirements Definition:**
  - Crucial for developing software that meets business needs.
  - Developers work with customers to outline specific purposes and business goals.

- **Waterfall Model:**
  - Developed by Winston Royce in the 1970s.
  - Linear process with rigid steps: system requirements, software requirements, preliminary design, detailed design, coding and debugging, testing, operations, and maintenance.
  - Limited flexibility for changes during development.

- **Spiral Model:**
  - Introduced by Barry Boehm in the 1980s.
  - Iterative process with four phases: requirements, design, build, and evaluation.
  - Developers move through phases multiple times until the product is satisfactory.

- **Agile Approach:**
  - Focuses on rapid development and flexibility.
  - Values individuals and interactions, working software, customer collaboration, and responding to change.
  - Principles include early and continuous delivery, welcoming changing requirements, frequent delivery of working software, and collaboration between business people and developers.

- **Agile Manifesto Principles:**
  - Satisfy the customer through early and continuous delivery.
  - Welcome changing requirements, even late in development.
  - Deliver working software frequently.
  - Promote sustainable development and simplicity.
  - Encourage self-organizing teams and regular reflection for improvement.


#

## Maturity Models

- **Purpose of Maturity Models:**
  - Evaluate organizations against a standard benchmark.
  - Identify next steps in evolving software development practices.

- **Capability Maturity Model Integrated (CMMI):**
  - Developed by Carnegie Mellon University.
  - Consists of five levels: Initial, Managed, Defined, Quantitatively Managed, and Optimizing.
  - Broader application beyond software development, including product development, supply chain management, acquisition, and service delivery.

- **CMMI Levels:**
  - **Level 1: Initial:**
    - Just starting with formal development practices.
    - Commonly experiences delays and budget overruns.

  - **Level 2: Managed:**
    - Basic processes in place, such as code reuse.
    - Key activities: configuration management, measurement and analysis, project monitoring and control, project planning, process and product quality assurance, requirements management, supplier agreement management.

  - **Level 3: Defined:**
    - Formal documented practices for many process areas.
    - Activities: decision analysis and resolution, integrated project management, organizational process definition, organizational training, organizational process focus, product integration, requirements development, risk management, technical solution, validation, and verification.

  - **Level 4: Quantitatively Managed:**
    - Use of quantitative measures to evaluate progress.
    - Activities: organizational process performance, quantitative project management.

  - **Level 5: Optimizing:**
    - Continuous process improvement.
    - Practices: causal analysis and resolution, organizational performance management.

- **Alternative Models:**
  - **IDEAL Model:**
    - Five phases: Initiating, Diagnosing, Establishing, Action, Learning.
    - Focuses on the process an organization follows to improve itself.

- **Key Takeaway:**
  - Maturity models guide the improvement of software development practices, leading to better security.
  - IMDQO

#

## Change Management

- **Operations and Maintenance Phase:** After software development, it enters a phase where it requires ongoing maintenance and operations.

- **Standardized Change Management:** Essential to avoid disruptions and control code flow to production.

- **Three Key Elements:**
  - **Request Control:** Customers request modifications; managers evaluate and prioritize these requests.
  - **Change Control:** Developers or managers write a Request for Change (RFC) and submit it for review. Approved changes are documented.
  - **Release Control:** Quality assurance tests the code, and a release manager moves it to production.

- **Development Environments:**
  - **Development Environment:** Where developers create and modify code.
  - **Test Environment:** Code is tested here.
  - **Staging Environment:** Prepares code for production.
  - **Production Environment:** Code is released for general use.

- **Configuration Management:** Ensures all updates are tested, approved, and have rollback plans.

- **Scheduled Changes:** Critical system changes are scheduled in advance to minimize disruption.

#

# Secure Coding Practices

## Input Validation 

- **User Input Vulnerability:** Any application accepting user input is susceptible to exploitation.

- **Types of Attacks:** User input can contain code for attacks like SQL injection and cross-site scripting.

- **Input Validation Importance:** Essential for protecting against input-based attacks by filtering user input to ensure it doesn't contain malicious or unexpected values.

- **Two Approaches to Input Validation:**
  - **Approved List (Whitelisting):**
    - Specifies exact allowed input types.
    - Example: Ensuring a year of birth is a four-digit number within a reasonable range.
  
  - **Unapproved List (Blacklisting):**
    - Specifies input types that are not allowed.
    - Example: Prohibiting HTML tags to prevent cross-site scripting or SQL keywords to prevent injection attacks.

- **Effectiveness:**
  - Approved list is more powerful but not always practical.
  - Unapproved list is more flexible but less effective as it’s hard to describe all malicious input types.

- **Server-Side Validation:** Critical to perform input validation on the server, not in the client’s browser, to prevent users from bypassing the validation.

#

## Parameterized Queries 

- **Definition and Purpose:**
  - Parameterized queries protect applications against SQL injection attacks by preventing direct SQL code from being sent to the database server.
  - They improve database performance by using pre-compiled query templates.

- **How It Works:**
  - The client sends arguments to the server, which inserts them into a pre-compiled query template.
  - This method ensures that user input cannot alter the underlying SQL statement.

- **Example Demonstration:**
  - The instructor uses Azure Data Studio to access a SQL server database.
  - A table called "Customers" is queried to show all customers in Texas.
  - The query is written as: `SELECT * FROM Customers WHERE State = 'Texas'`.

- **Stored Procedure Creation:**
  - A stored procedure named `spCustomerState` is created to handle the query.
  - The procedure takes one argument, `State`, which is a text argument.
  - The query template is modified to use the `@state` argument instead of hardcoding the state value.

- **Execution of Stored Procedure:**
  - The stored procedure is executed using the `EXEC` command with the state argument.
  - Examples include retrieving customers from Texas, California, and New Jersey.

- **Benefits:**
  - Protects against SQL injection attacks as the stored procedure is pre-compiled.
  - Provides flexibility to change the input without altering the query structure.

#

## Authentication and Session Mangement Issues

- **Password Storage:**
  - Never store user passwords in plain text.
  - Store passwords in hashed and salted form to prevent theft.
  - Hashing transforms passwords into irreversible values.
  - Salting adds a random value to passwords before hashing to protect against rainbow table attacks.

- **Password Encryption in Transit:**
  - Ensure passwords are encrypted during transmission to prevent eavesdropping.
  - Use Transport Layer Security (TLS) to encrypt the entire web session.
  - TLS protects session contents, including user passwords and HTTP headers.

- **Session Cookies:**
  - Protect HTTP headers containing session cookies to avoid session replay attacks.


#

## Output Encoding

- **Definition and Importance:**
  - Output encoding protects applications from potentially malicious input, such as SQL injection and cross-site scripting attacks.
  - It replaces dangerous characters with equivalent strings that are safe for the application but produce the same result for the end user.

- **Types of Encoding:**
  - **HTML Encoding:** Uses ampersand notation for encoding values in web documents.
  - **URL Encoding:** Uses percent sign notation for encoding values in web addresses.

- **Commonly Encoded Values:**
  - Less than symbol (`<`): HTML encoded as `&lt;`, URL encoded as `%3C`.
  - Greater than symbol (`>`): HTML encoded as `&gt;`, URL encoded as `%3E`.
  - Single quotation mark (`'`): HTML encoded as `&apos;`, URL encoded as `%27`.
  - Double quotation mark (`"`): HTML encoded as `&quot;`, URL encoded as `%28`.
  - Forward slash (`/`): HTML encoded as `&#x2F;`, URL encoded as `%2F`.
  - Ampersand (`&`): HTML encoded as `&amp;`, URL encoded as `%26`.
  - Percent sign (`%`): HTML encoded as `&#x25;`, URL encoded as `%25`.

- **Best Practices:**
  - Do not attempt to perform encoding manually due to the complexity and number of values that need protection.
  - Use a secure, trusted encoding library to automatically validate and encode all potentially dangerous values.

- **Example Demonstration:**
  - The video demonstrates output encoding using the Bing search engine to show how an SQL injection attempt is encoded in the URL.
  - The single quote character in the SQL injection attempt is re-encoded as `%27`.

- **Key Takeaway:**
  - Encoding is crucial for protecting web applications from malicious inputs. Always use a trusted library for encoding to ensure comprehensive protection.

#

## Error and Exception Handling

- **Importance of Error Handling:**
  - Prevents software from entering unpredictable states due to invalid user input or errors.
  - Critical for maintaining software security and preventing vulnerabilities like buffer overflows.

- **State Transition Model:**
  - **Example:** A simple program calculating sales tax has three states: awaiting input, calculating tax, and displaying output.
  - Unpredictable states occur when unexpected input (e.g., a word instead of a number) is received.

- **Exception Handling:**
  - Provides explicit instructions for handling errors, preventing unpredictable states.
  - **Example:** Modifying software to display an error message for invalid input.

- **Implementation in Java:**
  - Uses the Try-Catch model.
  - **Example:** Handling division by zero errors by enclosing the division statement in a try clause and using a catch clause to report errors.

- **Best Practices:**
  - Think through potential errors in your code.
  - Provide explicit instructions for handling those errors to write more secure code.

#

## Code Signing

- **Purpose of Code Signing:**
  - Demonstrates that applications come from a legitimate source.
  - Uses digital signatures to provide non-repudiation.

- **Process of Code Signing:**
  - Developers obtain a digital certificate from a trusted certificate authority.
  - Use the private key associated with the digital certificate to create a digital signature.
  - Release the signed code to users.

- **Validation by Operating System:**
  - The OS checks if the public key in the developer's digital certificate correctly decrypts the digital signature.
  - Verifies that the hash in the digital signature matches the downloaded code.
  - Ensures the code has not been tampered with.

- **Trust Verification:**
  - The OS checks if it trusts the developer who signed the code.
  - **Example:** A warning message appears if the code is not digitally signed, indicating the developer cannot be verified.

- **Benefits of Code Signing:**
  - Shows that the code originated from the developer and was not tampered with.
  - Helps users determine which software they can trust.

#

## Database Security

- **Importance of Database Security:**
  - Databases contain sensitive and critical business information.
  - Security professionals must collaborate with database administrators to protect data against confidentiality, integrity, and availability threats.

- **Database Normalization:**
  - Normalization improves database design and has security advantages.
  - **First Normal Form:** Separate tables for different sets of related data, primary key for each table, no multivalued fields, uniform number of fields in records.
  - **Second Normal Form:** Includes first normal form requirements; non-primary key fields must be facts about the entire primary key.
  - **Third Normal Form:** Includes first and second normal form requirements; restricts relationships between non-key fields.

- **Encryption:**
  - Strong encryption should protect sensitive data at rest in databases.
  - Prevents unauthorized access to sensitive information even if the database is accessed.

- **Obfuscation and Camouflage:**
  - Avoid obvious naming conventions for sensitive databases (e.g., avoid names like "credit card database").
  - Use strategic naming to not directly point attackers to sensitive information.

- **Database Activity Monitoring (DAM):**
  - Monitors all database requests, especially by administrative users.
  - Flags suspicious activity for review or intervention.

- **Stored Procedures:**
  - Store query text on the database server, allowing applications to provide arguments instead of the entire SQL command.
  - Effective control against SQL injection attacks.


#

## Data De-identification

- **Definition of De-identification:**
  - Process of removing identifying information from data sets when not needed for business requirements.

- **Examples of Identifiers to Remove:**
  - Names, Social Security numbers, and other obvious identifiers.

- **Challenges with Simple De-identification:**
  - Combining innocuous fields (e.g., zip code, date of birth, gender) can still uniquely identify individuals.
  - Carnegie Mellon study: 87% of people in the U.S. can be uniquely identified using these three fields together.

- **Need for Anonymization:**
  - Beyond de-identification, data should be anonymized to prevent identification of individuals.
  - HIPAA standards provide a rigorous process for anonymizing data.

- **HIPAA Anonymization Methods:**
  - **Statistical Analysis:** Statisticians validate that the data set is unlikely to disclose individual identities.
  - **Safe Harbor Approach:** Eliminates 18 data elements that might reveal an individual's identity (e.g., Social Security numbers, email addresses, date of birth, zip code).

- **Key Takeaway:**
  - Carefully consider and implement appropriate steps for data de-identification and anonymization to protect privacy.

#

## Data Obfuscation

- **Data Obfuscation Definition:**
  - Transforming data into a format where the original information can't be retrieved.

- **Hash Functions:**
  - One-way functions used to transform data values into hash values.
  - **Major flaw:** Vulnerable to Rainbow Table Attacks where attackers use precomputed hash values to identify original data.

- **Salting:**
  - Combines text with a randomly chosen value before hashing.
  - Increases security by making pre-computation of hashes impossible, preventing Rainbow Table Attacks.

- **Tokenization:**
  - Replaces sensitive values with unique identifiers using a lookup table.
  - **Example:** Replacing student IDs with randomly generated numbers.
  - Important to keep the lookup table secure.

- **Masking:**
  - Redacts sensitive information by replacing it with blank values.
  - **Example:** Masking Social Security numbers with Xs.

#

# Software Quality Assurance

## Software Testing

- **Model Validation and Verification:**
  - **Model Validation:** Ensures the software meets original business requirements. Answers the question, "Are we building the right software?"
  - **Software Verification:** Conducted throughout development to ensure the software functions correctly. Answers the question, "Are we building the software right?"

- **Stress/Load Testing:**
  - Simulates real-world activity on the system to ensure it can handle maximum expected load.
  - Tests continue increasing load until system failure to determine maximum capacity.

- **User Acceptance Testing (UAT):**
  - Final phase of testing where end users evaluate the software in a testing environment.
  - Focuses on usability and ensures the software is intuitive for end users.
  - Often referred to as beta testing.

- **Regression Testing:**
  - Conducted before releasing modifications to verify changes don't have unintended side effects.
  - Uses sets of inputs to compare the original system and modified code to ensure consistent behavior.

#

## Code Security Tests

- **Code Security Tests:**
  - Move beyond functional requirements to check for security flaws.
  - Complement code reviews by using technology to assist in code inspection.

- **Types of Code Testing:**
  - **Static Tests:**
    - Use specialized software to examine code for common defects without executing it.
    - Automated equivalent of a code review.
  - **Dynamic Tests:**
    - Execute the code, supply inputs, and verify outputs.
    - Closest to real-world operations, providing confidence in software functionality.

- **Synthetic Transactions:**
  - Scripted sets of inputs and instructions with known expected outputs.
  - Used in dynamic tests for regression testing to verify code functionality across various tests.

- **Importance of Multiple Testing Methods:**
  - Static tests identify defects not covered by synthetic transactions.
  - Dynamic tests find defects in functionality that static tests can't foresee.
  - Code reviews by skilled developers can catch deficiencies missed by automated tests.

#

## Fuzzing

- **Definition of Fuzzing:**
  - Fuzz testing, or fuzzing, is a software testing technique that provides various valid and invalid inputs to software to make it enter unpredictable states or disclose confidential information.

- **Types of Fuzzing:**
  - **Generation Fuzzing:** Generates input values from a specification.
  - **Mutation Fuzzing:** Analyzes real input and modifies those values.

- **Example Tool:**
  - **Zed Application Proxy (ZAP)** from OWASP is used for fuzz testing.
  - Demonstration involves using ZAP to visit Wikipedia, spider the site, and perform fuzz testing on an API page.

- **Steps in the Example:**
  1. **Spidering the Website:** ZAP discovers URLs on Wikipedia.
  2. **Selecting a Target:** Chooses `api.php` page and examines the request.
  3. **Fuzz Testing:** Highlights a parameter (`action=mobileview`), adds various payloads (e.g., `fullview`, `desktopview`, `admin`), and runs the fuzzer.
  4. **Results:** ZAP sends multiple requests with different inputs and displays the responses.

- **Important Notes:**
  - Fuzz testing can be seen as an offensive hacking technique; only perform with permission from the application owner.
  - Fuzz testing automates testing variations to see how software responds, aiming to identify security vulnerabilities.

# 

## Reverse Engineering Software

- **Reverse Engineering Purpose:** Reverse engineering aims to uncover how software functions by working backward from the end product.

- **Software Development:** Software is created using various programming languages like Python, Ruby, Java, R, C++, etc.

- **Source Code:** The code written by developers is known as source code and is somewhat readable by humans.

- **Interpreted vs. Compiled Languages:**
  - **Interpreted Languages:** Languages like R, Python, and Ruby use an interpreter to convert source code into machine language during execution.
  - **Compiled Languages:** Languages like C, C++, and Java are compiled into binary code (executable files) before execution.

- **Reverse Engineering Techniques:**
  - **Interpreted Languages:** Easier to reverse engineer as you can view the source code directly.
  - **Compiled Languages:** More challenging as you only have the binary executable file.
    - **Sandbox Environment:** Run the software in an isolated, instrumented environment to observe its behavior.
    - **Decompiler:** Use specialized software to convert binary code back into source code, though this is often difficult and inaccurate.

- **Software Integrity Verification:**
  - **Fingerprinting:** Uses cryptographic hashes to verify if software has been tampered with.
  - **Hashing Function:** Create a fingerprint of known good software and store it securely. Later, recompute the hash to check for changes.
  - **File Integrity Monitoring:** Tools like Tripwire use this principle to ensure software integrity.

#

## Reverse Engineering Hardware

- **Reverse engineering hardware** requires advanced skills and sophisticated equipment.
  - The logic controlling hardware is embedded in integrated circuits and firmware, making it difficult to analyze without specialized instruments.

- **Common use case:** Companies reverse engineer competitors' products to understand their functionality and gain a competitive advantage.

- **Documentation:** Teams should obtain original equipment manufacturer (OEM) documentation to aid in the reverse engineering process.

- **Security risks:** Sophisticated attackers may tamper with hardware to circumvent security controls.
  - **Example:** NSA intercepted Cisco hardware shipments and inserted eavesdropping equipment.

- **Source authenticity:** Organizations should verify hardware integrity to ensure it hasn't been tampered with before use.
  - Federal government uses "trusted foundries" for sensitive hardware manufacturing, ensuring rigorous security assessments and strong security controls throughout the manufacturing process.

#

# Threat Modeling

## Threat Research

- **Purpose of Threat Intelligence:** Helps understand the environment and defend against adversaries' attacks.

- **Threat Research:** Uses threat intelligence to understand adversaries' motivations and capabilities.

- **Reputational Threat Research:**
  - Identifies actors with a history of malicious activity.
  - Uses past defense mechanisms to block future attempts from known malicious sources.
  - Assigns reputations to objects to prevent repeat access from untrustworthy sources.

- **Behavioral Threat Research:**
  - Identifies unusual behaviors resembling past attackers.
  - Detects patterns even from new IP addresses or sources.

- **Combined Approach:** Using both reputational and behavioral research provides a powerful threat recognition program.

#

## Identify Threats

- **Importance of Structured Approach:** 
  - Avoids haphazard identification of threats, ensuring nothing is left out.

- **Three Structured Approaches:**
  - **Asset-Focused Approach:**
    - Uses the organization's asset inventory.
    - Identifies threats to each asset individually.
    - **Example:** Threat to web presence like severing a fiber optic cable.
  
  - **Threat-Focused Approach:**
    - Lists all possible threats and their impact on systems.
    - Considers a wide spectrum of threats from various sources (hackers, contractors, rogue employees).
    - Understands adversaries' capabilities.
  
  - **Service-Focused Approach:**
    - Commonly used by service providers.
    - Identifies threats to each service interface (e.g., API interfaces).

- **First Step in Threat Modeling:** Identifying all threats is crucial for implementing security controls.

#

## Understand Attacks

- **STRIDE Model:**
  - **Spoofing:** Falsified identity information to gain access. **Countermeasure:** Strong authentication.
  - **Tampering:** Unauthorized changes to systems or data. **Example:** Hacking a database to change grades.
  - **Repudiation:** Denying responsibility for an action. **Countermeasure:** Digital signatures.
  - **Information Disclosure:** Stealing and disclosing confidential information.
  - **Denial of Service (DoS):** Depriving legitimate users of access to systems.
  - **Elevation of Privilege:** Transforming a normal user account into an administrative one.

- **System Diagram:**
  - Useful for determining and evaluating potential attacks.
  - **Example:** E-commerce website diagram showing data flows and firewall boundaries.

- **Reduction Analysis:**
  - Breaking down a system into smaller components for thorough security reviews.

- **Key Concepts:**
  - **Attack Surface:** Total systems and services exposed to potential attack.
  - **Attack Vector:** Means used by an attacker to gain access (e.g., email, web traffic).

#

## Threat Modeling

- **Purpose of Threat Modeling:**
  - Provides valuable information about threats and attack types.
  - Helps identify vulnerabilities and evolve controls.

- **Key Factors in Threat Modeling:**
  - **Adversary Capabilities:** Understand the sophistication and tools of potential attackers.
  - **Attack Surface and Vectors:** Identify the total attack surface and potential attack vectors.
  - **Threat Prioritization:** Assess the impact and likelihood of threats to prioritize them.

- **Technology Perspective:**
  - Conduct periodic reviews of security infrastructure.
  - **Example:** Repeated data theft issues may indicate a need for better data protection controls like DLP systems.

- **Software Development Concerns:**
  - Conduct threat modeling for both internal use and customer security.
  - Address deficiencies that may affect customer security by changing software architecture.

- **Organizational Process Adaptation:**
  - Adapt technology and processes based on threat model results.
  - **Example:** Enhance security of direct deposit forms and change business practices to confirm changes with employees.

- **Overall Lesson:**
  - Threat modeling should inform the entire security program and may require adjustments to business operations.

#

## Attack Surface Management

- **Definition of Attack Surface:**
  - Combination of all systems and services exposed to attackers.
  - Includes border firewalls, public web servers, traveling laptops, and mobile devices.

- **Activities for Managing Attack Surface:**
  - **Edge Discovery Scanning:** Identifies systems or devices with public exposure by scanning IP addresses.
  - **Passive Discovery Techniques:** Monitors inbound and outbound traffic to detect devices missed by other scans.
  - **Security Control Testing:** Verifies that security controls are functioning properly.
  - **Penetration Testing and Adversary Emulation:** Emulates attacker actions to discover security control flaws.

- **Outcome of Discovery and Testing:**
  - Use results to make changes that improve security.
  - **Attack Surface Reduction:** Reduces the number of ways potential adversaries might attack the organization.`

#

## Bug Bounty

- **Purpose of Bug Bounty Programs:**
  - Allows organizations to open their systems to inspection by security researchers.
  - Encourages attackers to report vulnerabilities responsibly.

- **Operation of Bug Bounty Programs:**
  - Often managed by specialized vendors.
  - Vendors design, implement, and operate these programs.
  - Programs can be fully-managed or semi-managed.

- **Benefits of Bug Bounty Programs:**
  - Channels efforts of attackers into legal and legitimate activities.
  - Helps organizations learn from attacker activities and harden their systems.
  - Increases the robustness of the enterprise’s defensive posture.

- **Examples of Bug Bounty Success:**
  - Google paid over $100,000 to a researcher for discovering a serious vulnerability in Pixel phones (2018).
  - The US Department of Defense's "Hack the Army" program identified almost 150 vulnerabilities and paid out about $100,000 in rewards (2020).

- **Types of Bug Bounty Programs:**
  - **Fully-Managed:** Vendor validates reports and provides complete analysis.
  - **Semi-Managed:** Vendor hands off responsibility to the customer earlier in the vulnerability management lifecycle.

- **Key Takeaways:**
  - Bug bounty programs align the interests of organizations and attackers.
  - They are effective at uncovering previously unknown vulnerabilities.
  - Organizations must follow up on reports and remediate issues to benefit fully.

#

# Security Governance

## Align Security with the Business

- **Dual Role of Security Leaders:**
  - Security professionals must balance their roles as both security experts and business leaders.
  - They need to understand the organization’s mission, strategic, and tactical objectives.

- **Balancing Security and Business Needs:**
  - Security controls should manage risks without hindering business operations.
  - Important to design a control environment that balances security and other business considerations.

- **Exam Tip:**
  - Be mindful of questions that might trick you into making decisions solely from a security perspective, which could negatively impact the business.

- **Proposing New Security Controls:**
  - Present a business case justifying the investment in new security controls.
  - Consider the impact on users and the return on investment.

- **Administrative Responsibilities:**
  - Security leaders also manage budgets, conduct performance reviews, counsel employees, and contribute to strategic planning.
  - These tasks help maintain a connection to the broader organization and support its mission.

- **Key Goals of Information Security:**
  - Confidentiality, integrity, and availability should always be considered when making security decisions.

#

## Organizational Processes

- **Alignment with Business Functions:**
  - Information security must align with other organizational functions, including human resources and financial budgets.

- **Governance Processes:**
  - Involves aligning with governance processes at various levels.
  - May include an information governance committee with senior leaders.
  - Could involve a risk management committee managing organizational risks.
  - In non-profits, governance is often overseen by a board of directors or trustees.

- **Security Leaders' Responsibilities:**
  - Ensure governance bodies understand security risks and controls.
  - Inform governing groups of serious security incidents.
  - Review audit results that include security considerations.

- **Acquisitions and Divestitures:**
  - Security professionals must evaluate and integrate security controls during acquisitions.
  - Address redundancies and ensure system compatibility.
  - During divestitures, ensure new organizations have adequate security controls and cut security ties with the parent company.

- **Tailoring Security Governance:**
  - There is no one-size-fits-all model; security governance must be tailored to the specific context of the organization.

#

## Security Roles and Responsibilities

- **Chief Information Security Officer (CISO):**
  - The senior information security leader in an organization.
  - May also be titled Director of Information Security or Chief Security Officer.
  - Reporting structure varies: reports to either the Chief Information Officer or risk management/audit function.

- **Team Composition:**
  - Led by the CISO.
  - Team size varies based on organization size, business nature, and assigned responsibilities.
  - Includes security generalists and specialists in areas like incident response, network security, identity and access management, and security awareness.

- **Guiding Principles:**
  - **Due Care:** Security professionals must fulfill legal responsibilities and professional standards, exercising a reasonable level of care.
  - **Due Diligence:** Security professionals should investigate risks associated with situations, ensuring security controls meet organizational objectives.

#

## Security Control Selection

- **Security Controls Purpose:**
  - **Preventive Controls:** Stop security issues from occurring (e.g., firewalls).
  - **Detective Controls:** Identify potential security breaches (e.g., intrusion detection systems).
  - **Corrective Controls:** Remediate security issues that have occurred (e.g., restoring information from backups).
  - **Responsive Controls:** Initiate incident response (e.g., automatic notifications to police).

- **Mechanisms of Action:**
  - **Technical Controls:** Use technology to achieve security objectives (e.g., firewalls, encryption, antivirus software).
  - **Operational Controls:** Processes managed by individuals (e.g., user access reviews, log monitoring).
  - **Managerial Controls:** Focus on risk management processes (e.g., regular risk assessments, security planning).

- **Defense in Depth Principle:**
  - Applying multiple overlapping controls to achieve the same objective to ensure security even if one control fails.

- **Examples and Analogies:**
  - Home security analogy: Locks, alarms, cameras, and neighbor assistance as various security controls.

- **Categories of Security Controls:**
  - **Preventive:** Block unwanted network traffic.
  - **Detective:** Search for signs of network breaches.
  - **Corrective:** Restore information from backups.
  - **Responsive:** Notify authorities of intrusions.

#

# Risk Management

## Risk Assessment

- **Definition of Risk Assessment:**
  - Process of identifying and prioritizing risks based on their likelihood and impact.

- **Key Terminology:**
  - **Threat:** External force jeopardizing security (e.g., hacking, natural disasters).
  - **Threat Vector:** Method used by an attacker to reach the target (e.g., social engineering).
  - **Vulnerability:** Weakness in security controls that can be exploited.
  - **Risk:** Combination of a threat and a vulnerability.

- **Risk Assessment Process:**
  - Identify risks with both a vulnerability and a corresponding threat.
  - Rank risks based on two factors: likelihood and impact.

- **Likelihood:**
  - Probability that a risk will occur (e.g., higher earthquake probability in California than Wisconsin).

- **Impact:**
  - Amount of damage if the risk materializes (e.g., earthquake causing more damage than a rainstorm).

- **Assessment Techniques:**
  - **Qualitative Techniques:** Use subjective judgment, categorizing risks as low, medium, or high.
  - **Quantitative Techniques:** Use objective numeric ratings to assess likelihood and impact.

- **Qualitative Risk Assessment Chart:**
  - Rates likelihood and impact as low, medium, or high.
  - Categorizes overall risk based on these ratings (e.g., high-probability, high-impact risk is high overall).

#

## Quantitative Risk Assessment

- **Quantitative Risk Management:** Uses numeric data to make informed decisions about risk.
  - **Asset Value (AV):** Estimated value in dollars of an asset.
    - **Original Cost Technique:** Uses purchase invoices to determine asset value.
    - **Depreciating Cost Technique:** Reduces asset value over time based on its useful life.
    - **Replacement Cost Technique:** Uses current market prices to determine the cost of replacing an asset.

  - **Exposure Factor (EF):** Estimates the percentage of an asset that will be damaged if a risk materializes.
  - **Single Loss Expectancy (SLE):** Actual damage expected if a risk occurs once.
    - **Formula:** SLE = Asset Value (AV) × Exposure Factor (EF)
  
  - **Annualized Rate of Occurrence (ARO):** Number of times a risk is expected to occur each year.
  - **Annualized Loss Expectancy (ALE):** Amount of money expected to be lost each year from a specific risk.
    - **Formula:** ALE = Single Loss Expectancy (SLE) × Annualized Rate of Occurrence (ARO)

  - **Mean Time to Failure (MTTF):** Average time expected before a non-repairable asset fails.
  - **Mean Time Between Failures (MTBF):** Average time between failures of a repairable asset.
  - **Mean Time to Repair (MTTR):** Average time an asset will be out of service for repair.
#

## Risk Treatment Options

- **Risk Management Process:**
  - Systematically analyze potential responses to each risk.
  - Implement strategies to control risks appropriately.

- **Four Basic Risk Treatment Options:**
  - **Risk Avoidance:** Change business practices to eliminate the risk.
    - **Example:** Relocate a data center to avoid flood risk.
  
  - **Risk Transference:** Shift the impact of risk to another organization.
    - **Example:** Purchase insurance (e.g., cybersecurity insurance).
  
  - **Risk Mitigation:** Reduce the likelihood or impact of a risk.
    - **Example:** Install flood control systems to protect a data center.
  
  - **Risk Acceptance:** Accept the risk after a thoughtful analysis.
    - **Example:** Continue operations in a flood-prone area due to cost constraints.

- **Risk Profile:**
  - Combination of risks affecting an organization.
  - **Inherent Risk:** Initial level of risk before controls.
  - **Residual Risk:** Risk remaining after controls are applied.
  - **Control Risk:** New risks introduced by implementing controls.

- **Risk Appetite:**
  - The level of risk an organization is willing to accept.
  - **Goal:** Ensure residual and control risks are below the organization's risk appetite.
#

## Risk Management Frameworks

- **Risk Management Frameworks:** Proven techniques for performing enterprise risk management.
  - **NIST Framework:** Widely used, developed by the National Institute of Standards and Technology (NIST), detailed in Special Publication 800-37.

- **Preparation:**
  - Gather technology architecture information: reference models, technical details, business process info, system boundaries.
  - Collect organization-specific information: laws, regulations, policies, strategy, priorities, resources, supply chain info.

- **Six Steps of NIST Risk Management:**
  1. **Categorize Information System:** Assess the system and the information it handles.
  2. **Select Security Controls:** Choose controls based on the system’s categorization.
  3. **Implement Controls:** Put the selected controls into action.
  4. **Assess Controls:** Evaluate if controls are correctly implemented and effective.
  5. **Authorize System:** Formal authorization of the system’s operation, accepting any remaining risks.
  6. **Monitor Controls:** Continuously monitor the controls for effectiveness and respond to changes.
 
#

## Risk Visibility and Reporting

- **Risk Management Tools:** Cybersecurity teams use various tools for risk identification, assessment, and management.
  - **Risk Register:**
    - Centralized document tracking information about each risk.
    - May be used organization-wide or for specific projects/domains.
    - Also known as risk logs.
    - Typically includes:
      - Description of each risk.
      - Categorization scheme.
      - Risk assessment results (probability and impact).
      - Risk rating (probability × impact).
      - Actions taken for risk management.
  
  - **Example:** Educause risk register for higher education IT organizations.
    - Includes risk statements, possible causes, and impact.
    - Risk rating example: Likelihood (3) × Impact (2) = Risk score (6).

  - **Sources for Risk Register:**
    - Formal risk assessments.
    - Audit findings.
    - IT or planning team inputs.
    - Third-party threat intelligence.

- **Threat Intelligence:**
  - Important for maintaining visibility into risks.
  - Can be shared through vendors or consortia.
  - Helps monitor risk trends and create blacklists.

- **Communication with Leaders:**
  - Risk registers might be too detailed for business leaders.
  - Use risk matrices or heat maps for summarizing risks.
  - Helps leaders focus on significant risks quickly.

#

# Quiz

## More Cybersecurity Tools

Which of these is a reconnaissance tool that focuses on open-source intelligence gathering and connecting data points through a graphical user interface?
- Maltego: Maltego is a GUI tool for open-source intelligence gathering.

Which of these is not a cloud security auditing or exploitation tool?
- Malloc: Malloc is a memory allocation command in the C programming language.

The major drawback to using Metasploit for penetration testing is that it is only effective against Linux targets.
- FALSE: Metasploit can be used for pen testing against Linux, Windows, and Mac systems.

## Software Development Lifecycle

Which phase of the CMMI introduces the reuse of code across projects?
- Managed: Level 2 is managed, and activities include configuration management, measurement & analysis, project monitoring & control, project planning, process & product QA, requirements management, and supplier agreement management.

Which software development methodology uses four stages in an iterative process?
- Spiral: The spiral model has four stages: requirements gathering/identification, design, build, and evaluation/risk analysis.

Which of these is not a common example of client/server computing?
- Endpoint applications: Client/server apps interact with a server. Endpoint applications run on the host computer only without interacting with other systems.

Which component of a change management program includes final testing that the software functions properly?
- Release management: During release management, the quality assurance team tests the code and verifies that it meets the requirements, and implements the change described in the RFC.

## Secure Coding Practices

Developers wishing to sign their code must have a _____.
- digital certificate: Developers wishing to sign their code must have a digital certificate. Developers would sign their code using their private key.

What Java clause is critical for error handling?
- Try...Catch: The Java clause Try...Catch is critical for error handling.

Removing names and identification numbers is usually all that is necessary to deidentify a dataset.
- FALSE: You can often combine seemingly innocuous fields to uniquely identify an individual.

Database normalization should ALWAYS be used to improve database security.
- FALSE: The database community has an active and healthy debate about how closely database designers should follow the normal forms.

Which character is commonly used in URL encoding to indicate the replacement of a special character?
- %: The % character is commonly used in URL encoding to indicate the replacement of a special character.

What protocol may be used to secure passwords in transit to a web application?
- TLS: TLS is an Internet protocol that provides end-to-end encryption on data sent between systems and may be used to secure web application passwords.
    - MS-CHAPv2: MS-CHAP v1 & v2 are authentication protocols that do not provide security for web application passwords.

Which of these technologies is an example of a parameterized query?
- Stored procedure: A stored procedure is an example of a parameterized query.

Which input validation approach works to exclude prohibited input?
- Unapproved list: The unapproved list works to exclude prohibited input.

Which data obfuscation technique is intended to be reversible?
- Tokenization: In tokenization, sensitive values are replaced with a unique identifier using a lookup table.

## Software Quality Assurance

What type of organization does the U.S. government use when developing sensitive hardware?
- Trusted foundry: The U.S. government uses a trusted foundry when developing sensitive hardware. Trusted foundries are certified to produce sensitive hardware.

Which language would be a target for a decompiler during reverse engineering?
- C++: C++ would be a target for a decompiler during reverse engineering.

Which kind of testing checks for unexpected side effects of a code change?
- Regression: Regression testing checks for unexpected side effects of a code change.
    - Stress testing: Stress testing is another term for load testing and is used to simulate real activity on the system to verify that it is able to handle the maximum expected load.
    - Beta testing: Beta testing is performed by a group of consumers.
    - UAT: User Acceptance Testing (UAT) is usually the final phase in software testing where end-users use the software with real world transactions.

_____ is usually the final stage in code testing.
- UAT: User Acceptance Testing (UAT) is usually the final phase in software testing.

## Threat Modeling

Which attack surface management activities identify any systems or devices with public exposure by scanning IP addresses belonging to the organization?
- Edge discovery scanning: Edge discovery scanning identifies any systems or devices with public exposure by scanning IP addresses belonging to the organization.

What kind of attacks attempt to deny responsibility for an action?
- Repudiation: A repudiation attack attempts to deny responsibility for an action, and may blame a third party.

What approach to threat identification begins with a listing of all resources owned by the organization?
- Asset-focused:In an asset-focused approach to threat identification, an organization goes through their assets one-by-one and considers possible threats to each.

Companies should always manage bug bounty programs internally.
- FALSE: Organizations deploying a bug bounty program typically do so with the assistance of a vendor.


## Security Governance 

Chris is recovering from a security incident where the attacker installed malicious software on a server. He is rebuilding the server and restoring it from the backup. The backups are an example of what type of control?
- Corrective: Corrective controls correct some of the damage caused by an incident. This is the purpose of backups.

Which of the following describes a situation where a company spins off a part of the business?
- Corporate divestiture: In a corporate divestiture, a company spins off a part of the business.

Security leaders must think as both security leaders and business leaders.
- TRUE: Security leaders serve as subject matter experts on issues of confidentiality, integrity, and availability. Additionally, they serve as business leaders who understand the broader organization's mission, goals, and objectives.

## Risk Management

What is the first step in the NIST risk management framework?
- Categorize information system: The first step is to categorize information system.

Which of these is not a standard risk treatment option?
- Initiation: Initiation is not one of the risk treatment options.

What is the correct formula for computing the annualized loss expectancy?






































 








