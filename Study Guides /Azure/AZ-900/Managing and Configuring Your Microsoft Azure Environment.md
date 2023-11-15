# Introduction Overview

1. Azure Management Tools Overview:

- Azure management tools facilitate interaction with the cloud environment.
- Targeted at administrators, developers, and managers.
- Tasks include deploying numerous resources simultaneously, configuring individual services programmatically, and generating comprehensive reports on usage, health, and costs.

2. Microsoft Azure's Management Tool Options:

- Provides a variety of management tooling options based on specific situations.
- Tailwind Traders, a traditional retailer, achieved online success by efficiently managing its cloud environment with Azure tools.

3. Tailwind Traders' Cloud Journey:

- Experienced explosive growth by transitioning to online sales.
- Success attributed to quick and efficient cloud environment management.

4. Decision Criteria for Management Tools:

- Experts use decision criteria to choose the right management tools for specific business scenarios.
- Importance of understanding Azure's array of management tools.

5. Outcome of the Lesson:

- Lesson focuses on exploring Azure management tools and decision criteria.
- Aim is to empower individuals to choose Azure management tools aligned with their organization's technical needs and challenges.

<h2></h2>

# Identify the product options

1. Management Tool Categories:

- Two broad categories: visual tools and code-based tools.

2. Visual Tools:

- Provide visually friendly access to all Azure functionalities.
- Suitable for smaller deployments, but may be less useful for large deployments with interdependencies and configuration options.

3. Code-Based Tools:

- Better choice for quickly setting up and configuring Azure resources, especially for large deployments.
- Commands and parameters can be saved into files for repeated use.
- Code can be stored, versioned, and maintained alongside application source code in Git.
- This approach is referred to as "infrastructure as code."

4. Approaches to Infrastructure as Code:

- Imperative code details each step to achieve a desired outcome.
- Declarative code details only the desired outcome, allowing an interpreter to decide how to achieve it.
- Declarative code is more robust for deploying many resources simultaneously.

5. Azure Management Tools:

- Azure Portal: Web-based user interface for accessing all Azure features.
- Azure Mobile App: iOS and Android access to Azure resources for monitoring, issue diagnosis, and management.
- Azure CLI and Azure PowerShell: Command-line tools for managing Azure resources.
  - Azure PowerShell uses commandlets and calls the Azure REST API.
  - Available on Windows, Linux, Mac, and via a web browser in Azure Cloud Shell.

6. Azure PowerShell:

- Shell for developers, DevOps, and IT professionals.
- Executes commandlets to perform Azure management tasks.
- Scripts for routine setup, tear down, and maintenance of resources.

7. Azure CLI:

- Executable program for executing commands in Bash.
- Similar to Azure PowerShell but uses Bash syntax.
- Can run commands independently or in scripts for resource management.

8. Azure Resource Manager Templates:

- Declarative JSON format to describe resources.
- Verified before execution to ensure correct creation and connection of resources.
- Orchestrates creation of resources in parallel.
- Defines desired state and configuration, automating resource setup.
- Can execute PowerShell and Bash scripts before or after resource setup.

<h2></h2>

# Analyze the decision criteria

Analyzing Azure Management Tools Criteria:

- Understanding criteria used by experts to choose Azure management tools for business needs.
- Nuanced differences among products to be considered.

One-Off Management Actions:

- Use Azure PowerShell or Azure CLI for one-off management, administrative, or reporting actions.
- Azure Resource Manager (ARM) templates are not intended for one-off scenarios.

ARM Templates:

- Express infrastructure requirements for repeatable deployments.
- Can include PowerShell or Azure CLI scripts for flexibility.
- Suited for scenarios requiring repeatable setups and dependency management.

Azure Portal:

- Visual interface for management and administrative actions.
- Suitable for learning Azure, frequent resource setup, and visual reporting.
- Less efficient for cloud management or administrative roles.

Efficiency Considerations:

- Azure CLI or PowerShell more efficient for cloud management or administrative roles.
- Visual scanning and clicking in Azure Portal less efficient for such roles.

Azure Mobile App:

- Accessible via iOS or Android devices.
- Full-featured, suitable when a laptop is not readily available for immediate issue viewing and triage.

Repeatable Resource Setup:

- Use ARM templates for repeated resource setups with proper dependencies.
- ARM templates provide validation steps, item potency, and parallel resource creation.

Scripting Considerations:

- PowerShell preferred if coming from a Windows administration background.
- Azure CLI preferred if coming from a Linux administration background.
- Either tool can be used for most one-off administration tasks.

