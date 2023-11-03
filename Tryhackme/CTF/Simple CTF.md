# Simple CTF

Make a directory with the room name in the Desktop:

- Change directory to /Desktop.

`cd Desktop/`

- Make a new directory call SimpleCTF.

`mkdir SimpleCTF`

- Change directory into SimpleCTF.

`cd SimpleCTF/`

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

- `gobuster`: This is the name of the tool that is being used. Gobuster is a popular tool for directory and file brute-forcing on web servers.

- `dir`: This is the mode or flag that specifies that gobuster should perform directory brute-forcing.

- `-u http://10.10.165.66/`: This flag (-u) is used to specify the target URL that you want to scan. In this case, it's "http://10.10.165.66/", which is the URL of the web server you want to perform directory scanning on.

- `-w ../wordlists/dirb/common.txt`: This flag (-w) is used to specify the wordlist or dictionary file that gobuster should use to guess directory and file names. In this case, the wordlist file is "../wordlists/dirb/common.txt," which is located one directory level up from the current working directory. This file contains a list of common directory and file names that gobuster will use for its brute-force scanning.

<p align="center">
<br/>
<img src="https://i.imgur.com/R9Agzsf.png" height="90%" width="90%" alt=""/>
<br />

- Found: /simple to be suspicious.

Navigate to the website directory of /simple.
`http://10.10.165.66/simple/`

- We can scroll down all the way at the bottom and see C`MS Made Simple version 2.2.8`.

<p align="center">
<br/>
<img src="https://i.imgur.com/aGEmjF5.png" height="90%" width="90%" alt=""/>
<br />

- We can use searchploit to find the CVE.
`searchsploit "CMS Made Simple"`

<p align="center">
<br/>
<img src="https://i.imgur.com/7XqvmE2.png" height="90%" width="90%" alt=""/>
<br />

Or we can use a simplier method. Just search for CMS Made simple version 2.2.8 exploit on Google.

- The first link is CVE-2019-9053, and it's a SQLi.

<p align="center">
<br/>
<img src="https://i.imgur.com/bTJ08zg.png" height="90%" width="90%" alt=""/>
<br />

Answer: `CVE-2019-9053`

<h2></h2>

Question 4: To what kind of vulnerability is the application vulnerable?

Answer: `SQLi`

<h2></h2>

Question 5: What's the password?

We will download the exploit and move it to our SimpleCTF directory.

<p align="center">
<br/>
<img src="https://i.imgur.com/16xZoaN.png" height="90%" width="90%" alt=""/>
<br />

- Copy the exploit to the SimpleCTF directory.
  - On Terminal: `cp ~/Downloads/46635.py .`

<p align="center">
<br/>
<img src="https://i.imgur.com/waTBISY.png" height="90%" width="90%" alt=""/>
<br />

- We will use python3 to crack the password.
  - `python3 46635.py -u http://10.10.165.66/simple/ -c -w ../wordlists/dirb/common.txt`
 
<p align="center">
<br/>
<img src="https://i.imgur.com/K9kZHCv.png" height="90%" width="90%" alt=""/>
<br />

- `python3`: This is the command to run a Python 3 script. It invokes the Python interpreter for version 3.x.

- `46635.py`: This is the name of the Python script that you are running. The script is named "46635.py."

- `-u http://10.10.165.66/simple/`: This is a command-line argument. It appears to be specifying a URL using the -u flag. In this case, the URL is "http://10.10.165.66/simple/." The script might use this URL for some specific functionality.

-c: This is another command-line argument, and it doesn't have a value associated with it. It could be a flag that instructs the script to perform a specific action or enable a particular mode.

-w ../wordlists/dirb/common.txt: This is another command-line argument. It appears to specify a wordlist or dictionary file for the script using the -w flag. The wordlist file is located at "../wordlists/dirb/common.txt," which is in a directory one level up from the current working directory. The script may use this wordlist for some kind of scanning or dictionary attack.

Found the username and password.

Answer: `secret`

<h2></h2>

Question 6: Where can you login with the details obtained?

Answer: `SSH`

<h2></h2>

Question 7: What's the user flag?

We will break in the machine with ssh, my IP changed from `10.10.165.66` to `10.10.20.204` because Tryhackme ran out of time and terminated my IP Address.

`ssh mitch@10.10.20.204 -p 2222`  

- `ssh`: This is the SSH client command that you are using to initiate an SSH session.

- `mitch`: This is the username you want to use to log in to the remote server. In this case, you are trying to log in as the user "mitch."

- `@10.10.20.204`: This is the IP address or hostname of the remote server you want to connect to. In this example, the server's IP address is "10.10.20.204."

- `-p 2222`: This is an option that specifies the port number to use for the SSH connection. By default, SSH uses port 22, but in this command, you are explicitly specifying port 2222 for the connection. This is useful when the SSH server on the remote machine is configured to listen on a non-standard port.

<p align="center">
<br/>
<img src="https://i.imgur.com/VAV6CEu.png" height="90%" width="90%" alt=""/>
<br />

Got the user flag.

<p align="center">
<br/>
<img src="https://i.imgur.com/OsQV323.png" height="90%" width="90%" alt=""/>
<br />

Answer: `G00d j0b, keep up!`

<h2></h2>

Question 8: Is there any other user in the home directory? What's its name?

- We used `pwd` to find out that we are at the `/home/mitch` directory.
  - We can use the `cd ..` to change the directory to `/home`.
  - Use `ls` to see what other directory is there.
 
Found another user at the home directory.

<p align="center">
<br/>
<img src="https://i.imgur.com/WL6L1AV.png" height="90%" width="90%" alt=""/>
<br />

Answer: `sunbath`

<h2></h2>

Question 9: What can you leverage to spawn a privileged shell?

We can use `sudo -l` to see what we can do for the next privilege escalation step.

Found the command that we can run without password and root permission.

<p align="center">
<br/>
<img src="https://i.imgur.com/NJnK1DC.png" height="90%" width="90%" alt=""/>
<br />

Answer: `vim`

<h2></h2>

Question 10: What's the root flag?

We can use the information that we got from answer of question 9.

- We can go to [GTFOBins](https://gtfobins.github.io/) website

- Search: `vim` on the site. Then select `sudo`.

<p align="center">
<br/>
<img src="https://i.imgur.com/iC7nISn.png" height="90%" width="90%" alt=""/>
<br />

- We can copy (a) `sudo vim -c ':!/bin/sh'` and paste it on the Terminal.

<p align="center">
<br/>
<img src="https://i.imgur.com/5dWJ6Bb.png" height="90%" width="90%" alt=""/>
<br />

- Got in Root.

- Change the directory to root by `cd /root`.

- `ls` to check if there is anything in the root directory.

- `cat root.txt` to see what is in the root.txt.

- Got the root flag.

<p align="center">
<br/>
<img src="https://i.imgur.com/QcuPGpL.png" height="90%" width="90%" alt=""/>
<br />

Answer: `W3ll d0n3. You made it!`
