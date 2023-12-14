1. Data in an Azure storage account is replicated 3 times in the primary region.

- Yes

Explanation
Azure Storage always stores multiple copies of your data so that it is protected from planned and unplanned events, including transient hardware failures, network or power outages, and massive natural disasters. Redundancy ensures that your storage account meets the Service-Level Agreement (SLA) for Azure Storage even in the face of failures.

2. You want to deploy a file share that can be accessed from multiple Azure virtual machines without setting up a separate file server. Which Azure service can you use to achieve this?

- Azure Storage Account

Explanation
This is a tricky question. Azure Storage Account is the correct answer as it provides Azure Files, which can be used to create a file share accessible from multiple virtual machines. Remember, we always need to choose the BEST option from the ones provided. Even though Azure Files would've been the ideal option, but since its not one of the options we need to go with the best option possible.

Other Options:
- Azure SQL Database is a database service and not suitable for sharing files among multiple virtual machines.
- Azure Virtual Network is a networking service and not suitable for file sharing.
- Azure App Service is a platform for hosting web applications and not suitable for file sharing.

3. Which of the following affect costs in Azure? (Choose 2)

- Location
- Instance Size

Explanation
According to the official docs:

The instance size and the location (eg -US or Europe etc ) affect the prices. The knowledge center is completely free to use, and you aren't charged for an Availability Zone.

#

1. Which of the following Azure storage solutions meets ALL the following requirements:

1) The ability to handle unstructured data (document, graph, key-value)
2) Automatically index all data, regardless of the data model.
3) Multi-region writes and data distribution to any Azure region.

- Azure Cosmos DB

Explanation

From the official documentation:
Today's applications are required to be highly responsive and always online. To achieve low latency and high availability, instances of these applications need to be deployed in datacenters that are close to their users. Applications need to respond in real time to large changes in usage at peak hours, store ever increasing volumes of data, and make this data available to users in milliseconds.

Azure Cosmos DB is Microsoft's globally distributed, multi-model database service. With the click of a button, Cosmos DB enables you to elastically and independently scale throughput and storage across any number of Azure regions worldwide. You can elastically scale throughput and storage, and take advantage of fast, single-digit-millisecond data access using your favorite API including: SQL, MongoDB, Cassandra, Tables, or Gremlin. Cosmos DB provides comprehensive service level agreements (SLAs) for throughput, latency, availability, and consistency guarantees, something no other database service offers.

Azure Cosmos DB is a great way to store unstructured and JSON data. Combined with Azure Functions, Cosmos DB makes storing data quick and easy with much less code than required for storing data in a relational database.

2. Which of the following services would you help achieve the following:

1) Create and manage a group of load balanced VMs.
2) Provide high availability and application resiliency by distributing VMs across availability zones
3) Allows your application to automatically scale as resource demand changes

- Azure Scale Sets

Explanation

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/5cb71a0a-dfde-4646-9410-9892b8d438d2)


3. When should you scale out your deployment?

- When you need additional Virtual Machines / computers to speed up your application

Explanation

Scale Out: A scale out operation is the equivalent of creating multiple copies of your web site and adding a load balancer to distribute the demand between them. When you scale out a web site in Azure, there is no need to configure load balancing separately since this is already provided by the platform

4. When computing and processing demand increases beyond an on-premises datacenter’s capabilities, businesses can easily use the ___________ cloud to instantly scale capacity up or down to handle excess capacity.

- Public

Explanation

When computing and processing demand increases beyond an on-premises datacenter’s capabilities, businesses can use the cloud to instantly scale capacity up or down to handle excess capacity. It also allows them to avoid the time and cost of purchasing, installing, and maintaining new servers that they may not always need.


5. Which of the following factors can affect the availability of an Azure service under the SLA?

- Natural disasters
- Planned maintenance activities
- Hardware or software failures within Azure

Explanation

The Service Level Agreement (SLA) for Azure services guarantees a certain level of availability, which is expressed as a percentage of uptime over a specific period of time. However, certain factors can affect the availability of an Azure service, even if it is covered under the SLA.

Network disruptions outside of Azure, such as issues with your own internet service provider (ISP), can impact your ability to connect to Azure services and can affect their availability. However, these types of disruptions are outside of Microsoft's control, so they are NOT considered in the Azure SLA.

Planned maintenance activities, which are performed to update or maintain Azure services, can cause temporary downtime. However, Microsoft typically schedules maintenance activities during off-peak hours to minimize their impact on availability.

Hardware or software failures within Azure can cause disruptions to service availability. Microsoft implements measures to minimize the impact of these failures, such as redundancy and failover mechanisms, but they can still occur.