Deployment Considerations:

- PowerShell or Azure CLI can set up all resources for a deployment.
- ARM templates provide validation steps and item potency, ensuring proper dependency management.

<h2></h2>

# Visually understand and manage your cloud environment

Azure Usage at Tailwind Traders:

- Tailwind Traders extensively uses Azure across the organization.

Cloud Spending Awareness:

- Director of Cloud Operations and Chief Financial Officer meet weekly to discuss Cloud spending.

Meeting Goals:

- Discussion starts at a high level but may involve deep dives for insights into Azure resource usage.

Data Visualization and Real-time Reporting:

- Ideal scenario includes visualizing data and running custom reports in real-time during the meeting.

Tool Selection Criteria:

- Decision criteria include the need for one-off management, administrative actions, or reporting.
- Azure portal is chosen based on the requirement to view data visually and create custom reports during the meeting.

Azure Portal Advantages:

- Provides a wealth of reporting options.
- Enables meeting attendees to quickly find answers to their questions.

Relevance of Scripting Background:

- Questions about repeatedly setting up resources and scripting background are deemed irrelevant for this scenario.
- The director of Cloud operations and the CFO won't be deploying or configuring any resources.

Conclusion:

- Azure portal is the correct product option for this scenario, meeting the needs of visual data presentation and real-time reporting without the need for resource deployment or configuration.

<h2></h2>

# Use Azure for one-off administrative tasks

Tailwind Traders Scenario:

- Team with diverse technologists.
- Strong backgrounds in Windows development and network administration.
- Applications moved to the cloud, requiring one-off testing, management, and administrative tasks.

Issue with Azure Portal:

- Managing Azure from the portal is time-consuming and not repeatable.

Decision Criteria:

- Need for one-off management, administrative, or reporting tasks: Yes.
- Requirement for a repeatable and reliable means of deploying the entire infrastructure: No.
- Scripting background: Windows administration.

Tool Options:

- Azure PowerShell and Azure CLI are both suitable.
- Azure Resource Manager templates are not the right choice for this scenario.

Choice:

- Azure PowerShell is the best choice.
- Comfortable syntax for a team with a Windows administration background.
- Allows the team to perform one-off administration tasks efficiently and with familiarity.

<h2></h2>

# Use the Azure CLI for one-off administrative tasks

Tailwind Traders' Technologists:

- Employs technologists with diverse skills.

DevOps Team Focus:

- DevOps team primarily concerned with keeping external systems, like the e-commerce site, operational.
- Possesses a Linux administration background.

Challenges in Azure Management:

- Managing Azure from the portal is time-consuming and non-repeatable.

Tool Selection Criteria:

- Need a tool for administrative tasks related to the health of the cloud environment.

Decision Criteria Application:

- Skip Azure Resource Manager templates and Azure portal based on decision criteria.

Third Decision Criterion:

- Choose the option based on the team's background.

Preferred Option for Linux Administration Background:

- Due to a Linux administration background, the team would be most comfortable using the Azure CLI.

Azure CLI Benefits:

- Allows the use of the bash shell and its syntax.
- Enables efficient performance of administrative tasks.

Conclusion:

- Azure CLI is identified as the best choice for this scenario based on the team's background and the need for effective administration tasks in the Azure environment.

#

# Manage Azure on the go

Tailwind Traders Situation:

- Experiences surges in e-commerce traffic during national holidays and weekends.
- Historically, critical system managers had to convene at the director of cloud operations' office during important periods.

Operational Improvement:

- Tailwind Traders has successfully operationalized most critical systems.

Director's Intention:

- Director wants to relax the requirement for managers to be physically present during peak periods.
- Aims to allow employees to spend holidays and weekends with their families.

Need for Remote Monitoring:

- Question: Does Tailwind Traders need to remotely monitor and administer services?
- Answer: Yes.

Solution Suggested:

- Proposed solution involves using a phone or tablet for remote monitoring.
- Azure mobile app is recommended as a suitable compromise.
- Allows key employees to monitor the health of the cloud environment while away from the office.

Benefits of Azure Mobile App:

- Enables employees to be away from work while still performing essential management and administrative tasks.

Decision Criteria:

- In this unique scenario, the text suggests that the decision criteria beyond the Azure mobile app can be skipped.

Conclusion:

- The Azure mobile app is identified as the right choice for Tailwind Traders in this scenario.

#

# Use ARM Templates to deploy an entire cloud Infrastructure

