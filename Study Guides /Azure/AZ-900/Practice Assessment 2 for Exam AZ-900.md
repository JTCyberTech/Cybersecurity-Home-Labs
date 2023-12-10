1. Which two attributes are characteristics of the private cloud deployment model? Each correct answer presents a complete solution.

- Hardware must be purchased.
- The company has complete control over physical resources and security.

In a private cloud, hardware must be purchased for start up and maintenance. In a private cloud, organizations control resources and security. Quick provisioning is a characteristic of the public cloud deployment model. Paying only for what is used is a characteristic of the public cloud deployment model.

2. Which two characteristics are common advantages of cloud computing? Each correct answer presents a complete solution.

- geo-distribution
- high availability

Cloud-based apps can provide a continuous user experience with no apparent downtime, even when things go wrong. You can deploy apps and data to regional datacenters around the globe, thereby ensuring that your customers always have the best performance in their region. Apps in cloud computing can scale vertically and horizontally. In a public cloud model, you do not get physical access to servers, as they are managed by the cloud provider.

3. Why is cloud computing often less expensive than on-premises datacenters? Each correct answer presents a complete solution.

- You are only billed for what you use.

Renting compute and storage services and being billed for only what you use often lowers operating expenses. Depending on the service and the type of network bandwidth, charges can be incurred. Cloud service offerings often provide functionality that can be difficult or cost-prohibitive to deploy on-premises, especially for smaller organizations. Major cloud providers offer services around the world. Making it easy and relatively inexpensive to deploy services close to where your users reside.

4. What is an advantage of cloud computing compared to on-premises deployments?

- You can scale more quickly.

Cloud computing allows you to scale more quickly. Owning your own CPUs and having full access in the event of an internet outage are not features of cloud computing. Working from multiple workstations is not specific to cloud computing compared to an on-premises deployment.

5. Increasing compute capacity for an app by adding RAM or CPUs to a virtual machine is called [answer choice].

- vertical scaling

You scale vertically to increase compute capacity by adding RAM or CPUs to a virtual machine. Scaling horizontally increases compute capacity by adding instances of resources, such as adding virtual machines to the configuration. Disaster recovery keeps data and other assets safe in the event of a disaster. High availability minimizes downtime when things go wrong.

6. Increasing compute capacity for an app by adding instances of resources such as virtual machines is called [answer choice].

- horizontal scaling

Scaling horizontally increases compute capacity by adding instances of resources, such as adding virtual machines to the configuration. You scale vertically by adding RAM or CPUs to a virtual machine. Disaster recovery keeps data and other assets safe in the event of a disaster. High availability minimizes downtime when things go wrong.

7. What are cloud-based backup services, data replication, and geo-distribution features of?

- a disaster recovery plan

Disaster recovery uses services, such as cloud-based backup, data replication, and geo-distribution, to keep data and code safe in the event of a disaster.

8. An example of [answer choice] is automatically scaling an application to ensure that the application has the resources needed to meet customer demands.

- elasticity

Elasticity refers to the ability to scale resources as needed, such as during business hours, to ensure that an application can keep up with demand, and then reducing the available resources during off-peak hours. Agility refers to the ability to deploy new applications and services quickly. High availability refers to the ability to ensure that a service or application remains available in the event of a failure. Geo-distribution makes a service or application available in multiple geographic locations that are typically close to your users.

9. Which cloud service model provides you with the most control over the hardware that runs applications?

- infrastructure as a service (IaaS)

IaaS is the most flexible category of cloud services. It aims to give you complete control over the hardware that runs applications. Users do not control the operating system and do not configure the underlying servers in PaaS. With SaaS, you are using as-is software hosted in the cloud, instead of creating a platform to host a software yourself.

10. In a platform as a service (PaaS) model, which two components are the responsibility of the cloud service provider? Each correct answer presents a complete solution.

- operating system
- physical network

In PaaS, the cloud provider is responsible for the operating system, physical datacenter, physical hosts, and physical network. In PaaS, the customer is responsible for accounts and identities.

