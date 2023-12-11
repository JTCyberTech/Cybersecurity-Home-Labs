Attempt 1: 20 questions

1. Which of the following characteristics is essential for a system to be considered highly available in a cloud computing environment?

The system must be designed for resilience, with no single points of failure.
The system must operate on a minimum of two virtual machines.
The system must maintain 100% availability at all times.
It's impossible to create a highly available system.

2. What is the basic way of protecting an Azure Virtual Network subnet?

Network Security Group
Application Gateway with WAF
Azure DDos Standard protection
Azure Firewall

3. Which ways does the Azure Resource Manager model provide to deploy resources?

REST API / SDK
CLI
Azure Portal
Powershell

4. Which of the following is something that Azure Cognitive Services API can currently do?

All of these! Azure can do it all!
Create text from audio
Recognize text in an image
Speak text in an extremely realistic way
Translate text from one language to another

5. You have decided to subscribe to Azure DDoS Protection at the IP Protection Tier. This provides advanced protection to defend against DDoS attacks. What type of DDoS attack does DDoS Protection NOT protect against?

Transport (L4) level attacks
Application (L7) level attacks
Network (L3) level attacks


6. Which of the following characteristics of a cloud-based system primarily contributes to its elasticity?

The system's ability to recover automatically after a crash.
The system's ability to dynamically increase and decrease capacity based on real-time demand.
The system's ability to maintain availability while updates are being implemented.
The system's ability to withstand denial-of-service attacks.

7. True or False: Azure has the responsibility to manage the hardware in the Infrastructure as a Service model

TRUE
FALSE

8. What type of container is used to collect log and metric data from various Azure Resources?

Managed Storage
Azure Monitor account
Append Blob Storage
Log Analytics Workspace

9. True or false: you can create your own policies if built-in Azure Policy is not sufficient to your needs

TRUE
FALSE

10. What is the name of the group of services inside Azure that hosts the Apache Hadoop big data analysis tools?

Azure Data Factory
Azure Hadoop Services
Azure Kubernetes Services
HDInsight

11. Which tool within Azure helps you to track your compliance with various international standards and government laws?

Service Trust Portal
Microsoft Privacy Statement
Compliance Manager
Azure Government Services

12. Who is responsible for the security of your Azure Storage account access keys?

I am responsible for securing the access keys
Azure is responsible for securing the access keys

13. Your organization has implemented an Azure Policy that restricts the type of Virtual Machine instances you can use. How can you create a VM that is blocked by the policy?

The only way is to remove the policy, create the resource and add the policy back
Subscription Owners (Administrators) can create resources regardless of what the policy restricts
Use an account that has Contributor or above permissions to the resource group

14. Azure Services can go through several phases in a Service Lifecycle. What are the three phases called?

Announced, Coming Soon, and Live
Preview Phase, General Availability Phase, and Unpublished
Development phase, QA phase, and Live phase
Private Preview, Public Preview, and General Availability

15. True or false: there are no service level guarantees (SLA) when a service is in General Availability (GA)

FALSE
TRUE

16. When establishing a Site-to-Site VPN connection with Azure, what kind of network device needs to be present or installed in your company's on-premises network infrastructure?

An Application Gateway
An Azure Virtual Network
A compatible VPN Gateway device
A dedicated virtual machine

17. What feature within Azure will make recommendations to you about reducing cost on your account?

Azure Advisor
Azure Dashboard
Azure Security Center
Azure Service Health

18. An IT administrator has the requirement to control access to a specific app resource using multi-factor authentication. What Azure service satisfies this requirement?

Azure Function
Azure Authorization
Azure Authentication
Microsoft Entra ID

19. What is the name of Azure's hosted SQL database service?

Azure SQL Database
SQL Server in a VM
Table Storage
Cosmos DB

20. In Microsoft Azure, which tool or service allows for the organization and management of multiple subscriptions within hierarchical structures?

Management Groups
Resource Groups
Azure Active Directory
RBAC (Role-Based Access Control)

#

correct (15/20)
Incorrect: 5, 11, 16, 18, 19

Answer: 

1. Which of the following characteristics is essential for a system to be considered highly available in a cloud computing environment?

- The system must be designed for resilience, with no single points of failure.

The correct answer is "A system specifically designed to be resilient, with no single point of failures". High availability in a system means that it is designed to operate continuously without failure for a long period of time. This is achieved by building redundancy into the system, eliminating single points of failure, and enabling rapid recovery from any failures that do occur. In other words, even if a component of the system fails, there are other components that can take over, allowing the system to continue operating seamlessly.

While high availability often aims for close to 100% uptime, the claim of maintaining 100% availability is practically unrealistic due to factors like maintenance needs and unexpected failures. Also, having a minimum of two VMs may contribute to high availability but isn't a definitive requirement — it depends on the specifics of the system architecture.