Natural disasters, such as earthquakes or hurricanes, can also impact the availability of Azure services, but this is outside of Microsoft's control.

6. Is an internet connection necessary for using cloud computing?

- No

Explanation

The answer is no. Cloud computing services can be used over the internet, but they can also be used through private networks or dedicated connections, such as Azure ExpressRoute, which provides a dedicated, private network connection between on-premises infrastructure and Azure data centers. Some cloud services can also be accessed offline or through local networks.

For example, Azure Stack is a hybrid cloud solution that allows you to use Azure services on-premises, without an internet connection. This can be useful for organizations that have limited or unreliable internet connectivity but still want to take advantage of the benefits of cloud computing.

Similarly, some cloud providers offer edge computing solutions that allow you to run cloud workloads on devices located at the edge of the network, such as in a factory or remote location, without needing a constant internet connection.

In general, however, most cloud services do require an internet connection to access and use them. This is because the underlying infrastructure and resources that support these services are typically hosted in data centers that are connected to the internet.

7. Is it possible to modify an Azure resource that has a delete lock applied to it?

- Yes, it is possible for the admin to do so

Explanation

As an administrator, you can lock an Azure subscription, resource group, or resource to protect them from accidental user deletions and modifications. The lock overrides any user permissions.

You can set locks that prevent either deletions or modifications. In the portal, these locks are called Delete and Read-only. In the command line, these locks are called CanNotDelete and ReadOnly.

CanNotDelete means authorized users can read and modify a resource, but they can't delete it.

ReadOnly means authorized users can read a resource, but they can't delete or update it. Applying this lock is similar to restricting all authorized users to the permissions that the Reader role provides.


8. You have managed an app that you developed and deployed On-Prem for a long time, but would now like to move it to Azure and be relieved of all the manual administration and maintenance. Which of the following buckets would be most suitable for your use case?

- Platform as a Service (PaaS)

Explanation

Platform as a service (PaaS) is a complete development and deployment environment in the cloud, with resources that enable you to deliver everything from simple cloud-based apps to sophisticated, cloud-enabled enterprise applications. You purchase the resources you need from a cloud service provider on a pay-as-you-go basis and access them over a secure Internet connection.

Like IaaS, PaaS includes infrastructure—servers, storage, and networking—but also middleware, development tools, business intelligence (BI) services, database management systems, and more. PaaS is designed to support the complete web application lifecycle: building, testing, deploying, managing, and updating.

PaaS allows you to avoid the expense and complexity of buying and managing software licenses, the underlying application infrastructure and middleware, container orchestrators such as Kubernetes, or the development tools and other resources. You manage the applications and services you develop, and the cloud service provider typically manages everything else.

9. For all Virtual Machines that have two or more instances deployed across two or more Availability Zones in the same Azure region,  you will have Virtual Machine Connectivity to at least one instance guaranteed at least _______ of the time.

- 99.99%

Explanation

SLA for Virtual Machines

For all Virtual Machines that have two or more instances deployed across two or more Availability Zones in the same Azure region, we guarantee you will have Virtual Machine Connectivity to at least one instance at least 99.99% of the time.

For all Virtual Machines that have two or more instances deployed in the same Availability Set or in the same Dedicated Host Group, we guarantee you will have Virtual Machine Connectivity to at least one instance at least 99.95% of the time.

For any Single Instance Virtual Machine using Premium SSD or Ultra Disk for all Operating System Disks and Data Disks, we guarantee you will have Virtual Machine Connectivity of at least 99.9%.

For any Single Instance Virtual Machine using Standard SSD Managed Disks for Operating System Disk and Data Disks, we guarantee you will have Virtual Machine Connectivity of at least 99.5%.

For any Single Instance Virtual Machine using Standard HDD Managed Disks for Operating System Disks and Data Disks, we guarantee you will have Virtual Machine Connectivity of at least 95%.

10. Select the characteristics of the Public Cloud from the following:

- Metered pricing
- No captial expenditure to scale up
- Applications can be quickly provisioned and deprovisioned

Explaination:

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/0d203b0c-690b-4073-b855-3a01e13e2fda)

With the public cloud, you get pay-as-you-go pricing and you pay only for what you use, no CapEx costs are involved.

With the public cloud, you have self-service management. You are responsible for the deployment and configuration of the cloud resources such as virtual machines or web sites. The underlying hardware that hosts the cloud resources is managed by the cloud provider.

Incorrect Answers:

Hardware must be purchased for start-up and maintenance - You don't have to purchase any hardware on the public cloud. The underlying hardware is shared so you could have multiple customers using cloud resources hosted on the same physical hardware. Moreover, this is a characteristic of the private cloud.

