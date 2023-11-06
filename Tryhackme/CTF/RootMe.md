# RootMe

Room [RootMe](https://tryhackme.com/room/rrootme#) at TryHackMe

<h2></h2>

Make a directory with the room name in the TryHackMe Folder.

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "RootMe".

`mkdir RootMe`

- Change directory into RootMe.

`cd RootMe/`

<p align="center">
<br/>
<img src="https://i.imgur.com/dztLsyd.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Task 1: Deploy the machine</h3>

- Connect to TryHackMe network and deploy the machine.

<h2></h2>

<h3>Task 2: Reconnaissance</h3>

Gathering information from the target machine with Nmap command.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.233.63`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.233.63`.

<p align="center">
<br/>
<img src="https://i.imgur.com/sBJf7V9.png" height="90%" width="90%" alt=""/>
<br />

Question 1: Scan the machine, how many ports are open? 

Answer: `2`. From the nmap scan, we can see that port 22 and 80 is open.

<p align="center">
<br/>
<img src="https://i.imgur.com/AoQ4pYo.png" height="90%" width="90%" alt=""/>
<br />

Question 2: What version of Apache is running?

Answer: `2.4.29`. From the nmap scan, we can see that port 80 is running Apache version "2.4.29".

<p align="center">
<br/>
<img src="https://i.imgur.com/eoDEcYJ.png" height="90%" width="90%" alt=""/>
<br />

Question 3: What service is running on port 22?

Answer: `ssh`. From the nmap scan, we can see that port 22 is running on ssh service.

<p align="center">
<br/>
<img src="https://i.imgur.com/88p3EtJ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Using GoBuster tool to find out hidden directory for the target machine.

On terminal: `gobuster dir -u http://10.10.233.63/ -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt`

- `gobuster`: This is the name of the tool that is being used. Gobuster is a popular tool for directory and file brute-forcing on web servers.

- `dir`: This is the mode or flag that specifies that gobuster should perform directory brute-forcing.

- `-u http://10.10.233.63/`: This flag (-u) is used to specify the target URL that you want to scan. In this case, it's "http://10.10.233.63/", which is the URL of the web server you want to perform directory scanning on.

- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: This flag (-w) is used to specify the wordlist or dictionary file that gobuster should use to guess directory and file names. In this case, the wordlist file is located at a relative path of "../../wordlists/dirbuster/directory-list-2.3-medium.txt." The wordlist contains a list of directory and file names that gobuster will use for its brute-force scanning.

- `-x php,txt`: This flag (-x) is used to specify file extensions that should be included in the scan. In this case, it specifies that gobuster should look for directories and files with the extensions ".php" and ".txt." This is a way to filter the results and focus on specific types of files or directories.

<p align="center">
<br/>
<img src="https://i.imgur.com/CGELHcv.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Question 4: Find directories on the web server using the GoBuster tool. What is the hidden directory?

Answer: `/panel/`. From the GoBuster tool command, we found a few hidden directories. Includes: `/panel`, `/index.php`, `/uploads`, `/css`, `/js`. The question gave us a clue with the format "/*****/", therefore "/panel/" is the answer.

<h2></h2>

Visting the different directory on the target machine.

`http://10.10.233.63/`: Main webpage.

<p align="center">
<br/>
<img src="https://i.imgur.com/wXudqDo.png" height="90%" width="90%" alt=""/>
<br />

`http://10.10.233.63/panel/`: This directory let us upload file.

<p align="center">
<br/>
<img src="https://i.imgur.com/mM8L2Bo.png" height="90%" width="90%" alt=""/>
<br />

`http://10.10.233.63/index.php`: Nothing special, direct back to the main webpage.

<p align="center">
<br/>
<img src="https://i.imgur.com/04TVafg.png" height="90%" width="90%" alt=""/>
<br />

`http://10.10.233.63/uploads/`: This page shows the index of /uploads.

<p align="center">
<br/>
<img src="https://i.imgur.com/ppsMPCg.png" height="90%" width="90%" alt=""/>
<br />

`http://10.10.233.63/css/`: This page shows the index of /css.

<p align="center">
<br/>
<img src="https://i.imgur.com/Q4aqHIJ.png" height="90%" width="90%" alt=""/>
<br />

`http://10.10.233.63/js/`: This page shows the index of /js.

<p align="center">
<br/>
<img src="https://i.imgur.com/yRQNxn5.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Task 3: Getting a shell</h3> 

Find a form to upload and get a reverse shell, and find the flag in user.txt.

In order to get reverse shell payload, we will google "reverse shell upload file github".

- Click on the first link "pentestmonkey/php-reverse-shell".

<p align="center">
<br/>
<img src="https://i.imgur.com/JEDzXs7.png" height="90%" width="90%" alt=""/>
<br />

- Click on the Green button that said `Code`. Then select `Download ZIP`.

<p align="center">
<br/>
<img src="https://i.imgur.com/ofiShff.png" height="90%" width="90%" alt=""/>
<br />

- Move the downloaded ZIP file to the RootMe folder using the `mv` command.
  - `└─$ mv Downloads/php-reverse-shell-master.zip Desktop/Tryhackme/RootMe`

<p align="center">
<br/>
<img src="https://i.imgur.com/kQUXdkY.png" height="90%" width="90%" alt=""/>
<br />

- Unzip the ZIP file with `unzip` command.
  - `└─$ unzip php-reverse-shell-master.zip`

<p align="center">
<br/>
<img src="https://i.imgur.com/eYoHrij.png" height="90%" width="90%" alt=""/>
<br />