11. Which type of cloud service model is typically licensed through a monthly or annual subscription?

- software as a service (SaaS)

SaaS is software that is centrally hosted and managed for you and your users or customers. Usually, one version of the application is used for all customers, and it is licensed through a monthly or annual subscription. PaaS and IaaS use a consumption-based model, so you only pay for what you use.

12. You need to focus on application development rather than configuration and management of servers.

Which cloud service model should you use?

- platform as a service (PaaS)

With PaaS, users can focus on application development because the cloud provider handles all the platform management. In SaaS, the cloud provider manages all aspects of the application environment, such as virtual machines, networking resources, data storage, and applications. IaaS is the closest service model to managing physical servers.

13. Which cloud service model is used by Azure SQL Database?

- platform as a service (PaaS)

Azure SQL Database is a PaaS database engine.


14. Which type of cloud service are virtual networks?

- infrastructure as a service (IaaS)

IaaS helps you reduce the cost and complexity of maintaining a physical server and its datacenter infrastructure. Virtual networks are part of the IaaS cloud service.

15. Which two factors affect Azure costs? Each correct answer presents a complete solution.

- resource location
- resource usage

Usage meters, such as CPU time, disk size, and write operations, are used to calculate your bill for an Azure resource. Deleting or deallocating a resource means that you will no longer be billed for it. Different regions can have different associated prices. Resources cost the same no matter the time of day or the day of the week.

16. Which are two common scenarios for using resource tags? Each correct answer presents a complete solution.

- associating costs with different environments
- categorizing costs by department

You can use tags to categorize costs by department, such as human resources, marketing, or finance, or by environment, such as test or production. Resizing underutilized virtual machines is a good cost saving measure and provisioning resources in lower cost regions is a good practice, but resource tags do not help with this.

17. You need to associate the costs of resources to different groups within an organization without changing the location of the resources.

What should you use?

- resource tags

Resource tags can be used to group billing data and categorize costs by runtime environment, such as billing usage for virtual machines running in a production environment.

18. Your organization plans to deploy several production virtual machines that will have consistent resource usage throughout the year.

What can you use to minimize the costs of the virtual machines without reducing the functionality of the virtual machines?

- Azure Reservations

Azure Reservations offers discounted prices on certain Azure services. Azure Reservations can save you up to 72 percent compared to pay-as-you-go prices. To receive a discount, you can reserve services and resources by paying in advance.Spending limits can suspend a subscription when the spend limit is reached.

19. What can be applied to a resource to prevent accidental deletion?

- a resource lock

A resource lock prevents resources from being accidentally deleted or changed. Resource tags offer the custom grouping of resources. Policies enforce different rules across all resource configurations so that the configurations stay compliant with corporate standards. An initiative is a way of grouping related policies together.

20. What can you use to ensure that new and existing Azure resources stay in compliance with corporate standards?

- Azure Policy

Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit resources. These policies enforce different rules across all resource configurations so that the configurations stay compliant with corporate standards.

21. You need to recommend a solution for Azure virtual machine deployments. The solution must enforce company standards on the virtual machines.

What should you include in the recommendation?

- Azure Policy

Azure policies will allow you to enforce company standards on new virtual machines when combined with Azure VM Image Builder and Azure Compute Gallery. By using Azure Policy and role-based access control (RBAC) assignments, enterprises can enforce standards on Azure resources. But on virtual machines, these mechanisms only affect the control plane or the route to the virtual machine.

22. What can you use to restrict the deployment of a virtual machine to a specific location?

- Azure Policy

Azure Policy can help to create a policy for allowed regions, which enables you to restrict the deployment of virtual machines to a specific location.

23. What can you use to define the resources you want to provision in a declarative JSON format?

- Azure Resource Manager (ARM) templates

By using ARM templates, you can describe the resources you want to use in a declarative JSON format.

