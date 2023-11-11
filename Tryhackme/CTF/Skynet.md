# Skynet

Room [Skynet](https://tryhackme.com/room/skynet) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "Skynet".

`mkdir Skynet`

- Change directory into Skynet.

`cd Skynet/`

<p align="center"> <img src="https://i.imgur.com/JkneYK1.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Task 1: Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.120.154]

<h2></h2>

<h3>Room Questions</h3>

Question 1: What is Miles password for his emails?

Question 2: What is the hidden directory?

Question 3: What is the vulnerability called when you can include a remote file for malicious purposes?

Question 4: What is the user flag?

Question 5: What is the root flag?

<h2></h2>

<h3>Reconnaissance</h3>

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.120.154`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.120.154`.

<p align="center"> <img src="https://i.imgur.com/UErEXtv.png" height="90%" width="90%" alt=""/>

We found 6 ports open:

- Port 22/TCP Service: ssh
- Port 80/TCP Service: http
- Port 110/TCP Service: pop3
- Port 139/TCP Service: netibios-ssn Samba smbd
- Port 143/TCP Service: imap
- Port 445/TCP Service: Samba

<h2></h2>

<h3>Exploit the Smb Port</h3>

We can see that the smb (139) port is open, we will exploit it and see what is there.

On Terminal: `smbclient -L //10.10.120.154`

- `smbclient`: This is the command-line tool used to interact with SMB/CIFS (Common Internet File System) servers. It is commonly used for accessing shared files and directories on Windows networks.

- `-L`: This is an option or flag for smbclient. The -L flag is used to list (enumerate) shares on the specified server.

- `//10.10.120.154`: This is the server location specified in the Universal Naming Convention (UNC) format. It indicates that the SMB server is at the IP address 10.10.120.154. The double forward slashes (//) are part of the UNC notation used to specify network paths.

Just press "Enter" for the password.

<p align="center"> <img src="https://i.imgur.com/9DxFqiE.png" height="90%" width="90%" alt=""/>

Since we see there is an "anonymous" under Sharename. We will try to exploit it.

On Terminal: `smbclient //10.10.120.154/anonymous`

Just press "Enter" for the password.

- Successfully got in smb with anonymous.

<p align="center"> <img src="https://i.imgur.com/DV1i8Gv.png" height="90%" width="90%" alt=""/>

We will use the `ls` command to see if there any interesting contents.

On Terminal: `ls`

- We can see there are "attention.txt" and "logs directory".

<p align="center"> <img src="https://i.imgur.com/iyXT7pG.png" height="90%" width="90%" alt=""/>

We will extract those files by using the `mget` command.

On Terminal: `mget *.*` to get "attention.txt.
On Terminal: `cd logs` `mget *.*` to get all logs files in the logs directory.

<p align="center"> <img src="https://i.imgur.com/o7PlfxA.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Explore the contents</h3>

We will use the `cat` command to see what is inside of each txt file.

On Terminal: `cat attention.txt`

- From this content, we can see that there is a password change and the person who wrote this message is Miles Dyson, which is also a username that we saw when we exploit the smb port.

<p align="center"> <img src="https://i.imgur.com/cbVvBvX.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/cFqcsWq.png" height="90%" width="90%" alt=""/>

We will now look at "log1.txt".

On Terminal: `cat log1.txt`

- log1.txt seems to be a password list.

<p align="center"> <img src="https://i.imgur.com/tks8KGg.png" height="90%" width="90%" alt=""/>

We will now look at "log2.txt" and "log3.txt".

On Terminal: `cat log2.txt` `cat log3.txt`

- Both logs seems to be empty.

<p align="center"> <img src="https://i.imgur.com/cOMlmit.png" height="90%" width="90%" alt=""/>


<h2></h2>

<h3>Using Hydra to Bruteforce with the Username and Passwords</h3>

Since we got the username to be "milesdyson" and a password list. We will try to bruteforce using `hydra`.

On Terminal: `hydra -l milesdyson -P log1.txt 10.10.120.154 http-form-post "/squirrelmail/src/redirect.php:login_username=^USER^&secretkey=^PASS^&js_autodetect_results=1&just_logged_in=1&Login=Login:Unknown user or password incorrect" > miles.txt`

- `hydra`: The command itself, invoking the Hydra tool.

- `-l milesdyson`: Specifies the login username to be "milesdyson."

- `-P log1.txt`: Specifies the path to a file containing a list of passwords (log1.txt in this case).

- `10.10.120.154`: The IP address of the target system.

- `http-form-post`: Indicates the type of attack, in this case, it's an HTTP POST form-based attack.

- "/squirrelmail/src/redirect.php:login_username=^USER^&secretkey=^PASS^&js_autodetect_results=1&just_logged_in=1&Login=Login:Unknown user or password incorrect":

  - Specifies the login form details:
    - `"/squirrelmail/src/redirect.php:`: The URL of the login page.
    - `login_username=^USER^&secretkey=^PASS^&js_autodetect_results=1&just_logged_in=1&Login=Login:`: The form data to be sent, where ^USER^ and ^PASS^ will be replaced by Hydra during the brute-force attack.
    - `Unknown user or password incorrect"`: The failure message indicating an unsuccessful login attempt.
- `> miles.txt`: Redirects the output (results of the brute-force attack) to a file named miles.txt.

We found out that the password to be: `cyborg007haloterminator`

<p align="center"> <img src="https://i.imgur.com/p1MRX7A.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Login the Webpage</h3>

We now have both the username and password, we will login the webpage.

We will click on the email with the subject "Samba Password reset".

<p align="center"> <img src="https://i.imgur.com/rZFlMa3.png" height="90%" width="90%" alt=""/>

We have successfully obtain the smb password: ")s{A&2Z=F^n_E.B`"

<p align="center"> <img src="https://i.imgur.com/wY23XGU.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Exploit into Miles's Folder</h3>

Since we got the smb password for Miles, we will use it to exploit into his folder.

On Terminal: `smbclient //10.10.120.154/milesdyson -U milesdyson`

- `smbclient`: This is the command-line tool used to interact with SMB (Server Message Block) shares on a network.
- `//10.10.120.154/milesdyson`: This is the UNC (Universal Naming Convention) path specifying the location of the SMB share. It includes:
  - `//`: The standard prefix for SMB paths.
  - `10.10.120.154`: The IP address of the server hosting the SMB share.
  - `/milesdyson`: The specific share or directory on the server.
- `-U milesdyson`: This option specifies the username to be used when connecting to the SMB share. In this case, the username is "milesdyson."

Enter in )s{A&2Z=F^n_E.B` as password.


