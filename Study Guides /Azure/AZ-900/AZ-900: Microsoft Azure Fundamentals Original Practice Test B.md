Attempt 1:

1. What is the benefit of using a command line tool like Powershell or CLI as opposed to the Azure portal?

- Cheaper
- Quicker to deploy VMS
- Automation

2. How do you get access to services in Private Preview mode?

- You must apply to use them.
- You cannot use private preview services.
- They are available in the marketplace. You simply use them.
- You must agree to a terms of use first.

3. What does ARM stand for in Azure?

- Account Resource Manager
- Availability, Reliability, Maintainability
- Azure Resource Manager
- Advanced RISC Machine

4. Within the context of privacy and compliance, what does the acronym ISO stand for, in English?

- Instead of
- Intelligence and Security Office
- International Organization for Standardization
- Information Systems Officer

5. Select the way(s) to increase the security of a traditional user id and password system?

- Do not allow users to log into an application except using a company registered device.
- Use multi-factor authentication which requires an additional device (something you have) to verify identity.
- Require users to change their passwords more frequently.
- Require longer and more complex passwords.

6. True or false: Azure Cloud Shell allows access to the Bash and Powershell consoles in the Azure Portal

- TRUE
- FALSE

7. Which of the following cloud computing models requires the highest level of involvement in maintaining the operating system and file system by the customer?

- PaaS
- SaaS
- FaaS
- IaaS

8. Windows servers use "remote desktop protocol" (RDP) in order for administrators to get access to manage the server. Linux servers use SSH. What is the recommendation for ensuring the security of these protocols?

- Ensure strong passwords on your Windows admin accounts
- Do not allow public Internet access over the RDP and SSH ports directly to the server. Instead use a secure server like Bastion to control access to the servers behind.
- Disable RDP access using the Windows Services control panel admin tool
- Do not enable SSH access for Linux servers

9. What Azure product allows you to autoscale virtual machines from 1 to 1000 instances, and also provides load balancing services built in?

- Azure App Services
- Application Gateway
- Azure Virtual Machines
- Virtual Machine Scale Sets

10. What is the concept of Big Data?

- A small sensor or other device that constantly sends it's status and other data to the cloud
- A form of artificial intelligence (Al) that allows systems to automatically learn and improve from experience without being explicitly programmed.
- A set of Azure services that allow you to use execute code in the cloud but don't require (or even allow) you to manage the underlying server
- An extremely large set of data that you want to ingest and do analysis on; traditional software like SQL Server cannot handle Big Data as efficiently as specialized products

#

Answer: 

1. What is the benefit of using a command line tool like Powershell or CLI as opposed to the Azure portal?

- Automation

Explanation

The real benefit is automation. Being able to write a script to do something is better than having to do it manually each time.

#

2. How do you get access to services in Private Preview mode?

- You must apply to use them.

Explanation

Private Preview means you must apply to use them.

#

3. What does ARM stand for in Azure?

- Azure Resource Manager

Explanation

Azure Resource Manager (ARM) - this is the common resource deployment model that underlies all resource creation or modification; no matter whether you use the portal, powershell or the SDK, the Azure Resource Manager takes those commands and executes them

#

4. Within the context of privacy and compliance, what does the acronym ISO stand for, in English?

- International Organization for Standardization

Explanation

ISO is a standards body, International Organization for Standardization

#

5. Select the way(s) to increase the security of a traditional user id and password system?

- Do not allow users to log into an application except using a company registered device.
- Use multi-factor authentication which requires an additional device (something you have) to verify identity.
- Require users to change their passwords more frequently.
- Require longer and more complex passwords.

Explanation

All of these are ways to increase the security on an account.

#

6. True or false: Azure Cloud Shell allows access to the Bash and Powershell consoles in the Azure Portal

- TRUE

Explanation

Cloud Shell - allows access to the Bash and Powershell consoles in the Azure Portal

#

7. Which of the following cloud computing models requires the highest level of involvement in maintaining the operating system and file system by the customer?

- IaaS

Explanation

IaaS or Infrastructure as a service requires you to keep your OS patched, close ports, and generally protect your own server

#

8. Windows servers use "remote desktop protocol" (RDP) in order for administrators to get access to manage the server. Linux servers use SSH. What is the recommendation for ensuring the security of these protocols?

