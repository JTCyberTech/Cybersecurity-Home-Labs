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
- FALSE:




 








