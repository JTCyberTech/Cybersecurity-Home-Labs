# Daily Bugle

Room [Daily Bugle](https://tryhackme.com/room/dailybugle) on TryHackMe

#

Make a directory with the room name in the Tryhackme Folder.

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "DailyBugle".

`mkdir DailyBugle`

- Change directory into DailyBugle.

`cd DailyBugle/`

<p align="center"> <img src="https://i.imgur.com/ILt4Ag8.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.62.253]

Question: Access the web server, who robbed the bank?

`Spiderman`

<p align="center"> <img src="https://i.imgur.com/3UV4yfY.png" height="90%" width="90%" alt=""/>

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

#

# Obtain user and root

The webpage's [10.10.62.253] CMS is Joomla. In order to find the version of Joomla, we will use the command: `joomscan`. Can be downloaded on linux terminal.

<p align="center"> <img src="https://i.imgur.com/V7shmVf.png" height="90%" width="90%" alt=""/>

We will find out the version of Joomla with this command:

`joomscan -u 10.10.62.253`

<p align="center"> <img src="https://i.imgur.com/HkdWHXc.png" height="90%" width="90%" alt=""/>

Question: What is the Joomla version?

`3.7.0`

#

Now we will use python script to crack Jonah's password.

First we need to find out the vulnerability of Joomla 3.7.0 by Googling.


On the hint, it says: "SQLi and JohnTheRipper", we will google: "Joomla 3.7.0 exploit db SQLi".

<p align="center"> <img src="https://i.imgur.com/p9OClHE.png" height="90%" width="90%" alt=""/>

We found the CVE to be CVE-2017-8917. 

<p align="center"> <img src="https://i.imgur.com/kkoOwwT.png" height="90%" width="90%" alt=""/>

We will now search on google: "CVE-2017-8917 python script". You can choose any of them but I chose the second one.

<p align="center"> <img src="https://i.imgur.com/HKwtd4A.png" height="90%" width="90%" alt=""/>

Click on "joomblah.py" > Raw

<p align="center"> <img src="https://i.imgur.com/LhGdjeV.png" height="90%" width="90%" alt=""/>

To grab the script into our machine, we copy the URL of the [Raw] and use this command on the terminal:

`wget https://raw.githubusercontent.com/stefanlucas/Exploit-Joomla/master/joomblah.py`

<p align="center"> <img src="https://i.imgur.com/j7ItSNH.png" height="90%" width="90%" alt=""/>

Now we have the script in our project folder.

<p align="center"> <img src="https://i.imgur.com/oMVGc4s.png" height="90%" width="90%" alt=""/>

We will now run the new script with the webpage IP Address.

`python3 joomblah.py http://10.10.62.253/`

- We found the username: "jonah", email: "jonah@tryhackme.com", password in hash: `$2y$10$0veO/JSFh4389Lluc4Xya.dfy2MF.bZhz0jVMw.V.d3p12kBtZutm`

<p align="center"> <img src="https://i.imgur.com/TSE87E8.png" height="90%" width="90%" alt=""/>

We will look into the hash and find out what type of hash it is by using hashcat example(https://hashcat.net/wiki/doku.php?id=example_hashes).

Press "Ctrl + F" and enter "$2" to find what type of hash is the password.

- Found the hash to be "bcrypt" Hash mode: 3200

<p align="center"> <img src="https://i.imgur.com/lwCwVLj.png" height="90%" width="90%" alt=""/>

We will now use Johntheripper to crack the password but first we will need to put the hash value into a txt file.

<p align="center"> <img src="https://i.imgur.com/tGN1F9v.png" height="90%" width="90%" alt=""/>

Then we will use `john` command to crack the hash.

`john --format=bcrypt --wordlist=../../wordlists/rockyou.txt hash.txt`

- We got the password to be "spiderman123"

<p align="center"> <img src="https://i.imgur.com/SHFxTkT.png" height="90%" width="90%" alt=""/>

Question 2: What is Jonah's cracked password?

`spiderman123`

#

Now we are going to login to the webpage with this password.

Logging into the default page didn't see anything special. 

<p align="center"> <img src="https://i.imgur.com/SHFxTkT.png" height="90%" width="90%" alt=""/>

So I look into my gobuster.txt and found the directory: /administrator

<p align="center"> <img src="https://i.imgur.com/5866KJU.png" height="90%" width="90%" alt=""/>

Login with the same user:password jonah:spiderman123.

<p align="center"> <img src="https://i.imgur.com/FdZS63y.png" height="90%" width="90%" alt=""/>

We will need to upload a reverse shell on the webpage and exploit it.

To do this, we will need to click on "Extensions" > "Templates" > "Templates".

<p align="center"> <img src="https://i.imgur.com/1zAxQIl.png" height="90%" width="90%" alt=""/>

Click on "Protostar".

<p align="center"> <img src="https://i.imgur.com/WwEqDAH.png" height="90%" width="90%" alt=""/>

Click on "New File".

<p align="center"> <img src="https://i.imgur.com/dNm47PB.png" height="90%" width="90%" alt=""/>

Call the new file "Shell" and file type ".php" > Create.

<p align="center"> <img src="https://i.imgur.com/SmXfbE3.png" height="90%" width="90%" alt=""/>

Now find a reverse php shell on google and paste it into the file.

<p align="center"> <img src="https://i.imgur.com/jj6nozp.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/FyKWIxw.png" height="90%" width="90%" alt=""/>

After pasting the shell into the file, we need to change the IP into **our** own IP address.
- In my case: "10.6.106.187"

Change the port into anything that you want.
- In my case: "1202"

<p align="center"> <img src="https://i.imgur.com/P3eQlqS.png" height="90%" width="90%" alt=""/>

Save the file.

<p align="center"> <img src="https://i.imgur.com/w8PI3XM.png" height="90%" width="90%" alt=""/>

Now we will go to the terminal and use `ncat` to listen.

`ncat -nlvp 1202`

<p align="center"> <img src="https://i.imgur.com/2TszRtr.png" height="90%" width="90%" alt=""/>

Since the webpage said the file is in /template, we will navigate to /templates to open "shell.php".

- `http://10.10.62.253/templates/protostar/shell.php`

<p align="center"> <img src="https://i.imgur.com/NXwxkQA.png" height="90%" width="90%" alt=""/>

We have successfully got in using ncat.

<p align="center"> <img src="https://i.imgur.com/F6Inlyp.png" height="90%" width="90%" alt=""/>

#

We will try to get some information with the "configuration.php" file in `/var/www/html` to see if there something interesting.

- See there is some sort of a $password = `nv5uz9r3ZEDzVjNu`

<p align="center"> <img src="https://i.imgur.com/nRvJEop.png" height="90%" width="90%" alt=""/>

We will change the directory to `/home` to see the users in the system

- Found user: "jjameson`.

<p align="center"> <img src="https://i.imgur.com/qPA6Gs2.png" height="90%" width="90%" alt=""/>

Now we will try to use ssh to login with jjameson:nv5uz9r3ZEDzVjNu.

On new Terminal: `ssh jjameson@10.10.62.253`

- Successfully login to jjameson's ssh.

<p align="center"> <img src="https://i.imgur.com/XAZj1Wt.png" height="90%" width="90%" alt=""/>

Successsully capture the user flag.

<p align="center"> <img src="https://i.imgur.com/x8zOimm.png" height="90%" width="90%" alt=""/>

Question 3: What is the user flag?

`27a260fe3cba712cfdedb1c86d80442e`

#

We will now try to gain root access.

First we will run: `sudo -l` to see if we can exploit anything.

- It said we can exploit with `yum`.

<p align="center"> <img src="https://i.imgur.com/FBhW6Xp.png" height="90%" width="90%" alt=""/>

Go to Gtfobins(https://gtfobins.github.io/gtfobins/yum/#sudo) and search for yum, sudo.

<p align="center"> <img src="https://i.imgur.com/78CjuZ5.png" height="90%" width="90%" alt=""/>

We will copy and paste part B into the ssh.

<p align="center"> <img src="https://i.imgur.com/IYxA3Xa.png" height="90%" width="90%" alt=""/>

Successfully gain root privilege.

<p align="center"> <img src="https://i.imgur.com/9P9Ys9w.png" height="90%" width="90%" alt=""/>

Successfully captured the root flag.

<p align="center"> <img src="https://i.imgur.com/ylSCwuC.png" height="90%" width="90%" alt=""/>

Question 4: What is the root flag?

`eec3d53292b1821868266858d7fa6f79`
