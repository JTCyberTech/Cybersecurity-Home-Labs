<h2>Description:</h2>

The project's initial phase entails the establishment of an Azure account, coupled with the activation of a free subscription. Subsequently, we proceed with the configuration of a Virtual Machine to fulfill the project's objectives. Initiate the process by establishing a log analytics workspace with concurrent log-gathering activation. Next, establish connectivity between the log analytic workspace and the virtual machine. To culminate the setup, configure Microsoft Sentinel to visualize the attack data and function as a Security Information and Event Management (SIEM) solution.

- Create an Azure Account with the free trial subscription
- Create a Virtual Machine
- Create a Log Analytics Workspace
- Enable Log Gathering with Microsoft Defender for Cloud
- Connect Log Analytics Workspace to the Virtual Machine
- Setup Microsoft Sentinel


<h2></h2>

<h2>Creating an Azure Account</h2>

1. Sign in or create a new account for [Azure Trial](https://azure.microsoft.com/en-us/free/).
    - You will have to put in your credit card information to get the trial subscription with $200 free credits.


2. After the subscription is created, head to [Azure Portal](https://portal.azure.com) and select the account that has been associated with the trial subscription.

<h2></h2>

<h2>Creating a Virtual Machine</h2>

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

<h2></h2>
    
<h2>Creating a Log Analytics Workspace</h2>

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Log Analytics workspaces and click it > Create 

2. In the Basic tab - Select Resource group and Change instance details:
    - Resource group: Lab-Honeypot
    - Name: law-honeypot
    - Region: West US 2

<p align="left">
Create Log Analytics Workspace <br/>
<img src="https://i.imgur.com/CyZPBvN.png" height="35%" width="35%" alt=""/>
<br />

3. Click Review + create at the bottom left corner > create

4. Successfully created a Log Analytics Workspace

<p align="left">
Successfully created Log Analytics Workspace <br/>
<img src="https://i.imgur.com/W0BBymq.png" height="35%" width="35%" alt=""/>
<br />

<h2></h2>

<h2>Enable Log Gathering with Microsoft Defender for Cloud</h2>

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Microsoft Defender for Cloud

2. On the left side, Click on Environment settings under Management > click on Azure subscription 1 > law-honeypot

<p align="left">
Navigating in Microsoft Defender for Cloud <br/>
<img src="https://i.imgur.com/uih1pdY.png" height="35%" width="35%" alt=""/>
<br />


3. Turn on Servers and leave SQL servers on the machine off > save

<p align="left">
Settings | Defender Plans<br/>
<img src="https://i.imgur.com/ch8Vm9P.png" height="35%" width="35%" alt=""/>
<br />

4. Click on Data Collection on the left > Click on All events> save

<p align="left">
Settings | Defender Collection<br/>
<img src="https://i.imgur.com/WgsozCY.png" height="35%" width="35%" alt=""/>
<br />

<h2></h2>

<h2>Connecting Log Analytics Workspace to the Virtual Machine</h2>

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Log Analytics workspaces

2. Click on law-honeypot > Scroll down on the left bar > click on Virtual machine (deprecated) under Classic

<p align="left">
law-honeypot | Virtual machines (deprecated)<br/>
<img src="https://i.imgur.com/fTv6hBf.png" height="35%" width="35%" alt=""/>
<br />

3. Click on connect

<p align="left">
Successfully Connected our Log Analytics Workspace and VM (deprecated)<br/>
<img src="https://i.imgur.com/Ajz0aju.png" height="35%" width="35%" alt=""/>
<br />


<h2></h2>

<h2>Setup Microsoft Sentinel</h2>

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Microsoft Sentinel > Create

2. Pick law-honeypot to add Microsoft Sentinel to a workspace > add

<p align="left">
Successfully Added Sentinel to our Workspace (deprecated)<br/>
<img src="https://i.imgur.com/nbFrxiQ.png" height="35%" width="35%" alt=""/>
<br />