Unsecured Connections - Connections to the public cloud are secure.

Organizations are responsible for hardware maintenance and updates - This is a characteristic of the Private Cloud.

11. True or False: Resources don't inherit the tags you apply to a resource group or a subscription.

- True

Explanation

Yes, this is true. Resources don't inherit the tags you apply to a resource group or a subscription. To apply tags from a subscription or resource group to the resources, see Azure Policies - tags.

12. Can you apply a read-only lock to an Azure resource that already has a delete lock applied to it?


- Yes, but only by the owner of the subscription

Explanation

As an administrator, you can lock an Azure subscription, resource group, or resource to protect them from accidental user deletions and modifications. The lock overrides any user permissions.

You can set locks that prevent either deletions or modifications. In the portal, these locks are called Delete and Read-only. In the command line, these locks are called CanNotDelete and ReadOnly.

CanNotDelete means authorized users can read and modify a resource, but they can't delete it.

ReadOnly means authorized users can read a resource, but they can't delete or update it. Applying this lock is similar to restricting all authorized users to the permissions that the Reader role provides.

Try this out in the Azure portal, you should be able to add a read-only lock to a resource having a CanNotDelete lock already!

13. When you as a consumer are implementing a Software as a Service (SaaS) solution, you are responsible for configuring high availability.

Review the bolded text. If the statement is already correct, select "No change is needed". If the statement is incorrect, choose the option below that would make the statement correct.

- Configurating the SaaS solution

Explanation

Software as a service (SaaS) allows users to connect to and use cloud-based apps over the Internet. Common examples are email, calendaring, and office tools (such as Microsoft Office 365).

SaaS provides a complete software solution that you purchase on a pay-as-you-go basis from a cloud service provider. You rent the use of an app for your organization, and your users connect to it over the Internet, usually with a web browser. All of the underlying infrastructure, middleware, app software, and app data are located in the service provider’s data center. The service provider manages the hardware and software, and with the appropriate service agreement, will ensure the availability and the security of the app and your data as well. SaaS allows your organization to get quickly up and running with an app at minimal upfront cost.

If you’ve used a web-based email service such as Outlook, Hotmail, or Yahoo! Mail, then you’ve already used a form of SaaS. With these services, you log into your account over the Internet, often from a web browser. The email software is located on the service provider’s network, and your messages are stored there as well. You can access your email and stored messages from a web browser on any computer or Internet-connected device.

The previous examples are free services for personal use. For organizational use, you can rent productivity apps, such as email, collaboration, and calendaring; and sophisticated business applications such as customer relationship management (CRM), enterprise resource planning (ERP), and document management. You pay for the use of these apps by subscription or according to the level of use.

14. A resource group can contain resources from multiple Azure regions.

- Yes

Explanation:

Resources from multiple different regions can be placed in a resource group. The resource group only contains metadata about the resources it contains.

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/d48da6de-4adc-43ce-8a52-9bff54d58f91)

15. Which of the following factors influence the cost of Azure resources? (Select all that apply)

- Comsumption
- Resource type
- Geography

Explanation

The correct answers are - Resource type, Consumption, and Geography. These factors influence the cost of Azure resources. Maintenance, on the other hand, is an important aspect of managing resources to control costs but does not directly influence the cost of the resources themselves.

16. During live telecasts of football matches, streaming platforms sometimes experience massive spikes in viewerships and users visiting their websites when a goal is scored. Which of the following would be beneficial to deal with such expected demand of resources?

- Serverless Computing

Explanation

Serverless computing enables developers to build applications faster by eliminating the need for them to manage infrastructure. With serverless applications, the cloud service provider automatically provisions, scales, and manages the infrastructure required to run the code.

While understanding the definition of serverless computing, it’s important to note that servers are still running the code. The serverless name comes from the fact that the tasks associated with infrastructure provisioning and management are invisible to the developer. This approach enables developers to increase their focus on the business logic and deliver more value to the core of the business (IMPORTANT). Serverless computing helps teams increase their productivity and bring products to market faster, and it allows organizations to better optimize resources and stay focused on innovation.

17. Which of the following actions can help you reduce your Azure costs?

- Reducing the amount of data transferred between Azure regions

Explanation
Reducing the amount of data transferred between Azure regions can help reduce costs by minimizing data egress charges.

Other options:
Deploying more virtual machines: This can actually increase costs if they are not utilized efficiently.
Enabling automatic scaling: This can help optimize resource usage and reduce costs, but it depends on the specific workload and usage patterns.
Keeping virtual machines running 24/7: This can result in unnecessary costs, especially if they are not utilized all the time. It is recommended to use automation to start and stop VMs based on usage patterns.

















