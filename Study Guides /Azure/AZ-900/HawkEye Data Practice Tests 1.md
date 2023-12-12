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
