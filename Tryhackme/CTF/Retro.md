# Retro

Room [Retro](https://tryhackme.com/room/retro) on TryHackMe

#

Make a directory with the room name in the Tryhackme Folder.

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "Retro".

`mkdir Retro`

- Change directory into Retro.

`cd Retro/`

<p align="center"> <img src="https://i.imgur.com/ctggqCb.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.39.14]

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.39.14`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.39.14`.

<p align="center"> <img src="https://i.imgur.com/KWkVEz9.png" height="90%" width="90%" alt=""/>

Gather the directories and files of the webpage with `Gobuster` command.

On Terminal: `gobuster dir -u 10.10.39.14 -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt | tee Gobuster.txt`

- `gobuster`: This is the command for Gobuster, a tool used for directory and file brute-forcing in web applications.

- `dir`: Specifies that Gobuster should perform directory brute-forcing.

- `-u 10.10.39.14`: Specifies the target URL. In this case, the IP address is 10.10.39.14.

- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: Specifies the path to the wordlist file (directory-list-2.3-medium.txt) that contains the list of directories to be tested.

- `|`: The pipe operator redirects the output of the gobuster command to the next command.

- `tee Gobuster.txt`: The tee command takes the output from Gobuster and writes it to both the terminal (standard output) and a file named Gobuster.txt.

<p align="center"> <img src="https://i.imgur.com/ta9mvef.png" height="90%" width="90%" alt=""/>

#

Question 1: A web server is running on the target. What is the hidden directory which the website lives on?

From Gobuster, we got the answer:

`/retro`

#

We will navigate to the webpage because port 80 is open.

- There is nothing special.

<p align="center"> <img src="https://i.imgur.com/EyZJbuT.png" height="90%" width="90%" alt=""/>

We will now look at /retro.

<p align="center"> <img src="https://i.imgur.com/kAiLgaF.png" height="90%" width="90%" alt=""/>

As I scroll down and look at each post, I found the post "Ready Player One" to be interesting because he made a note about his name of his acatar.
- Note: `parzival` could be a password.

<p align="center"> <img src="https://i.imgur.com/6lDsnPr.png" height="90%" width="90%" alt=""/>

Now we are going use the command "xfreerdp" to try to get into rdp port 3389 that's open.

- We will use Wade as username and parzival as password.

`xfreerdp /u:Wade /v:10.10.39.14`

- `xfreerdp`: This is the command for FreeRDP, an open-source implementation of the Remote Desktop Protocol (RDP).

- `/u:Wade`: Specifies the username for the RDP connection. In this case, the username is "Wade."

- `/v:10.10.39.14`: Specifies the IP address or hostname of the remote machine to which you want to connect. In this case, the IP address is "10.10.39.14."

So, when you run this command, it initiates an RDP connection to the machine with the IP address 10.10.39.14, using the username "Wade." This is useful for remote desktop access to a Windows machine.

<p align="center"> <img src="https://i.imgur.com/JbruoV8.png" height="90%" width="90%" alt=""/>

Successfully login to RDP with Wade:parzival.

<p align="center"> <img src="https://i.imgur.com/lTh1jSm.png" height="90%" width="90%" alt=""/>

We will open the user.txt file.

<p align="center"> <img src="https://i.imgur.com/lTh1jSm.png" height="90%" width="90%" alt=""/>

Successfully capture the user flag.

<p align="center"> <img src="https://i.imgur.com/lJPQmW6.png" height="90%" width="90%" alt=""/>

#

Question 2: user.txt

`3b99fbdc6d430bfb51c72c651a261927`

#

Inside the Remote Desktop, we can see that there is a program: "hhupd" in the recycle bin.

<p align="center"> <img src="https://i.imgur.com/15wFpSk.png" height="90%" width="90%" alt=""/>

We will drag it out of the recycle bin and put on the desktop.

<p align="center"> <img src="https://i.imgur.com/TfI70nh.pngg" height="90%" width="90%" alt=""/>

Now we will follow this video to exploit: [https://www.youtube.com/watch?v=3BQKpPNlTSo]





