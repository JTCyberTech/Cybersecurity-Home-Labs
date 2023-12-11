1. You need to compare the costs of running an application in an on-premises datacenter with the costs of running the application in Azure.

What should you use to assist you?

-- Total Cost of Ownership (TCO) Calculator

The TCO Calculator helps you estimate the cost savings over time of operating a solution in Azure compared to operating in an on-premises datacenter.

2. What can be applied to a resource to prevent accidental deletion?

- a resource lock

A resource lock prevents resources from being accidentally deleted or changed. Resource tags offer the custom grouping of resources. Policies enforce different rules across all resource configurations so that the configurations stay compliant with corporate standards. An initiative is a way of grouping related policies together.

3. You need to recommend a solution for Azure virtual machine deployments. The solution must enforce company standards on the virtual machines.

What should you include in the recommendation

- Azure Policy

Azure policies will allow you to enforce company standards on new virtual machines when combined with Azure VM Image Builder and Azure Compute Gallery. By using Azure Policy and role-based access control (RBAC) assignments, enterprises can enforce standards on Azure resources. But on virtual machines, these mechanisms only affect the control plane or the route to the virtual machine.

4. What can you use to ensure that a development team can only create virtual machines of a certain size?

- Azure Policy

Azure Policy enables you to define both individual policies and groups of related policies called initiatives. Azure Policy evaluates your resources and highlights resources that are not compliant with the policies you created. Azure Policy can also prevent noncompliant resources from being created.

5. Which two actions can be performed by using Azure portal? Each correct answer presents a complete solution.

- Create new resources.
- Create Microsoft Entra user.

The Azure portal provides a GUI to view all the services you are using, create new services, configure your services, and view reports.

6. What can you use to define the resources you want to provision in a declarative JSON format?

- Azure Resource Manager (ARM) templates

7. Which management layer accepts requests from any Azure tool or API and enables you to create, update, and delete resources in an Azure account?

- Azure Resource Manager (ARM)

ARM is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in an Azure account.

8. What can you use to create resources in Azure and includes a validation step to ensure all resources are created in a specific order based on dependencies, in parallel and idempotent?

- Azure Resource Manager (ARM) templates

ARM templates define an application's infrastructure requirements for a repeatable deployment that is done in a consistent manner. A validation step ensures that all resources can be created in the proper order based on dependencies, in parallel and idempotent.

9. Which two tools can you use to create a new Azure virtual machine from a mobile device that runs Android? Each correct answer presents complete solution.

- PowerShell in Azure Cloud Shell
- the Azure portal

The Azure portal can run on devices that have the Android operating system installed. The browser can be any type, such as Internet Explorer 11, Chrome, Firefox, or Safari (all the latest versions). When you visit the portal, you will see Cloud Shell. Users can then access Bash and PowerShell from within Cloud Shell. You can use Bash and PowerShell to create Azure virtual machines.

10. What provides recommendations to reduce the cost of Azure resources?

- Azure Advisor

Azure Advisor analyzes the account usage and makes recommendations based on its set and configured rules.

11. You have a team of Linux administrators that need to manage the resources in Azure. The team wants to use the Bash shell to perform the administration.

What should you recommend?

- Azure CLI

Azure CLI allows you to use the Bash shell to perform administrative tasks. Bash is used in Linux environments, so a Linux administrator will probably be more comfortable performing command-line administration from Azure CLI.

12. You need to review the root cause analysis (RCA) report for a service outage that occurred last week.

Where should you look for the report?

- Azure Service Health

After an outage, Service Health provides official incident reports called root cause analysis (RCA), which you can share with stakeholders.

13. You need to create a custom solution that uses thresholds to trigger autoscaling functionality to scale an app up or down to meet user demand.

What should you include in the solution?

- Azure Monitor

Azure Monitor is a platform that collects metric and logging data, such as CPU percentages. The data can be used to trigger autoscaling.

