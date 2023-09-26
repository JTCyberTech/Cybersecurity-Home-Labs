<h2>Description:</h2>

The first step of this project is to create a SIEM with Azure and configure a Virtual Machine.

<h2></h2>

<h2>Creating an Azure Account</h2>

1. Sign in or create a new account for [Azure Trial](https://azure.microsoft.com/en-us/free/).
    - You will have to put in your credit card information to get the trial subscription with $200 free credits.


2. After the subscription is created, head to [Azure Portal](https://portal.azure.com) and select the account that has been associated with the trial subscription.

<h2></h2>

<h2>Creating an Virtual Machine</h2>

This is the machine that will be exposed to the attackers. (The Honeypot Machine)

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search virtual machines and click it.

<p align="left">
Search Bar - Virtual Machines <br/>
<img src="https://i.imgur.com/rrADzfv.png" height="35%" width="35%" alt=""/>
<br />


2. Create > Azure virtual machine

<p align="left">
Create a Virtual Machine Page <br/>
<img src="https://i.imgur.com/CYIjFLl.png" height="35%" width="35%" alt=""/>
<br />

3. Create a new resource group and name it: Lab-Honeypot

<p align="left">
Create a new resource group <br/>
<img src="https://i.imgur.com/uWVk9zv.png" height="35%" width="35%" alt=""/>
<br />

4. In the Basic tab - Change instance details:
   - Virtual machine name: honeypot-vm
   - Region: (US) West US 3
   - Availability options: No infrastructure redundancy required
   - Security type: Standard
   - Image: Windows 10 Pro, version 22H2 - x64 Gen2 (free service eligible)
   - Size: Standard_B1s - 1 vcpu, 1 GiB memory ($7.59/month) (free service eligible)
   - Create your own username and password
   
<p align="left">
Instance Details <br/>
<img src="https://i.imgur.com/V8grONm.png" height="35%" width="35%" alt=""/>
<br />   

5. Leave Disks tab as it is > Next Networking

6. In the Networking tab:
    - Change NIC network security group: Advanced
    - Configure network security group: create new
        - Delete the default inbound rule
        - Add an inbound rule:
            - Destination port ranges: * (meaning everything)
            - Priority: 100
            - Name: DANGER

<p align="left">
Create a new inbound rule <br/>
<img src="https://i.imgur.com/8aVsRNB.png" height="35%" width="35%" alt=""/>
<br />


7. Click Review + create at the bottom left corner > create

<p align="left">
Review + create <br/>
<img src="https://i.imgur.com/RHRZIcw.png" height="35%" width="35%" alt=""/>
<br />

8. Successfully deploy a honeypot machine

<p align="left">
Honeypot Machine Created <br/>
<img src="https://i.imgur.com/9wgVAfM.png" height="35%" width="35%" alt=""/>
<br /> 
