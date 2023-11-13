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
- Suitable for smaller deployments, but may be less useful for large deployments with interdependencies and
- configuration options.

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

- eclarative JSON format to describe resources.
- Verified before execution to ensure correct creation and connection of resources.
- Orchestrates creation of resources in parallel.
- Defines desired state and configuration, automating resource setup.
- Can execute PowerShell and Bash scripts before or after resource setup.
