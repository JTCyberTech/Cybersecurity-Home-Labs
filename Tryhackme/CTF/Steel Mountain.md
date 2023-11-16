# Steel Moutain.md

Room [Steel Moutain](https://tryhackme.com/room/steelmountain) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "SteelMountain".

`mkdir SteelMountain`

- Change directory into SteelMountain.

`cd SteelMountain/`

<p align="center"> <img src="https://i.imgur.com/lV4jHcT.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.27.109]

Introduction: In this room you will enumerate a Windows machine, gain initial access with Metasploit, use Powershell to further enumerate the machine and escalate your privileges to Administrator.

Question: Who is the employee of the month?

`Bill Harper`

Navigate to the Temporary IP [10.10.27.109].

<p align="center"> <img src="https://i.imgur.com/9e0crsp.png" height="90%" width="90%" alt=""/>

Reverse image the picture with Google.

Right click the image > Select "Search image with Google".

<p align="center"> <img src="https://i.imgur.com/ChtOCix.png" height="90%" width="90%" alt=""/>

Found the name of the person in the photo.

<p align="center"> <img src="https://i.imgur.com/I0ZlrUc.png" height="90%" width="90%" alt=""/>

#

# Initial Access: Questions

Question 1: Scan the machine with nmap. What is the other port running a web server on?

Question 2: Take a look at the other web server. What file server is running?

Question 3: What is the CVE number to exploit this file server?

Quesion 4: Use Metasploit to get an initial shell. What is the user flag?

#

<h2>Question 1</h2>

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -p- -oN nmap_initial.txt 10.10.27.109`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-p-`: This flag specifies scanning all ports. The hyphen after -p indicates that Nmap should scan all 65535 ports. This can be time-consuming but thorough.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.27.109`.

<p align="center"> <img src="https://i.imgur.com/npFTfrB.png" height="90%" width="90%" alt=""/>

Question 1: Scan the machine with nmap. What is the other port running a web server on?

`8080`

#

# Question 2

Navigate to `10.10.27.109:8080` > Click on `HttpFileServer 2.3`.

<p align="center"> <img src="https://i.imgur.com/hFeQIln.png" height="90%" width="90%" alt=""/>

From the URL, we know that the server is "Rejetto". So it's "Rejetto HTTP File Server".

<p align="center"> <img src="https://i.imgur.com/8bO2Ojw.png" height="90%" width="90%" alt=""/>

Question 2: Take a look at the other web server. What file server is running?

`Rejetto HTTP File Server`

# 

# Question 3

Google: Rejetto Http File Server 2.3 exploit.



