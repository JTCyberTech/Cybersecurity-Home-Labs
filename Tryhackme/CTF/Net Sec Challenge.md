# Net Sec Challenge

Room [Net Sec Challenge](https://tryhackme.com/room/netsecchallenge) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "NetSecChallenge".

`mkdir NetSecChallenge`

- Change directory into NetSecChallenge.

`cd NetSecChallenge/`

<p align="center"> <img src="https://i.imgur.com/aIx6qL5.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Task 1: Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.225.162]

Introduction: Use this challenge to test your mastery of the skills you have acquired in the Network Security module. All the questions in this challenge can be solved using only `nmap`, `telnet`, and `hydra`.

<h2></h2>

<h3>Taske 2: Challenge Questions</h3>

Question 1: What is the highest port number being open less than 10,000?

Question 2: There is an open port outside the common 1000 ports; it is above 10,000. What is it?

Question 3: How many TCP ports are open?

Question 4: What is the flag hidden in the HTTP server header?

Question 5: What is the flag hidden in the SSH server header?

Question 6: We have an FTP server listening on a nonstandard port. What is the version of the FTP server?

Question 7: We learned two usernames using social engineering: eddie and quinn. What is the flag hidden in one of these two account files and accessible via FTP?

Question 8: Browsing to http://MACHINE_IP:8080 displays a small challenge that will give you a flag once you solve it. What is the flag?

<h2></h2>

<h3>Reconnaissance</h3>

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -p- -oN nmap_initial.txt 10.10.225.162`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-p-`: This flag specifies scanning all ports. The hyphen after -p indicates that Nmap should scan all 65535 ports. This can be time-consuming but thorough.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.225.162`.

<p align="center"> <img src="https://i.imgur.com/tPSfkQx.png" height="90%" width="90%" alt=""/>

From the nmap scan, we can answer a lot of the challenge questions: 

Question 1: What is the highest port number being open less than 10,000?

Answer: `8080`

<p align="center"> <img src="https://i.imgur.com/RYy9kWw.png" height="90%" width="90%" alt=""/>

Question 2: There is an open port outside the common 1000 ports; it is above 10,000. What is it?

Answer: `10021`

<p align="center"> <img src="https://i.imgur.com/TRasCDE.png" height="90%" width="90%" alt=""/>

Question 3: How many TCP ports are open?

Answer: `6`

<p align="center"> <img src="https://i.imgur.com/KbswdSA.png" height="90%" width="90%" alt=""/>

Question 4: What is the flag hidden in the HTTP server header?

Answer: `THM{web_server_25352}`

<p align="center"> <img src="https://i.imgur.com/0FQ6G63.png" height="90%" width="90%" alt=""/>

Question 5: What is the flag hidden in the SSH server header?

Answer: `THM{946219583339}`

<p align="center"> <img src="https://i.imgur.com/O3i733g.png" height="90%" width="90%" alt=""/>

Question 6: We have an FTP server listening on a nonstandard port. What is the version of the FTP server?

Answer: `vsftpd 3.0.3`

<p align="center"> <img src="https://i.imgur.com/SstFjer.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Bruteforce with Hydra</h3>

We are going to use the `hydra` command to bruteforce the password for both "eddie" and "quinn" via FTP.

On Terminal: `hydra -l eddie -P ../../wordlists/rockyou.txt ftp://10.10.225.162:10021 > eddie.txt`

- `hydra`: The command-line tool for performing brute-force attacks.
- `-l eddie`: The -l flag specifies the login username, and in this case, it's set to "eddie."
- `-P ../../wordlists/rockyou.txt`: The -P flag specifies the path to the password list (wordlist) file. In this case, the wordlist file is "rockyou.txt," and it is located in the specified path.
- `ftp://10.10.225.162:10021`: Specifies the protocol, IP address, and port of the target FTP service. In this case, the FTP service is running on IP address 10.10.225.162 and port 10021.
- `> eddie.txt`: The > symbol is used for output redirection. It redirects the output of the Hydra command to a file named "eddie.txt." This file will contain the results of the brute-force attack.

Found out that eddie's password is `jordan`.

<p align="center"> <img src="https://i.imgur.com/boXkSsF.png" height="90%" width="90%" alt=""/>

Repeat for "quinn"

On Terminal: `hydra -l quinn -P ../../wordlists/rockyou.txt ftp://10.10.225.162:10021 > quinn.txt`

Found out that quinn's password is `andrea`.

<p align="center"> <img src="https://i.imgur.com/T8NhVWH.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Login the FTP using Eddie and Quinn's password</h3>

We will use the `ftp` commnad to login for eddie first.

On Terminal: `ftp 10.10.225.162 10021` > eddie > jordan

- `ftp`: This is the command-line FTP (File Transfer Protocol) client.
- `10.10.225.162`: This is the IP address of the FTP server that you want to connect to.
- `10021`: This is the port number. In this case, the FTP server is configured to listen on port 10021. The default FTP port is 21, but using a different port might be a security measure or a specific configuration.

Successfully log into Eddie's account.

<p align="center"> <img src="https://i.imgur.com/SR0Yx02.png" height="90%" width="90%" alt=""/>

We will explore if eddie have any contents that we can use by using the `ls` command to list all the file.

There is nothing in eddie's account.

<p align="center"> <img src="https://i.imgur.com/tuspz5h.png" height="90%" width="90%" alt=""/>

We will repeat the same thing for quinn's account.

On terminal: `ftp 10.10.225.162 10021` > quinn > andrea

Successfully log into Quinn's account. 

<p align="center"> <img src="https://i.imgur.com/54NubpR.png" height="90%" width="90%" alt=""/>

We will explore if eddie have any contents that we can use by using the `ls` command to list all the file.

There is a "ftp_flag.txt".

<p align="center"> <img src="https://i.imgur.com/02hkJOo.png" height="90%" width="90%" alt=""/>

We will extract it with the `mget` command.

On terminal: `mget *.*`

- `mget`: This is an FTP command that stands for "multiple get." It is used to retrieve multiple files from the remote FTP server.

- `*.*`: This is a wildcard expression specifying the files to be retrieved. The asterisk (*) is a wildcard character that matches any sequence of characters, and the period (.) is a literal character. So, *.* is a wildcard pattern that matches any file with any name and any extension.

Successfully extracted the "ftp_flag.txt" into our own machine.

<p align="center"> <img src="https://i.imgur.com/pVlBHbe.png" height="90%" width="90%" alt=""/>

Use the `cat` command to look at the "ftp_flag.txt" contents.

On Terminal: `cat ftp_flag.txt`

Successfully capture the flag.

<p align="center"> <img src="https://i.imgur.com/qdK0RaM.png" height="90%" width="90%" alt=""/>

Question 7: We learned two usernames using social engineering: eddie and quinn. What is the flag hidden in one of these two account files and accessible via FTP?

Answer: `THM{321452667098}`

<h2></h2>

<h3>Last Question's Small Challenge</h3>

Navigate to the webpage the question asked: `http://10.10.225.162:8080`

The small task: Your mission is to use Nmap to scan 10.10.225.162 (this machine)
as covertly as possible and avoid being detected by the IDS.

We will use: `sudo nmap -sN 10.10.225.162`

- `sudo`: This is a command that allows a permitted user to execute a command as the superuser or another user, as specified by the security policy.
- `nmap`: This is the name of the command-line tool for network exploration and security auditing.
- `-sN`: This is an option or flag for Nmap. The -sN flag specifies the TCP Null scan technique. In a Null scan, the scanner sends TCP packets with no flags set (Null), expecting a certain response from open, closed, or filtered ports. It is a stealthy scanning technique.
- `10.10.225.162`: This is the target IP address. Nmap will perform the specified scan on the device with this IP address.

Successfully capture the flag for the last question.

<p align="center"> <img src="https://i.imgur.com/vk5LuK8.png" height="90%" width="90%" alt=""/>

Question 8: Browsing to http://10.10.225.162:8080 displays a small challenge that will give you a flag once you solve it. What is the flag?

Answer: `THM{f7443f99}`
