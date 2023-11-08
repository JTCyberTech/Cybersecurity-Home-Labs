# RootMe

Room [Bounty Hunter](https://tryhackme.com/room/cowboyhacker) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "BountyHunter".

`mkdir BountyHunter`

- Change directory into BountyHunter.

`cd BountyHunter/`

<p align="center">
<br/>
<img src="https://i.imgur.com/C9zzmUR.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.221.71]

<h2></h2>

<h3>Reconnaissance:</h3> 
  
Gather the Information from the Target Machine with Nmap Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.221.71`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.221.71`.

<p align="center">
<br/>
<img src="https://i.imgur.com/FjHqFs1.png" height="90%" width="90%" alt=""/>
<br />

Create a new document to write down the open ports:

<p align="center">
<br/>
<img src="https://i.imgur.com/krkrNzO.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Examine the HTTP Port</h3>

Since port 80  HTTP is open, we will examine the HTTP webpage.

On the site, we found text message with a few usernames. We will create a new txt file with those usernames and name it "users.txt" for good practice.

<p align="center">
<br/>
<img src="https://i.imgur.com/EjQlNWl.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Examine the FTP Port</h3>

Since port 21 FTP is open. We can try to login as anonymous.

On Terminal: `ftp anonymous@10.10.221.71`

<p align="center">
<br/>
<img src="https://i.imgur.com/tH7Z4bq.png" height="90%" width="90%" alt=""/>
<br />

We successfully login, now we can get all the files that we can get by using the `mget` command.

On Terminal: `mget *.*`

<p align="center">
<br/>
<img src="https://i.imgur.com/QM0S4FX.png" height="90%" width="90%" alt=""/>
<br />

An error occur. `229 Entering Extended Passive Mode (|||27161|)`. We can fix it by typing in `passive` first before using the `mget` command. We will reconnect to the ftp port.

On Terminal: `passive`
On Terminal: `mget *.*`

<p align="center">
<br/>
<img src="https://i.imgur.com/NobeU01.png" height="90%" width="90%" alt=""/>
<br />

We have successfully exported "locks.txt" and "task.txt". We are finished with the ftp port, we can exit the ftp port by:

On Terminal: `quit`

<p align="center">
<br/>
<img src="https://i.imgur.com/Dl4Zkz9.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h3>Explore the New "locks.txt" File</h3>

We can examine the "lock.txt" file by using the `cat` command.

On Terminal: `cat locks.txt`

<p align="center">
<br/>
<img src="https://i.imgur.com/6JZJvDm.png" height="90%" width="90%" alt=""/>
<br />

The locks.txt seems like a list of passwords.

<h2></h2>

<h3>Explore the New "task.txt" File</h3>

We can examine the "task.txt" file by using the `cat` command.

On Terminal: `cat task.txt`

<p align="center">
<br/>
<img src="https://i.imgur.com/E9oBlvq.png" height="90%" width="90%" alt=""/>
<br />

We found a new user `lin`. Update the users.txt with the new user.

<p align="center">
<br/>
<img src="https://i.imgur.com/daO6XMN.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 1:  Who wrote the task list?  

Answer: `lin`

We know is `lin` because of the "task.txt".

<h2></h2>

<h3>Bruteforce with SSH Port</h3>

Since we know port 22 SSH is open, we can try to exploit it by bruteforce attack using `hydra` command.

On Terminal: `hydra -L users.txt -P locks.txt 10.10.221.71 ssh

- `hydra`: This is the command to run the Hydra tool.

- `-L users.txt`: This option specifies the file "users.txt" as the source of usernames to be tested during the brute-force attack. Each line in the file "users.txt" is considered a potential username.

- `-P locks.txt`: This option specifies the file "locks.txt" as the source of passwords to be tested during the brute-force attack. Each line in the file "locks.txt" is considered a potential password.

- `10.10.221.71`: This is the target IP address or hostname of the SSH server that you want to attack.

- `ssh`: This part of the command specifies the service or protocol for the attack, in this case, SSH. Hydra will attempt to gain access to the SSH server using the provided usernames and passwords.

<p align="center">
<br/>
<img src="https://i.imgur.com/Mw53hjG.png" height="90%" width="90%" alt=""/>
<br />

Successfully found the login and password, `lin:RedDr4gonSynd1cat3`. 

<p align="center">
<br/>
<img src="https://i.imgur.com/WUEB7h4.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 2: What service can you bruteforce with the text file found?

Answer: `lin`

Question 3: What is the users password? 

Answer: `RedDr4gonSynd1cat3`

<h2></h2>

<h3>Login ssh with the Newly Obtained User and Password</h3>

Log into ssh using the `shh` command.

On Terminal: `ssh lin@10.10.221.71`

<p align="center">
<br/>
<img src="https://i.imgur.com/2j1TeeE.png" height="90%" width="90%" alt=""/>
<br />

Successfully login lin's account. And successfully captured the flag for "user.txt".

Answer: `THM{CR1M3_SyNd1C4T3}`

<p align="center">
<br/>
<img src="https://i.imgur.com/TsVgWcR.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Try to Access Root Privilege</h3>

We will use the sudo -l command to list all the sudo privileges that current user can do.

On terminal: `sudo -l`

<p align="center">
<br/>
<img src="https://i.imgur.com/TCyhpUl.png" height="90%" width="90%" alt=""/>
<br />

Found that the user "lin" can run commands in `/bin/tar` to gain root privilege.

<h2></h2>

<h3>Search on Gtfobins for Exploit</h3>

Navigate to Google, search Gtfobins. And click on the first result (gtfobins.github.io)

<p align="center">
<br/>
<img src="https://i.imgur.com/mQ1yrKr.png" height="90%" width="90%" alt=""/>
<br />

On the search bar: `tar`, click on "Sudo" for script that help gainning root privilege.

<p align="center">
<br/>
<img src="https://i.imgur.com/wmuHS7A.png" height="90%" width="90%" alt=""/>
<br />

Copy the script for the exploit.

<p align="center">
<br/>
<img src="https://i.imgur.com/3V3PgMI.png" height="90%" width="90%" alt=""/>
<br />

Paste the script on the terminal:

<p align="center">
<br/>
<img src="https://i.imgur.com/hpd1Ta2.png" height="90%" width="90%" alt=""/>
<br />

Gained root privilege.

<h2></h2>

<h3>Search for the Final Flag</h3>

Change directory to the root directory using the `cd` command.

On Terminal: `cd /root`

List all the file inside the root directory using the `ls` command.

On Terminal: `ls`

Read the "root.txt" file using the `cat` command and successfully capture the final flag.

Answer: `THM{80UN7Y_h4cK3r}`

<p align="center">
<br/>
<img src="https://i.imgur.com/DCz97DI.png" height="90%" width="90%" alt=""/>
<br />