14. What should you proactively review and act on to avoid service interruptions, such as service retirements and breaking changes?

-- health advisories

Health advisories are issues that require that you take proactive action to avoid service interruptions, such as service retirements and breaking changes. Service issues are problems such as outages that require immediate actions.

15. What can you use to automatically detect performance anomalies for web apps?

- Azure Application Insights

Application Insights is a feature of Azure Monitor that allows you to monitor running applications, automatically detect performance anomalies, and use built-in analytics tools to see what users do on an app.

16. What can you apply to an Azure virtual machine to ensure that users cannot change or delete the resource?

- a lock

Incorrect: A user-assigned managed identity –– Adding an identity will not add the ability to change or delete the resource.

Correct: A lock –– A resource lock will meet both requirements.
Incorrect: A tag –– A tag will not meet the requirements.
Incorrect: Conditional Access –– Conditional Access will not meet the requirements.
Protect your Azure resources with a lock - Azure Resource Manager | Microsoft Learn

17. Which feature in the Microsoft Purview governance portal should you use to manage access to data sources and datasets?

- Data Policy

Incorrect: Data Catalog –– This enables data discovery.
Incorrect: Data Sharing –– This shares data within and between organizations.
Incorrect: Data Estate Insights –– This accesses data estate health.
Correct: Data Policy –– This governs access to data.

18. [Answer choice] is the logical container used to combine and organize Azure resources.

- a resource group

Resources are combined into resource groups, which act as a logical container into which Azure resources like web apps, databases, and storage accounts, are deployed and managed.

19. In a region pair, a region is paired with another region in the same [answer choice].

-- geography

Each Azure region is always paired with another region within the same geography, such as US, Europe, or Asia, at least 300 miles away.

20. Which two components are created in an Azure subscription? Each correct answer presents a complete solution.

- resource groups
- resources

Resources can only be associated with a single subscription. Subscriptions may be grouped into management groups. An account may be associated with multiple subscriptions.

21. For which resource does Azure generate separate billing reports and invoices by default?

-- subscriptions

Azure generates separate billing reports and invoices for each subscription so that you can organize and manage costs. Resource groups can be used to group costs, but you will not receive a separate invoice for each resource group. Management groups are used to efficiently manage access, policies, and compliance for subscriptions. You can set up billing profiles to roll up subscriptions into invoice sections, but this requires customization.

22. Which resource can you use to manage access, policies, and compliance across multiple subscriptions?

- management groups

Management groups can be used in environments that have multiple subscriptions to streamline the application of governance conditions.
Resource groups can be used to organize Azure resources.
Administrative units are used to delegate the administration of Azure AD resources, such as users and groups.
Accounts are used to provide access to resources

23. Which Azure resource is a software emulation of a physical computer that includes a virtual processor, memory, storage, and networking resources?

- a virtual machine

Virtual machines are software emulations of physical computers. They include a virtual processor, memory, storage, and networking resources. Virtual machines host an operating system, and you can install and run software just like on a physical computer.

24. Which scenario is a use case for a VPN gateway?

- connecting an on-premises datacenter to an Azure virtual network

A VPN gateway is a type of virtual network gateway. Azure VPN Gateway instances are deployed to a dedicated subnet of a virtual network. You can use them to connect on-premises datacenters to virtual networks through a Site-to-Site (S2S) VPN connection.


25. What can you use to provide Mac and Android users with access to a Windows environment that will run Windows-based applications?

-- Azure Virtual Desktop

Azure Virtual Desktop is a desktop and application virtualization service that runs in the cloud. It enables your users to use a cloud-hosted version of Windows from any location. Azure Virtual Desktop works across devices such as Windows, Mac, iOS, Android, and Linux. It works with apps that you can use to access Remote Desktops and apps. You can also use most modern browsers to access Azure Virtual Desktop-hosted experiences.

26. What are two services that allow you to run applications in containers? Each correct answer presents a complete solution.

