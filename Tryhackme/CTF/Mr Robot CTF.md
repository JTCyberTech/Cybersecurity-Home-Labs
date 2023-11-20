# Mr Robot CTF

Room [Mr Robot CTF](https://tryhackme.com/room/mrrobot) on TryHackMe

#

Make a directory with the room name in the Tryhackme Folder.

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "MrRobotCTF".

`mkdir MrRobotCTF`

- Change directory into MrRobotCTF.

`cd MrRobotCTF/`

<p align="center"> <img src="https://i.imgur.com/ILt4Ag8.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.62.253]

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.62.253`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.62.253`.

<p align="center"> <img src="https://i.imgur.com/gGTVnB7.png" height="90%" width="90%" alt=""/>

Gather the directories and files of the webpage with `Gobuster` command.

On Terminal: `gobuster dir -u 10.10.62.253 -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt | tee Gobuster.txt`

- `gobuster`: This is the command for Gobuster, a tool used for directory and file brute-forcing in web applications.
- `dir`: Specifies that Gobuster should perform directory brute-forcing.
- `-u 10.10.62.253`: Specifies the target URL. In this case, the IP address is 10.10.62.253.
- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: Specifies the path to the wordlist file (directory-list-2.3-medium.txt) that contains the list of directories to be tested.
- `|`: The pipe operator redirects the output of the gobuster command to the next command.
- `tee Gobuster.txt`: The tee command takes the output from Gobuster and writes it to both the terminal (standard output) and a file named Gobuster.txt.

<p align="center"> <img src="https://i.imgur.com/PpuujVu.png" height="90%" width="90%" alt=""/>
