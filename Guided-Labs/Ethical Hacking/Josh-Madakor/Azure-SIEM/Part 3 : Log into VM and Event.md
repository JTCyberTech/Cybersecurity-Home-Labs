<h2>Description:</h2>

<h2>Logging In the Virtual Machine</h2>

1. In [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Virtual Machine

2. Click on honeypot > copy the Public IP Address

3. Go on our own Desktop > click on start menu > open up Remote Desktop Connection Application

4. Paste the Public IP Address to the Remote Desktop Connection Application and use the account information that you sign up the subscription with

<p align="left">
Remote Desktop Connection<br/>
<img src="https://i.imgur.com/WHRlnQp.png" height="35%" width="35%" alt=""/>
<br />

5. Once finished loading up the VM, apply No to all the setting

<p align="left">
VM Startup Settings<br/>
<img src="https://i.imgur.com/4tnLZkG.png" height="35%" width="35%" alt=""/>
<br />

<h2></h2>


<h2>Obesrve Event Viewer on VM</h2>

1. In the Virtual Machine > click start menu > type in Event Viewer and start it up

2. Inside the Event Viewer > Windows Logs > Security > Audit Failure are the ones that we will be gathering.

<p align="left">
Event Viewer<br/>
<img src="https://i.imgur.com/d5BGoft.png" height="35%" width="35%" alt=""/>
<br />

3. The Audit Failure contains:
  - Account Name, Workstation Name, IP Address

<p align="left">
Audit Failure<br/>
<img src="https://i.imgur.com/j7BZFvg.png" height="35%" width="35%" alt=""/>
<br />

4. 