- Azure Container Instances
- Azure Kubernetes Service (AKS)

Containers are a virtualization environment. Much like running multiple virtual machines on a single physical host, you can run multiple containers on a single physical or virtual host. Unlike virtual machines, you do not manage the operating system for a container.

27. Which storage service should you use to store thousands of files containing text and images?

- Azure Blob storage

Azure Blob storage is an object storage solution that you can use to store massive amounts of unstructured data, such as text or binary data.

28. Which Azure Blob storage tier stores data offline and offers the lowest storage costs and the highest costs to access data?

- Archive

The Archive storage tier stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data. The Hot storage tier is optimized for storing data that is accessed frequently. Data in the Cool access tier can tolerate slightly lower availability, but still requires high durability, retrieval latency, and throughput characteristics similar to hot data.

29. Which Azure Blob storage service tier has the highest storage costs and the fastest access times for reading and writing data?

- Hot

The Hot tier is optimized for storing data that is accessed frequently. The Cool access tier has a slightly lower availability SLA and higher access costs compared to hot data, which are acceptable trade-offs for lower storage costs. Archive storage stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data.

30. Which Azure Storage service should you use to store unstructured files, such as images, that will be served on webpages?

- Azure Blob storage

Azure Blob storage is an object storage solution that you can use to store massive amounts of unstructured data, such as text or binary data.


31. What is the purpose of defense in depth?

- to use several layers of protection to prevent information from being accessed by unauthorized users

The objective of defense in depth is to use several layers of protection to prevent information from being accessed or stolen by unauthorized users.

32. What can you use to ensure that a user can only access applications from compliant devices?

- Conditional Access

Conditional Access is a feature that Microsoft Entra uses to allow or deny access to resources based on identity signals, such as the device being used. SSO enables a user to sign in one time and use that credential to access multiple resources and applications from different providers. MFA is a process whereby a user is prompted during the sign-in process for an additional form of identification. Hybrid identity solutions create a common user identity for authentication and authorization to all resources, regardless of location.

33. What can you use to allow a user to manage all the resources in a resource group?

- Azure role-based access control (RBAC)

Azure RBAC allows you to assign a set of permissions to a user or group. Resource tags are used to locate and act on resources associated with specific workloads, environments, business units, and owners. Resource locks prevent the accidental change or deletion of a resource. Key Vault is a centralized cloud service for storing an application secrets in a single, central location.

34. To which object or level is an Azure role-based access control (RBAC) role applied?

-- scope

An Azure RBAC role is applied to a scope, which is a resource or set of resources that the access applies to. Resource locks prevent the accidental change or deletion of a resource. Resource tags are used to locate and act on resources associated with specific workloads, environments, business units, and owners. Policies enforce different rules across resource configurations so that the configurations stay compliant with corporate standards.

35. Which type of strategy uses a series of mechanisms to slow the advancement of an attack that aims to gain unauthorized access to data?

- defense in depth

A defense in depth strategy uses a series of mechanisms to slow the advancement of an attack that aims to gain unauthorized access to data. The principle of least privilege means restricting access to information to only the level that users need to perform their work. A DDoS attack attempts to overwhelm and exhaust an application's resources. The perimeter layer is about protecting an organization's resources from network-based attacks.

36. What Microsoft Entra feature can you use to configure security authentication that requires users to use their mobile phone to sign in?

- multi-factor authentication (MFA)


MFA is the concept of requiring something more than only a password to sign in to an application. You can use the mobile phone to receive a phone call, text, or a code to get authenticated.

37. What are two characteristics of a consumption-based model? Each correct answer presents a complete solution.

- no upfront costs
- the ability to stop paying for resources that are no longer used

In a consumption-based model, you do not pay for anything until you start using resources, and you only pay for what you use. If you stop using a resource, you stop paying for it. High expenditures are usually associated with the purchase of the physical infrastructure, which is not needed in a consumption-based model.

38. Which two characteristics are common advantages of cloud computing? Each correct answer presents a complete solution.

