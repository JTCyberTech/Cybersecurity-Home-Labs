# Pickle Rick Easy Way

Make a directory with the room name in the Tryhackme Folder.

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "PickleRick".

`mkdir PickleRick`

- Change directory into PickleRick.

`cd PickleRick/`

<p align="center">
<br/>
<img src="https://i.imgur.com/mRzT3gV.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Find the open ports for the given IP for the room. And save the output into a txt file named, `nmap_initial.txt`.

`nmap -sC -sV -oN nmap_initial.txt 10.10.115.58`

- `nmap`: This is the command to run the Nmap network scanning tool.

- `-sC`: This is the option that enables script scanning. When you use -sC, Nmap will run a set of default scripts against the target host specified.

- `-sV`: This is another option that instructs Nmap to perform service version detection. Nmap will try to determine the version of the services running on the target host.

- `-oN nmap_initial.txt`: This option specifies the output format and filename for the Nmap scan results. In this case, -oN indicates that the output should be in normal format, and the output will be saved to a file named "nmap_initial.txt."

- `10.10.115.58`: This is the target IP address or hostname that you want to scan with Nmap. Nmap will perform the scan on this host.

<p align="center">
<br/>
<img src="https://i.imgur.com/mRzT3gV.png" height="90%" width="90%" alt=""/>
<br />

From the nmap scan, we can see port 22 and port 80 is open.

- Port 80 is open so we can visit the website.
  - Port 80 is on the apache server which uses PHP.
 
- Navigate to the given IP Address for the room. http://10.10.115.58/

- We can Right-click on the webpage and select "View Page Source".

- From the page source, we got the Username: `R1ckRul3s`. But have no idea what to do with it.

<p align="center">
<br/>
<img src="https://i.imgur.com/lNpGhF5.png" height="90%" width="90%" alt=""/>
<br />
  
<h2></h2>

We will begin to use gobuster to see if there is any directory that is interesting.

`gobuster dir -u 10.10.115.58/ -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt`

- `gobuster`: This is the name of the tool that is being used. Gobuster is a popular tool for directory and file brute-forcing on web servers.

- `dir`: This is the mode or flag that specifies that gobuster should perform directory brute-forcing.

- `-u http://10.10.80.212/`: This flag (-u) is used to specify the target URL that you want to scan. In this case, it's "http://10.10.80.212/", which is the URL of the web server you want to perform directory scanning on.

- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: This flag (-w) is used to specify the wordlist or dictionary file that gobuster should use to guess directory and file names. In this case, the wordlist file is located at a relative path of "../../wordlists/dirbuster/directory-list-2.3-medium.txt." The wordlist contains a list of directory and file names that gobuster will use for its brute-force scanning. (My wordlist is in my Desktop)

- `-x php,txt`: This flag (-x) is used to specify file extensions that should be included in the scan. In this case, it specifies that gobuster should look for directories and files with the extensions ".php" and ".txt." This is a way to filter the results and focus on specific types of files or directories.

<p align="center">
<br/>
<img src="https://i.imgur.com/BGXmOdX.png" height="90%" width="90%" alt=""/>
<br />

Found: `/.php`, `/login.php`, `/assets`, `/portal.php`, and `/robots.txt`

<h2></h2>

Investigate each directory by navigating to each of them.

- `/.php` is a Forbidden page, just like gobuster said (status: 403).

<p align="center">
<br/>
<img src="https://i.imgur.com/EMjRrgr.png" height="90%" width="90%" alt=""/>
<br />

- `/login.php` is a login page that needs a username and password.

<p align="center">
<br/>
<img src="https://i.imgur.com/EMjRrgr.png" height="90%" width="90%" alt=""/>
<br />

- `/assets` is the Index of /assets.

<p align="center">
<br/>
<img src="https://i.imgur.com/Sjnki3d.png" height="90%" width="90%" alt=""/>
<br />

- `/portal.php` just redirect to the `/login.php` page.

- `/robots.txt` have a word "Wubbalubbadubdub".

<p align="center">
<br/>
<img src="https://i.imgur.com/YV0dfFr.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Logging into the `/login.php`.

- We have the username of `R1ckRul3s`.
- We will try password of `Wubbalubbadubdub`, that we got from `/robots.txt`.

<p align="center">
<br/>
<img src="https://i.imgur.com/sptfxZY.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Logged into the Portal.

<p align="center">
<br/>
<img src="https://i.imgur.com/xg0tWG2.png" height="90%" width="90%" alt=""/>
<br />

Every tabs besides the `Commands` tab are not accessible.

We will try different commands.

- Commands: `ls`

<p align="center">
<br/>
<img src="https://i.imgur.com/7I2qB53.png" height="90%" width="90%" alt=""/>
<br />

We can see that there are two interesting .txt files, `Sup3rS3cretPickl3Ingred.txt` and `clue.txt`.
- We will try to read it by using commands.

- Commands: `cat Sup3rS3cretPickl3Ingred.txt` Failed.
- Commands: `nano Sup3rS3cretPickl3Ingred.txt` Failed.
- Commands: `vi Sup3rS3cretPickl3Ingred.txt` Failed.
- Commands: `head Sup3rS3cretPickl3Ingred.txt` Failed.

<p align="center">
<br/>
<img src="https://i.imgur.com/D6tp7uz.png" height="90%" width="90%" alt=""/>
<br />

- Commands: `less Sup3rS3cretPickl3Ingred.txt` Success.

<p align="center">
<br/>
<img src="https://i.imgur.com/gEC2yOH.png" height="90%" width="90%" alt=""/>
<br />

Output: `mr. meeseek hair`

<h2></h2>

Look at what clue.txt says.

- Commands: `less clue.txt`

Output: Look around the file system for the other ingredient.

<h2></h2>

In order to look for file system, we will use the `cd` command.

- Commands: `cd /home`, no output.

We can try to link two commands by using `;`.

- Commands: `cd /home; ls`, output: `rick` `ubuntu`.

Interested in the rick directory.

- Commands: `cd /home/rick; ls` output: `second ingredients`

Interested in the second ingredients, will try to use `less` command again.

- Commands: `cd /home/rick; less second ingredients`, no output.

- Commands: `cd /home/rick;  less "second ingredients"`



Output: `1 jerry tear`

<p align="center">
<br/>
<img src="https://i.imgur.com/9TeqNOy.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Let's try to get root privilege. Will run `sudo -l` to see if we need any password to run sudo.

- Command: `sudo -l`

<p align="center">
<br/>
<img src="https://i.imgur.com/oyuiX45.png" height="90%" width="90%" alt=""/>
<br />

- NOPASSWD means the user is not required to enter a password when using sudo to execute commands.

Let's check out the Root directory.

- Commands: `sudo ls /root`, Output: `3rd.txt`.

Exploit and see the .txt file.

- Commands: `sudo less /root/3rd.txt`

<p align="center">
<br/>
<img src="https://i.imgur.com/K7a8ARQ.png" height="90%" width="90%" alt=""/>
<br />

Output: `3rd ingredients: fleeb juice`

<h2></h2>

Question 1: What is the first ingredient that Rick needs?

Answer: `mr. meeseek hair`

Question 2: What is the second ingredient in Rick’s potion?

Answer: `1 jerry tear`

Question 3: What is the last and final ingredient?

Answer: `fleeb juice`

<h2></h2>
