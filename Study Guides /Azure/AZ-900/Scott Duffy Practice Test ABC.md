1. In the context of Azure's high availability solutions, what is the primary purpose of Azure Availability Zones?

- They allow manual selection of data centers for virtual machine placement to achieve superior availability compared to other options.

The correct answer is: "They allow manual selection of data centers for virtual machine placement to achieve superior availability compared to other options."

Azure Availability Zones are a high availability offering that protects applications and data from datacenter failures. Each Azure region is composed of multiple datacenters, and each datacenter is essentially an Availability Zone. They are unique physical locations within a region, equipped with their own independent power, cooling, and networking.

By placing your resources across different Availability Zones within a region, you can protect your apps and data from the failure of a single datacenter. If one datacenter goes down, the resources in the other datacenters (Availability Zones) can continue to operate, providing redundancy and increasing the overall availability of your applications.

It's important to note that these zones are not the same as Azure regions (which are geographical areas containing one or more datacenters), nor are they equivalent to resource groups (which are logical containers for resources deployed on Azure). They are also not isolated to specific racks within a datacenter, but rather spread across different datacenters in a region, offering a broader scope of protection.

2. Which of the following scenarios would Azure Policy be a recommended method for enforcement?

- Prevent certain Azure Virtual Machine instance types from beingused in a resource group

Azure Policy can add restrictions on storage account SKUs, virtual machine instance types, and rules relating to tagging of resources and groups. It cannot prompt a user to ask them if they are sure.

3. What is the maximum amount of Azure Storage space a single subscription can store?

- Virtually unlimited

A single Azure subscription can have up to 250 storage accounts per region, and each storage account can store up to 5 Petabytes. That is 31 million Terabytes. This is probably 15-20 times what Google, Amazon, Microsoft and Facebook use combined. That's a lot.

4. TRUE OR FALSE: Through Azure Active Directory one can control access to an application but not the resources of the application.

- False

Azure AD can control the access of both the apps and the app resources.

