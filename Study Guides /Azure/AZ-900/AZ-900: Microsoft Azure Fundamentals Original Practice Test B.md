Attempt 1:

1. What is the benefit of using a command line tool like Powershell or CLI as opposed to the Azure portal?

Cheaper
Quicker to deploy VMS
Automation

2. How do you get access to services in Private Preview mode?

You must apply to use them.
You cannot use private preview services.
They are available in the marketplace. You simply use them.
You must agree to a terms of use first.

3. What does ARM stand for in Azure?

Account Resource Manager
Availability, Reliability, Maintainability
Azure Resource Manager
Advanced RISC Machine

4. Within the context of privacy and compliance, what does the acronym ISO stand for, in English?

Instead of
Intelligence and Security Office
International Organization for Standardization
Information Systems Officer

5. Select the way(s) to increase the security of a traditional user id and password system?

Do not allow users to log into an application except using a company registered device.
Use multi-factor authentication which requires an additional device (something you have) to verify identity.
Require users to change their passwords more frequently.
Require longer and more complex passwords.

6. True or false: Azure Cloud Shell allows access to the Bash and Powershell consoles in the Azure Portal

TRUE
FALSE

7. Which of the following cloud computing models requires the highest level of involvement in maintaining the operating system and file system by the customer?

PaaS
SaaS
FaaS
IaaS

8. Windows servers use "remote desktop protocol" (RDP) in order for administrators to get access to manage the server. Linux servers use SSH. What is the recommendation for ensuring the security of these protocols?

Ensure strong passwords on your Windows admin accounts
Do not allow public Internet access over the RDP and SSH ports directly to the server. Instead use a secure server like Bastion to control access to the servers behind.
Disable RDP access using the Windows Services control panel admin tool
Do not enable SSH access for Linux servers

9. What Azure product allows you to autoscale virtual machines from 1 to 1000 instances, and also provides load balancing services built in?

Azure App Services
Application Gateway
Azure Virtual Machines
Virtual Machine Scale Sets

10. What is the concept of Big Data?

A small sensor or other device that constantly sends it's status and other data to the cloud
A form of artificial intelligence (Al) that allows systems to automatically learn and improve from experience without being explicitly programmed.
A set of Azure services that allow you to use execute code in the cloud but don't require (or even allow) you to manage the underlying server
An extremely large set of data that you want to ingest and do analysis on; traditional software like SQL Server cannot handle Big Data as efficiently as specialized products

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

10. What is the concept of Big Data?

- An extremely large set of data that you want to ingest and do analysis on; traditional software like SQL Server cannot handle Big Data as efficiently as specialized products

Explanation
Big Data - a set of open source (Apache Hadoop) products that can do analysis on millions and billions of rows of data; current tools like SQL Server are not good for this scale