- geo-distribution
- high availability

Cloud-based apps can provide a continuous user experience with no apparent downtime, even when things go wrong. You can deploy apps and data to regional datacenters around the globe, thereby ensuring that your customers always have the best performance in their region. Apps in cloud computing can scale vertically and horizontally. In a public cloud model, you do not get physical access to servers, as they are managed by the cloud provider.

39. Why is cloud computing often less expensive than on-premises datacenters? Each correct answer presents a complete solution.

- 

40. What is an advantage of cloud computing compared to on-premises deployments?

- You can scale more quickly.

Cloud computing allows you to scale more quickly. Owning your own CPUs and having full access in the event of an internet outage are not features of cloud computing. Working from multiple workstations is not specific to cloud computing compared to an on-premises deployment.

41. [Answer choice] refers to upfront costs incurred one time, such as hardware purchases.

- Capital expenditures

Capital expenditures are one-time expenses that can be deducted over time. Operational expenditures are billed as you use services and a do not have upfront costs.

42. Increasing compute capacity for an app by adding RAM or CPUs to a virtual machine is called [answer choice].

- vertical scaling

You scale vertically to increase compute capacity by adding RAM or CPUs to a virtual machine. Scaling horizontally increases compute capacity by adding instances of resources, such as adding virtual machines to the configuration. Disaster recovery keeps data and other assets safe in the event of a disaster. High availability minimizes downtime when things go wrong.

43. Deploying and configuring cloud-based resources quickly as business requirements change is called [answer choice].

- agility

Agility means that you can deploy and configure cloud-based resources quickly as app requirements change. Scalability means that you can add RAM, CPU, or entire virtual machines to a configuration. Elasticity means that you can configure cloud-based apps to take advantage of autoscaling, so apps always have the resources they need. High availability means that cloud-based apps can provide a continuous user experience with no apparent downtime, even when things go wrong.

44. Increasing compute capacity for an app by adding instances of resources such as virtual machines is called [answer choice].

- horizontal scaling

Scaling horizontally increases compute capacity by adding instances of resources, such as adding virtual machines to the configuration. You scale vertically by adding RAM or CPUs to a virtual machine. Disaster recovery keeps data and other assets safe in the event of a disaster. High availability minimizes downtime when things go wrong.

45. What is high availability in a public cloud environment dependent on?

- the service-level agreement (SLA) that you choose

Different services have different SLAs. Sometimes different tiers of the same service will offer different SLAs, which can increase or decrease the promised availability.

46. In cloud computing, [answer choice] allows you to deploy applications to regional datacenters around the world.

- geo-location

You can deploy apps and data to regional datacenters around the globe, thereby ensuring that your customers always have the best performance in their region. This is referred to as geo-distribution.

47. Increasing the capacity of an application by adding additional virtual machine is called [answer choice].

- horizontal scaling

Scaling horizontally increases compute capacity by adding instances of resources, such as adding virtual machines to the configuration. You scale vertically to increase compute capacity by adding RAM or CPUs to a virtual machine. Agility refers to the ability to deploy new applications and services quickly. High availability minimizes downtime when things go wrong.

48. Which cloud service model provides you with the most control over the hardware that runs applications?

- infrastructure as a service (IaaS)

IaaS is the most flexible category of cloud services. It aims to give you complete control over the hardware that runs applications. Users do not control the operating system and do not configure the underlying servers in PaaS. With SaaS, you are using as-is software hosted in the cloud, instead of creating a platform to host a software yourself.

49. In which cloud service model is the customer responsible for managing the operating system?

Infrastructure as a service (IaaS)

IaaS consists of virtual machines and networking provided by the cloud provider. The customer is responsible for the OS and applications. The cloud provider is responsible for the OS in PaaS and SaaS.

50. Which cloud service model is used by Azure SQL Database?

- platform as a service (PaaS)

Azure SQL Database is a PaaS database engine.



