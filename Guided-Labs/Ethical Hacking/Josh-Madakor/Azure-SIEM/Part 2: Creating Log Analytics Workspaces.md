<h2>Description:</h2>

Create a log analytics workspace with a log repository in Azure to process and analyze our logs from the virtual machine.

<h2>Creating an Log Analytics Workspace</h2>

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

<h2>Enable Log Gathering on Microsoft Defender for Cloud</h2>

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

3. 
