# Azure AD DS (Azure Active Directory Domain Service)

- Not part of Azure AD; part of Microsoft Entra.
- Can be enabled in ARM virtual network.
- Cannot invite guest user to use.
- Cannot be pause once deployed; have to delete it to stop.
- Includes High availability options; have have 2 doamin controllers.

#

# Azure AD (Azure Active Directory)

- Let you set dynamic membership rules.
- Azure monitor can send alerts to AD's security group.
- Azure AD can save logs in Azure Monitor.
- Allows users to authenticate by using Single Sign-On (SSO).
- Conditional Access in Azure AD = based on organizational policies.
- Application can connect to Azure AD to retrieve security tokens.
- Provides authenication service for Azure and Microsoft 365.
- No need Domain controller.
- User Account in Azure AD can be assign to multiple license.
- 

#

# Azure AD service

- Azure AD Privileged Identity Maangement (PIM) = enable for manage control and monitor access to important resource.
- Azure AD Identity Protection = have function to encourage password change.
- Azure AD Identity Protection = Can enforce Azure MFA based on condition.

#

# Azure Resources Group: inherit

- Azure resource **inherit locks** from resource group.
- Azure resource **inherit permissions** from resource group.
- Azure resource **Doesn't Inherit tags** from resource group.

#

# Azure Resource Group

- You cannot nest resource group; cannot create resource group inside a resource group.
- Azure Virtual Machine can only be in one resource group; VM cannot be in multiple resource group.
- Resource group can be from multiple Azure Regions.
- Must deploy Azure VM to Azure resource group if you need put permissions to serveral Azure VM.

#

# Management Groups

- Manage multiple subscription.

#

# Azure Policies

- Helps with implementing tagging.
- Applies to newly created resources after assigning policy, existing one will continue to function the same.

#

# Azure Resource Manger Templates

- Identical
- 

#

# Azure Monitor

- Can send alert -> Azure AD security groups.
- Can trigger alerts -> data in Azure Log Analytic Workspace.
- Can monitor on-premises computers performance.
- Can help Azure AD save logs.

#

# Trust Center

- To identify complies of regional requirements.
- Regulatory requirement can also be -> Compliance Manager from Security Trust Portal.
- Information about Microsoft cloud help secure sensitive data and comply with laws and regulations.
- Tracks company's regulatory standards and regulations like ISO 27001.

#

# Sevice Trust Portal/ Microsoft Defender for Cloud

- Service Trust Portal = Download published audit reports.
- Microsoft Defender for Cloud = Download regulatory Compliance Report.

# 

# ExpressRoute

- Layer 3 of the OSI Layer; Network.
- On-Premises network and Microsoft cloud over private connection.

#

# Service Plans

- Contact Microsoft engineer by phone/email in business hours = Professional Direct; Standard; Developer; Not included in Basic Plan.
- Health Status/notification, 24/7 access to billing information = Professional Direct; Standard; Developer; Basic. ALL

#

# Software as a Service (SaaS)

- No need to apply software updates.

#

# Infrasturcture as a Service (IaaS)

- Azure Storage Account; Virtual Machine; Disk Storage; Virtual Network.
- Must install software that you want to use.

#

# Platform as a Service (PaaS)

- App Service;
- App Search;
- Azure CDN (Content Delivery Network);
- Cosmos DB; Azure Webapp;
- Logic App;
- Azure SQL Database;
- Azure Files;
- Azure Backup;
- Microsoft SQL Database.

#

# Cost on Azure

- Azure Cost Mangement = helps analyze cost create and manage budge export data; cost optimization; Azure invoice (bills); Manage billing account and subscription.
- Azure Cost Management = Use to view cost associated to management groups and resource groups, and usage of VM during last 3 months.
- Azure Cost Management Requirement = Microsoft Customer Agreement and Azure Plan.
- Azure Total Cost of Ownship (TCO) Calculator = help you calculate on-premise cost vs moving to Azure.

#

# Azure Firewall

- Deny by default.

#

# Azure Blueprint

- Design pattern for Azure Environment.
- Component type: ARM Templates; Azure Role Assignment; Azure Resource Groups; Azure Policy Assignment.
- Blueprint Contributor = bulit-in role that can manage blueprint but not assign them.

# 

# Network Security Group/ Azure Firewall

- NSG = Filter internet traffic in Azure virtual Network.
- NSG inbound security rule = IP Address, Service tag, Application security groups.
- Azure Firewall = Filter internet traffic out of Azure virtual network.

#

# Azure Logic Apps

- Execute workflows from predefined logic block without code.
- Serverless computing; Orchestrate -> like send email notifications automatically based on rule.

#

# Random Services 

- Azure Application Insights = Detect diagnose anomalies in web apps.
- Azure Information Protection = Protect classify documents/emails; apply label to the content.
- Azure Key Vault = Secret; credentials encryption.
- Microsoft Purview compliance portal -> Compliance Manager.
- Azure SQL Data Warehouse = high availability.
- Azure Batch = enable scale 1000s of VM for high-performance computing and large scale parallel job.
- JIT VM = Azure Security Center.
- Azure Advanced Threat Protection (ATP) = Monitor threat by using sensors.
- DDoS protection = generates reports on the attacks; secure website.
- Azure Databrick = Apache Spark-bazed analytics service.

