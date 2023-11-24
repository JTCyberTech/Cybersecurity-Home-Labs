# Practice exam covering Introduction to Azure Core Concepts and Service

1. Tradewind Traders current on-premises datacenter has several hundred servers and available resources in the datacenter are currently very low. Management has asked you to research a solution that will allow for increased resources but will keep expenditure such as capital expenditure and operational expenditure at a minimum. What solution should you recommend?

`Yes`

2. Tradewind Traders is planning to migrate to Azure cloud services. The company currently operates multiple MySQL database solutions on-premises. Management has asked you to spend some time researching the MySQL features available in Azure specifically the ability to perform automatic backups and point in time restores. You have determined that these features are available for MySQL in Azure. 

For how many days are point-in-time restores supported for MySQL in Azure?

`35`: Azure database for MySQL supports Automatic backups and point-in-time-restore for up to 35 days. Try going back and reviewing Introduction to Microsoft Azure Fundamentals.

3. Tradewind Traders is planning to migrate to Azure cloud services. Management has asked you to research some of the main features of cloud services. Based on your research, which of the following statements is correct?

``

4. Tradewind Traders is planning to migrate some of their data and resources to Azure cloud services, Management has decided to only make use of the Platform as a Service (PaaS) offerings in Azure. You have been asked to design a migration plan. As part of this design, you have included the creation of Azure virtual machines, Azure SQL databases, and Azure Storage accounts

Does this design meet the requirements of the organization?

`No`: Platform as a service (PaaS) is a complete development and deployment environment in the cloud. PaaS includes infrastructure servers, storage, and networking as well as middleware, development tools, business intelligence (BI) services, database management systems, and more. PaaS is designed to support the complete web application lifecycle: building, testing, deploying, managing, and updating. However, virtual machines are examples of Infrastructure as a service (IaaS). IaaS is an instant computing infrastructure, provisioned and managed over the internet.

5. Tradewind Traders is planning to migrate to Azure cloud services but before they do management has asked you to spend some time exploring Azure features and solutions. Which of the following should be your first step?

`Create a subscription`: The first thing you create in Azure is a subscription. A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue. You get billed per subscription. Try going back and reviewing Microsoft Azure Fundamental Concepts & Architectural Components.

6. Tradewind Traders is planning to migrate some of their data and resources to Azure cloud services, Management has decided to only make use of the Platform as a Service (PaaS) offerings in Azure. You have been asked to design a migration plan. As part of this design, you have included the creation of Azure App Services and Azure virtual machines that will run MySQL Databases.

`No`: Azure App Service is a PaaS (Platform as a Service) service. However, Azure virtual machines are an IaaS (Infrastructure as a Service) service. Therefore, this design does not meet the requirements.

7. Tradewind Traders is planning to migrate to Azure cloud services, and you have been asked to do some research on Infrastructure as a Service. Which of the following is an example of IaaS?

`Azure virtual machine`: An Azure virtual machine is an example of Infrastructure as a Service (IaaS).

8. Tradewinds Traders is planning to migrate to Azure cloud services however management has questions concerning management and responsibilities once resources are migrated. You have identified three cloud service models. In which model does the cloud provider keep the hardware up to date but the operating system maintenance and network configuration are left to the cloud tenant? 

`IaaS`: IaaS is the cloud service model that is closest to managing physical servers. In this model, the cloud provider keeps the hardware up to date, but operating system maintenance and network configuration are left to the cloud tenant. 

9. Tradewinds Traders is planning to migrate to Azure cloud services but before they do you have been asked to do some research on cloud deployment models. Based on your research which of the following deployment models will provide the ability to share data, applications, and resources on-premises and in the Cloud

`Hybrid Cloud`: A hybrid cloud is a computing environment that combines a public cloud and a private cloud by allowing data and applications to be shared between them.

10. Tradewind Traders are in the process of migrating their resources to Azure cloud services. Currently, they have several VMs deployed to their Azure subscription. Management has asked you to research how their on-premises users will be able to securely access the resources that have been migrated to Azure. Based on that research, which of the following will you need to create to implement this solution?

`A Gateway Subnet`:The virtual network gateway needs to be located in a dedicated subnet in the Azure virtual network. This dedicated subnet is known as a gateway subnet. Try going back and reviewing Microsoft Azure Database, Analytics, and Compute Services.

`A Virtual Network Gateway`: To implement a solution that enables the client computers on your on-premises network to communicate to the Azure virtual machines, you need to configure a VPN (Virtual Private Network) to connect the on-premises network to the Azure virtual network. The Azure VPN device is known as a Virtual Network Gateway. 

`A Virtual network`: 

11. Tradewind Traders is planning to migrate to Azure cloud services. The company currently operates multiple database solutions on-premises including PostgreSQL databases. Management has asked you to spend some time researching the high availability features and support levels available for Azure Database for PostgreSQL.

Based on your research, what level of SLA is available for single-server deployments of PostgreSQL in Azure?

`99.99%`: Azure Database for PostgreSQL - Single Server deployment option delivers built-in high availability with no additional cost of 99.99% SLA.

12. Tradewind Traders is planning to migrate to Azure cloud services but before they do, management has asked you to spend some time researching the Database solutions available in Azure with specific regard to the use of multiple APIs. Based on your research, which of the following cloud database solutions is most appropriate to provide this feature?

`Azure Cosmos DB`: Cosmos DB level of flexibility means that as you migrate your company's databases to Azure Cosmos DB, your developers can stick with the API where they're most comfortable.


13. Tradewind Traders is planning to migrate some of their data and resources to Azure cloud services, Management has decided to only make use of the Platform as a Service (PaaS) offerings in Azure. You have been asked to design a migration plan. As part of this design, you have included the creation of Azure App Services and Azure Storage accounts.

Does this design meet the requirements of the Organization?

`No`: Azure App Service is a PaaS (Platform as a Service) service. However, Azure Storage accounts are an IaaS (Infrastructure as a Service) service. Therefore, this design does not meet the requirements.

14. Tradewind Traders is planning to migrate some of their data and resources to Azure cloud services, Management has asked you to design a deployment plan that will guarantee services running on virtual machines will continue to operate in the event a single datacenter fails. As part of this design, you will deploy virtual machines to two or more scale sets. 

Does this design meet the requirements of the organization?

`No`: Azure virtual machine scale sets let you create and manage a group of load-balanced VMs. The number of VM instances can automatically increase or decrease in response to demand or a defined schedule. Scale sets provide high availability to your applications and allow you to centrally manage, configure, and update many VMs. However, this question does not specify that the scale set will be configured across multiple datacenters so this solution does not meet the goal.

15. Tradewind Traders is planning to migrate to Azure cloud services however management has asked you to research connectivity features between your on-premises environment and Cloud resources. In your research, you learn that Azure virtual networks enable you to link resources in your on-premises environment with your Azure subscription. In effect, you can create a network that spans both your local and cloud environments. There are three mechanisms for you to achieve this connectivity. 

Which of the following is not a valid mechanism?

``
