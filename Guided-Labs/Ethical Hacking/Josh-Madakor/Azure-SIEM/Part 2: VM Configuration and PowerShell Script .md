<h2>Description:</h2>

In this project phase, I will illustrate the procedure for accessing the virtual machine and demonstrate how to monitor the Event Viewer within it. Subsequently, as part of a controlled experiment, I will disable the firewall to entice potential attackers to target our virtual machine. Following this, I will acquire an online PowerShell script designed to extract the longitude and latitude of the attackers' location. To execute this script, it will be necessary to establish an account on Geolocation.io in order to obtain the requisite API Key. Lastly, we will execute the script to test if we can obtain precise geolocation data pertaining to the attackers' origin.

- Logging into the VM with Remote Desktop Application
- Observe Event Viewer on VM
- Turn off the firewall in the VM
- Download PowerShell Script
- Get the API Key from Gelocation.io
- Run the Script to get Geolocation Data from Attackers

<h2></h2>

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

<h2></h2>

<h2>Turning off the Firewall in VM</h2>

1. In the Virtual Machine > click start menu > type in wf.msc and open it

<p align="left">
wf.msc <br/>
<img src="https://i.imgur.com/frth2Ph.png" height="35%" width="35%" alt=""/>
<br />

2. Click on Windows Defender Firewall Properties

<p align="left">
Windows Defender Firewall <br/>
<img src="https://i.imgur.com/Kk6ofUe.png" height="35%" width="35%" alt=""/>
<br />

3. Turn the Firewall state: Off, for Domain Profile, Private Profile, and Public Profile > Apply

4. This will allow my Desktop Device to ping the VM which doesn't allow before turning off the firewall.

<p align="left">
Desktop Ping VM <br/>
<img src="https://i.imgur.com/jEho9CL.png" height="35%" width="35%" alt=""/>
<br />

<h2></h2>

<h2>Download PowerShell Script</h2>