24. What can you use to create resources in Azure and includes a validation step to ensure all resources are created in a specific order based on dependencies, in parallel and idempotent?

- Azure Resource Manager (ARM) templates

ARM templates define an application's infrastructure requirements for a repeatable deployment that is done in a consistent manner. A validation step ensures that all resources can be created in the proper order based on dependencies, in parallel and idempotent.

25. What provides recommendations to reduce the cost of Azure resources?

- Azure Advisor

Azure Advisor analyzes the account usage and makes recommendations based on its set and configured rules.

26. You have a team of Linux administrators that need to manage the resources in Azure. The team wants to use the Bash shell to perform the administration.

What should you recommend?

- Azure CLI

Azure CLI allows you to use the Bash shell to perform administrative tasks. Bash is used in Linux environments, so a Linux administrator will probably be more comfortable performing command-line administration from Azure CLI.

27. You need to review the root cause analysis (RCA) report for a service outage that occurred last week.

Where should you look for the report?

- Azure Service Health

After an outage, Service Health provides official incident reports called root cause analysis (RCA), which you can share with stakeholders.

28. You need to create a custom solution that uses thresholds to trigger autoscaling functionality to scale an app up or down to meet user demand.

What should you include in the solution?

- Azure Monitor

Azure Monitor is a platform that collects metric and logging data, such as CPU percentages. The data can be used to trigger autoscaling.

29. What can you use to get notification about an outage in a specific Azure region?

- Azure Service Health

Service Health notifies you of Azure-related service issues, such as region-wide downtime.

30. What can you apply to an Azure virtual machine to ensure that users cannot change or delete the resource?

- a lock

Incorrect: A user-assigned managed identity –– Adding an identity will not add the ability to change or delete the resource.
Correct: A lock –– A resource lock will meet both requirements.
Incorrect: A tag –– A tag will not meet the requirements.
Incorrect: Conditional Access –– Conditional Access will not meet the requirements.

31. Which feature in the Microsoft Purview governance portal should you use to manage access to data sources and datasets?

- Data Policy

Incorrect: Data Catalog –– This enables data discovery.
Incorrect: Data Sharing –– This shares data within and between organizations.
Incorrect: Data Estate Insights –– This accesses data estate health.
Correct: Data Policy –– This governs access to data.

32. [Answer choice] is the logical container used to combine and organize Azure resources.

- a resource group

Resources are combined into resource groups, which act as a logical container into which Azure resources like web apps, databases, and storage accounts, are deployed and managed.

33. [Answer choice] are physically separate datacenters within an Azure region.

- Availability zones

Availability zones are physically separate datacenters within an Azure region. Each availability zone is made up of one or more datacenters equipped with independent power, cooling, and networking.

34. Which two components are created in an Azure subscription? Each correct answer presents a complete solution.

- resource groups
- resources

Resources can only be associated with a single subscription. Subscriptions may be grouped into management groups. An account may be associated with multiple subscriptions.

35. What is an Azure Storage account named storage001 an example of?

- a resource

A resource is a manageable item that is available through Azure. Virtual machines, storage accounts, web apps, databases, and virtual networks are examples of resources.

36. Which resource can you use to manage access, policies, and compliance across multiple subscriptions?

- management groups

Management groups can be used in environments that have multiple subscriptions to streamline the application of governance conditions.
Resource groups can be used to organize Azure resources.
Administrative units are used to delegate the administration of Azure AD resources, such as users and groups.
Accounts are used to provide access to resources

37. [Answer choice] is the deployment and management service for Azure.

- Azure Resource Manager (ARM)

ARM is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in an Azure subscription. You use management features, such as access control, resource locks, and resource tags, to secure and organize resources after deployment.

38. Which Azure compute service can you use to deploy and manage a set of identical virtual machines?

- Azure Virtual Machine Scale Sets

Virtual Machine Scale Sets are an Azure compute resource that you can use to deploy and manage and scale a set of identical virtual machines.

39. Which scenario is a use case for a VPN gateway?

