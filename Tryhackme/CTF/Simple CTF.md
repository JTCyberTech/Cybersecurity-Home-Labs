# Simple CTF

Make a directory with the room name on the Desktop:

- Change directory to /Desktop.

`cd Desktop/`

- Make a new directory call SimpleCTF.

`mkdir SimpleCTF`

- Change directory into SimpleCTF.

`cd SimpleCTF`

<p align="center">
<br/>
<img src="https://i.imgur.com/mx6J0iw.png" height="90%" width="90%" alt=""/>
<br />

Question 1: How many services are running under port 1000?

In order to find open ports, we will use **nmap**.

- `-p 1-65535` (port range).
- `-sC` (script scan).
- `-sV` (service and version info).
- `-oN` (output normal).
- Use format: `nmap -p 1-1000 -sC -sV -oN nmap_initial.txt IP`.

On Terminal: `nmap -p 1-1000 -sC -sV -oN nmap_initial.txt 10.10.165.66`

<p align="center">
<br/>
<img src="https://i.imgur.com/2WnyxHa.png" height="90%" width="90%" alt=""/>
<br />
  
- Found 2 open ports under port 1000, and made a new txt file named: nmap_initial.

Answer: `2`

<h2></h2>

Question 2: What is running on the higher port?

TCP did not work so, I assume there is another port that is open above port 1000.

On Terminal: `nmap -sC -sV -oN nmap_all.txt 10.10.165.66`

<p align="center">
<br/>
<img src="https://i.imgur.com/lFQnou8.png" height="90%" width="90%" alt=""/>
<br />

- Found the third port, 2222 open SSH.

Answer: `SSH`

<h2></h2>

Question 3: What's the CVE you're using against the application? 

We will use Gobuster Directory Brute Force.

`gobuster dir -u http://10.10.165.66/ -w ../wordlists/dirb/common.txt`