Finally, the assertion that it's not possible to create a highly available system is incorrect. There are established strategies and technologies for designing and operating highly available systems, and they are widely used in mission-critical applications across many industries.

#

2. What is the basic way of protecting an Azure Virtual Network subnet?

- Network Security Group

Network Security Group (NSG) - a fairly basic set of rules that you can apply to both inbound traffic and outbound traffic that lets you specify what sources, destinations, and ports are allowed to travel through from outside the virtual network to inside the virtual network

#

3. Which ways does the Azure Resource Manager model provide to deploy resources?

- REST API / SDK
- CLI
- Azure Portal
- Powershell

Azure Resource Manager (ARM) is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in your Azure account. The ARM model allows you to work with resources in a consistent manner, whether through Azure portal, PowerShell, REST APIs/SDKs, or the Command-Line Interface (CLI).

Azure Portal: This is a web-based, unified console that provides an alternative to command-line tools. You can manage your Azure resources directly through a GUI.

PowerShell: Azure PowerShell is a module that provides cmdlets to manage Azure through Windows PowerShell and PowerShell Core. You can use it to build scripts for managing and automating your Azure resources.

REST API / SDK: Azure provides comprehensive REST APIs that can be used directly or via Azure SDKs available in multiple languages. This allows developers to integrate Azure services in their applications, services, or tools.

CLI: Azure CLI is a cross-platform command-line program that connects to Azure and executes administrative commands on Azure resources. It's designed to make scripting easy, authenticate with Azure platform, and quickly run commands to perform common administrative tasks or deploy to Azure.

Each of these methods supports the full set of Azure Resource Manager features, and you can choose the one that best fits your workflow.

#

4. Which of the following is something that Azure Cognitive Services API can currently do?

- All of these! Azure can do it all!

Azure can do all of them, of course.

#

5. You have decided to subscribe to Azure DDoS Protection at the IP Protection Tier. This provides advanced protection to defend against DDoS attacks. What type of DDoS attack does DDoS Protection NOT protect against?

- Application (L7) level attacks

The correct answer is "Application level attacks":

Network-level attacks are attacks that target the network infrastructure, such as the routers and switches that connect your Azure resources to the internet. Azure DDoS Protection IP Protection Tier can protect against network-level attacks by absorbing and rerouting excessive traffic, and by scrubbing malicious traffic.

Transport-level attacks are attacks that target the transport layer of the network protocol stack, such as TCP and UDP. Azure DDoS Protection IP Protection Tier can protect against transport-level attacks by absorbing and rerouting excessive traffic, and by scrubbing malicious traffic.

Application-level attacks are attacks that target the application layer of the network protocol stack, such as HTTP and DNS. Azure DDoS Protection IP Protection Tier does not protect against application-level attacks, because it is designed to protect against network and transport-level attacks.

To protect against application-level attacks, you need to use a web application firewall (WAF). A WAF is a software appliance that sits in front of your application and filters out malicious traffic. WAFs can be configured to protect against a wide variety of application-level attacks, such as SQL injection, cross-site scripting, and denial of service attacks.

#

6. Which of the following characteristics of a cloud-based system primarily contributes to its elasticity?

- The system's ability to dynamically increase and decrease capacity based on real-time demand.

The correct answer is "The ability to increase and reduce capacity based on actual demand." This characteristic refers to the concept of elasticity in cloud computing. An elastic system is one that can automatically adjust its resources (compute, storage, etc.) in response to changing workloads and demands. This is done to ensure optimal performance and cost-effectiveness. When demand increases, the system can scale out by adding more resources, and when demand decreases, it can scale in by reducing resources, all without significant manual intervention.

The other options, while important for overall system robustness, do not define elasticity. Withstanding denial of service attacks pertains to security, maintaining availability during updates refers to zero-downtime deployment or high availability, and self-healing after a crash refers to resilience or fault tolerance. None of these are about dynamically adjusting capacity based on demand, which is the hallmark of an elastic system.

#

7. True or False: Azure has the responsibility to manage the hardware in the Infrastructure as a Service model

- TRUE

The correct answer is TRUE. In an Infrastructure as a Service (IaaS) model, the cloud service provider, in this case Microsoft Azure, is responsible for managing the underlying physical hardware. This includes servers, storage, networking hardware, and the virtualization layer. Azure ensures that these resources are available and maintained, providing capabilities like automated backup, disaster recovery, and scaling.

The customer, on the other hand, is responsible for managing the software components of the service, including the operating system, middleware, runtime, data, and applications. This arrangement allows customers to focus on their core business and application development without worrying about the physical infrastructure's procurement, management, and maintenance.

It's important to remember that the division of responsibilities may change in other service models like Platform as a Service (PaaS) or Software as a Service (SaaS), where the cloud service provider manages more layers of the technology stack. But for IaaS, the provider indeed manages the hardware, making the statement TRUE.

#


8. What type of container is used to collect log and metric data from various Azure Resources?