- connecting an on-premises datacenter to an Azure virtual network

A VPN gateway is a type of virtual network gateway. Azure VPN Gateway instances are deployed to a dedicated subnet of a virtual network. You can use them to connect on-premises datacenters to virtual networks through a Site-to-Site (S2S) VPN connection.

40. You need to allow resources on two different Azure virtual networks to communicate with each other.

What should you configure?

- peering

You can link virtual networks together by using virtual network peering. Peering enables resources in each virtual network to communicate with each other.

41. Which two services can you use to establish network connectivity between an on-premises network and Azure resources? Each correct answer presents a complete solution.

- Azure VPN Gateway
- ExpressRoute

ExpressRoute connections and Azure VPN Gateway are two services that you can use to connect an on-premises network to Azure. Bastion provides a web interface to remotely administer Azure virtual machines by using SSH/RDP. Azure Firewall is a stateful firewall service used to protect virtual networks.

42. What are two services that allow you to run applications in containers? Each correct answer presents a complete solution.

- Azure Container Instances
- Azure Kubernetes Service (AKS)

Containers are a virtualization environment. Much like running multiple virtual machines on a single physical host, you can run multiple containers on a single physical or virtual host. Unlike virtual machines, you do not manage the operating system for a container.

43. Which Azure Blob storage tier stores data offline and offers the lowest storage costs and the highest costs to access data?

- Archive

The Archive storage tier stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data. The Hot storage tier is optimized for storing data that is accessed frequently. Data in the Cool access tier can tolerate slightly lower availability, but still requires high durability, retrieval latency, and throughput characteristics similar to hot data.

44. Which Azure Blob storage service tier has the highest storage costs and the fastest access times for reading and writing data?

- Hot

The Hot tier is optimized for storing data that is accessed frequently. The Cool access tier has a slightly lower availability SLA and higher access costs compared to hot data, which are acceptable trade-offs for lower storage costs. Archive storage stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data.

45. Which two protocols can be used to access Azure file shares? Each correct answer presents a complete solution.

- Network File System (NFS)
- Server Message Block (SMB)

Azure Files offers fully managed file shares in the cloud that are accessible via industry-standard SMB and NFS protocols.

46. What is the purpose of defense in depth?

- to use several layers of protection to prevent information from being accessed by unauthorized users

The objective of defense in depth is to use several layers of protection to prevent information from being accessed or stolen by unauthorized users.

47. Which type of strategy uses a series of mechanisms to slow the advancement of an attack that aims to gain unauthorized access to data?

- defense in depth

A defense in depth strategy uses a series of mechanisms to slow the advancement of an attack that aims to gain unauthorized access to data. The principle of least privilege means restricting access to information to only the level that users need to perform their work. A DDoS attack attempts to overwhelm and exhaust an application's resources. The perimeter layer is about protecting an organization's resources from network-based attacks.

48. Which Microsoft Entra feature can you use to ensure that users can only access Microsoft Office 365 applications from approved client applications?

- Conditional Access

Conditional Access allows administrators to control, allow, or deny access to resources based on certain signals. You can require that access to certain applications only be allowed if the users are using an approved client application. MFA is a process whereby a user is prompted during the sign-in process for an additional form of identification. Examples include a code on their mobile phone or a fingerprint scan.

49. What can you use to sync identities from an on-premises Active Directory Domain Services (AD DS) domain to Microsoft Entra?

- Microsoft Entra Connect

Microsoft Entra Connect syncs user identities from an on-premises Active Directory Domain Services (AD DS) domain to Microsoft Entra. Microsoft Entra Connect allows you to use features such as single sign-on (SSO), MFA, and self-service password reset (SSPR) in both systems. SSPR prevents users from using known compromised passwords.

50. What can you use to ensure that users authenticate by using multi-factor authentication (MFA) when they attempt to sign in from a specific location?

- Conditional Access

Conditional Access can use signals to determine information about authentication attempts, and then determine whether to block access or require additional verifications, such as MFA.


