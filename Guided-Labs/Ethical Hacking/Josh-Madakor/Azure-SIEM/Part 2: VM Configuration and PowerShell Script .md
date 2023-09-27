<h2>Description:</h2>

In this project phase, I will illustrate the procedure for accessing the virtual machine and demonstrate how to monitor the Event Viewer within it. Subsequently, as part of a controlled experiment, I will disable the firewall to entice potential attackers to target our virtual machine. Following this, I will acquire an online PowerShell script designed to extract the longitude and latitude of the attackers' location. To execute this script, it will be necessary to establish an account on Geolocation.io in order to obtain the requisite API Key. Lastly, we will execute the script to test if we can obtain precise geolocation data pertaining to the attackers' origin.

- Logging into the VM with Remote Desktop Application
- Observe Event Viewer on VM
- Turn off the firewall in the VM
- Get the API Key from Gelocation.io
- Download PowerShell Script
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

<h2>Get API Key from Geolocation.io</h2>

1. Sign up on [Geolocation.io](https://ipgeolocation.io/signup.html)

2. Verify Email and login to get the API Key

<p align="left">
API Key Obtained <br/>
<img src="https://i.imgur.com/kuIVe04.png" height="35%" width="35%" alt=""/>
<br />


<h2></h2>

<h2>Fetching PowerShell Script</h2>

1. [PowerShell Script](https://github.com/joshmadakor1/Sentinel-Lab/blob/main/Custom_Security_Log_Exporter.ps1) by Josh Madakor

2. Copy the whole code on the GitHub website

3. Go back to the VM > Start menu > Search: Windows PowerShell ISE and run it as administrator

4. Windows PowerShell ISE > File > New

5. Paste the whole code into PowerShell ISE

6. Change the API KEY to your own that you got from Geolocation.io

<p align="left">
PowerShell ISE <br/>
<img src="https://i.imgur.com/DMQIBdY.png" height="35%" width="35%" alt=""/>
<br />

7. Save it on Desktop > name: Log_Exporter

<h2></h2>

<h2>Running and TestingPowerShell Script</h2>

1. PwerShell ISE > Click Run

<p align="left">
PowerShell ISE Run Script <br/>
<img src="https://i.imgur.com/jNfut1T.png" height="35%" width="35%" alt=""/>
<br />

2. Check if the log file is created
  - VM start menu > search: run > Run program: C:\ProgramData\

<p align="left">
Navigate to logfile <br/>
<img src="https://i.imgur.com/eCcTv6a.png" height="35%" width="35%" alt=""/>
<br />
  
3. Test if the Log will update
  - Go back to your Desktop > Start menu search: Remote Desktop Connect
  - Attempt to fail to log to the VM with
    - Username: Testing
   
<p align="left">
Log is working<br/>
<img src="https://i.imgur.com/OUHZZUu.png" height="35%" width="35%" alt=""/>
<br />