- Do not allow public Internet access over the RDP and SSH ports directly to the server. Instead use a secure server like Bastion to control access to the servers behind.

Explanation

You need to either control access to the RDP and SSH ports to a very specific range of IPs, enable the ports only when you are using it, or use a Bastion server/jump box to protect those servers.

#

9. What Azure product allows you to autoscale virtual machines from 1 to 1000 instances, and also provides load balancing services built in?

- Virtual Machine Scale Sets

Explanation

Virtual Machine Scale Sets - these are a set of identical virtual machines (from 1 to 1000 instances) that are designed to auto-scale up and down based on user demand; IaaS

#

10. What is the concept of Big Data?

- An extremely large set of data that you want to ingest and do analysis on; traditional software like SQL Server cannot handle Big Data as efficiently as specialized products

Explanation

Big Data - a set of open source (Apache Hadoop) products that can do analysis on millions and billions of rows of data; current tools like SQL Server are not good for this scale


#

1. Which Azure service is the recommended Identity-as-a-Service offering inside Azure?

- Azure Active Directory (AD)

Azure AD is the identity service designed for web protocols, that you can use for your applications.

2. What would be a good reason to have multiple Azure subscriptions?

- There is one person/credit card paying for resources, but many people who have accounts in Azure, and you need to separate out resources between clients so that there is absolutely no chance of resources being exposed between them.

Explanation

Having multiple subscriptions can technically be done for any reason, but it only makes sense if you have to separate billing directly, or have actual clients logging into the Portal to manage their resources.

3. Which of the following is not a feature of Azure Functions?

- Designed for backend batch applications that are continuously running

Explanation

Functions are designed for short pieces of code that start and end quickly.


#

1. Select all features part of Azure AD?

- Single sign-on
- Smart lockout
- Custom banned password list
- Device Management

Explanation

The Log Alert Rule is not a feature of Azure AD.

2. Application Gateway contains what additional optional security feature over a regular Load Balancer?

- Web Application Firewall (or WAF)

Explanation

Application Gateways also comes with an optional Web Application Firewall (or WAF) as a security benefit

3. What is the benefit of using Powershell over CLI?

- No benefit, it's the same

Explanation

There is no benefit, only a matter of personal choice.

4. Each person has their own user id and password to log into Azure. But how many subscriptions can a single account be associated with?

- No limit

Explanation

There is not a limit to the number of subscriptions a single user can be included on.

#

1. What does it mean if a service is in General Availability (GA) mode?

- Anyone can use the service for any reason

Explanation

Anyone can use a GA service. It is fully supported and can be used for production.

2. Which of the following elements is considered part of the "perimeter" layer of security?

- Use a firewall

Explanation

Firewall is part of the perimeter security

3. Which free Azure security service checks all traffic travelling over a subnet against a set of rules before allowing it in, or out.

- Network Security Group

Explanation

Network Security Group (NSG) - a fairly basic set of rules that you can apply to both inbound traffic and outbound traffic that lets you specify what sources, destinations and ports are allowed to travel through from outside the virtual network to inside the virtual network.

4. Besides Azure Service Health, where else can you find out any issues that affect the Azure global network that affect you?

- Each Virtual Machine has a Resource Health blade

Explanation

Each Virtual Machine has a Resource Health blade

5. What types of files can a Content Delivery Network speed up the delivery of?

- Videos
- PDFs
- Images
- JavaScript files

Explanation

All of them. Any static file that doesn't change.

6. In which US state is the East US 2 region?

- Virginia

Explanation

East US 2 is in the Eastern state of Virginia, close to Washington DC

7. What is the new data privacy and information protection regulation that took effect across Europe in May 2018?

- GDPR

Explanation

The General Data Protection Regulation (GDPR) took effect in Europe in May 2018.

8. How many regions does Azure have in Brazil?

- 1 

Explanation

There is 1 region in Brazil.

9. What is the Azure SLA for two or more Virtual Machines in an Availability Set?

- 99.95%

10. What is the service level agreement for two or more Azure Virtual Machines that have been manually placed into different Availability Zones in the same region?

- 99.99%

11. Why is Azure App Services considered Platform as a Service?

- You give Azure the code and configuration, and you have no access to the underlying hardware

#