- Log Analytics Workspace

Log Analytics Workspace is required to collect logs and metrics

#

9. True or false: you can create your own policies if built-in Azure Policy is not sufficient to your needs

- TRUE

True, you can create custom policies using JSON

#

10. What is the name of the group of services inside Azure that hosts the Apache Hadoop big data analysis tools?

- HDInsight

The correct answer is HDInsight. HDInsight is Microsoft Azure's offering for hosting the Apache Hadoop big data analysis tools. Apache Hadoop is an open-source software platform that supports data-intensive distributed applications. This platform enables processing large amounts of data across clusters of computers.

Azure HDInsight is a cloud distribution of the Hadoop components from the Hortonworks Data Platform. It allows Azure users to process vast amounts of data with popular open-source frameworks such as Hadoop, Hive, HBase, Storm, and others. Additionally, the HDInsight service also supports R, Python, Scala, and .NET. So, it's not just limited to traditional Hadoop tools.

Options like 'Azure Hadoop Services' and 'Azure Data Factory' are incorrect as Azure doesn't have a service named 'Azure Hadoop Services' and 'Azure Data Factory' is a cloud-based data integration service. 'Azure Kubernetes Services' is a service for managing containerized applications, not specifically for Hadoop.

#

11. Which tool within Azure helps you to track your compliance with various international standards and government laws?

- Compliance Manager

Compliance Manager will track your own compliance with various standards and laws.

#

12. Who is responsible for the security of your Azure Storage account access keys?

- I am responsible for securing the access keys

Customers are responsible to secure the access keys they are given and regenerate them if they are exposed.

#

13. Your organization has implemented an Azure Policy that restricts the type of Virtual Machine instances you can use. How can you create a VM that is blocked by the policy?

- The only way is to remove the policy, create the resource and add the policy back

You cannot perform a task that violates policy, so you have to remove the policy in order to perform the task.

#

14. Azure Services can go through several phases in a Service Lifecycle. What are the three phases called?

- Private Preview, Public Preview, and General Availability

Private Preview, Public Preview, and General Availability

#

15. True or false: there are no service level guarantees (SLA) when a service is in General Availability (GA)

- FALSE

False, most Azure GA services do have service level agreements

#

16. When establishing a Site-to-Site VPN connection with Azure, what kind of network device needs to be present or installed in your company's on-premises network infrastructure?

- A compatible VPN Gateway device

The correct answer is a compatible VPN Gateway device.

In order to establish a site-to-site VPN connection with Azure, a VPN Gateway is required on your company's internal network. A VPN Gateway is a specific type of virtual network gateway that sends encrypted traffic across a public network, like the Internet.

While the name might suggest it's a purely virtual entity, in practice, the term "VPN Gateway" often refers to a hardware device that's installed on-premises in your data center. This device uses Internet Protocol security (IPsec) to establish a secure, encrypted connection to the Azure VPN Gateway, which resides in the Azure virtual network.

This setup allows your local network and Azure to interact as if they're directly connected. In contrast, virtual machines, virtual networks, and application gateways are other types of Azure resources, but they do not facilitate creating a site-to-site VPN connection. It's important to note that your company's internal network hardware and settings must meet specific requirements to support a VPN Gateway.

#

17. What feature within Azure will make recommendations to you about reducing cost on your account?

- Azure Advisor

Azure Advisor analyzes your account usage and makes recommendations for you based on its set rules

#

18. An IT administrator has the requirement to control access to a specific app resource using multi-factor authentication. What Azure service satisfies this requirement?

- Microsoft Entra ID

You can use Microsoft Entra ID (new name for Azure AD) to control access to your apps and your app resources, based on your business requirements. In addition, you can use Microsoft Entra ID (Azure AD) to require multi-factor authentication when accessing important organizational resources.

#

19. What is the name of Azure's hosted SQL database service?

- Azure SQL Database

SQL Database is a SQL Server compatible option in Azure, a database as a service

#

20. In Microsoft Azure, which tool or service allows for the organization and management of multiple subscriptions within hierarchical structures?

- Management Groups

The correct answer is Management Groups. In Azure, Management Groups provide a way to manage access, policies, and compliance for multiple subscriptions. They can be structured into a hierarchy for the organization's needs. All subscriptions within a Management Group automatically inherit the conditions applied to the Management Group, facilitating governance on a large scale.

Resource Groups, on the other hand, are containers for resources deployed on Azure. They do not provide management capabilities across multiple subscriptions.

RBAC (Role-Based Access Control) is a system that provides fine-grained access management to Azure resources but it doesn't inherently support the organization of subscriptions into hierarchies.

Azure Active Directory is a service that provides identity and access management capabilities but does not provide a direct mechanism for managing multiple subscriptions in nested hierarchies.

Hence, Management Groups is the correct answer as it directly allows for the management and organization of multiple subscriptions into nested hierarchies, which the other options do not.

#





