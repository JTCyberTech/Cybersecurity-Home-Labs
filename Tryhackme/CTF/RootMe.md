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
<img src="https://i.imgur.com/r0pkikC.png" height="90%" width="90%" alt=""/>
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

<h2>

In order to download a reverse shell payload, we will google "reverse shell upload file github".

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

<h2></h2>

We will now move the zip folder into the RootMe directory tohave better accessiblity.

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

<h2></h2>

We will now edit the payload to change it into our IP Address so it will work for us.

- Click inside the Unzipped folder. Then open up the php file to edit.
  - You can use any editing tools but I will be using "Visual Studio Code".

<p align="center">
<br/>
<img src="https://i.imgur.com/m4svard.png" height="90%" width="90%" alt=""/>
<br />
 
- Scroll down to line 49 and 50. Then, change the IP and Port number for the payload.
  - IP = the IP Address of **your own** machine. (Mine is: `10.6.106.187`)
  - Port = anything that you want. (I will be choosing: `1337`)

<p align="center">
<br/>
<img src="https://i.imgur.com/XuOaosn.png" height="90%" width="90%" alt=""/>
<br />

- Save it.

<p align="center">
<br/>
<img src="https://i.imgur.com/zGQJuMJ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

We will now try to upload the payload into the target machine.

- Navigate to `http://10.10.233.63/panel/`. Try to upload the reverse shell payload.
  - Click on "Browse". Find the `php-reverse-shell.php` payload that you just edited.
  - Click on "Upload".

<p align="center">
<br/>
<img src="https://i.imgur.com/NxLJs7a.png" height="90%" width="90%" alt=""/>
<br />

- After trying to upload the php file, it said error with "PHP não é permitido!"
  - "PHP não é permitido!" means "PHP is not allowed!" in Portuguese.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/QFbwvgZ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

We will now try to bypass the php restriction.
 
- In order to bypass this rule. We will search "how to bypass php file upload" on Google.
  - Click on the first site "GitBook".
 
<p align="center">
<br/>
<img src="https://i.imgur.com/Q5xKU3h.png" height="90%" width="90%" alt=""/>
<br />

- We will try and change our `.php` into `.phtml` like the site said.

<p align="center">
<br/>
<img src="https://i.imgur.com/bNDZLmy.png" height="90%" width="90%" alt=""/>
<br />

- Using `mv` to use the `.php` file into `.phmtl`.

<p align="center">
<br/>
<img src="https://i.imgur.com/yl2r0Gw.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Now we will try to upload the new phtml file into `http://10.10.233.63/panel/`.

- Navigate back to `http://10.10.233.63/panel/`.
  - Browse and upload the `php-reverse-shell-master.phtml`.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/jA4TJ7z.png" height="90%" width="90%" alt=""/>
<br />

Success!

<h2></h2>

Now we will go to the index of uploads to check if the phtml file is really there.

- Navigate to `http://10.10.233.63/uploads/`

<p align="center">
<br/>
<img src="https://i.imgur.com/xLFNgFI.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Since the payload is uploaded successfully, if we click on it we will need `netcat` to recieve the connect. So we will start a netcat command to listen to the connect.

- On terminal: `ncat -nlvp 1337`

  - `ncat`: This is the command itself, which is used to invoke the ncat utility.

  - `-n`: This option tells ncat not to perform DNS resolution. It means that IP addresses should be used directly without attempting to resolve hostnames.

  - `-l`: This option stands for "listen." It tells ncat to listen for incoming network connections on a specified port.

  - `-v`: This option stands for "verbose." It instructs ncat to run in verbose mode, which provides more detailed output about the connections and data being transferred.

  - `-p 1337`: This option specifies the port number (1337 in this case) on which ncat should listen for incoming connections.

<p align="center">
<br/>
<img src="https://i.imgur.com/YEwKGj7.png" height="90%" width="90%" alt=""/>
<br />

- Click on `php-reverse-shell-phtml` on `http://10.10.233.63/uploads/`.

<p align="center">
<br/>
<img src="https://i.imgur.com/EfVBqbw.png" height="90%" width="90%" alt=""/>
<br />

- Successfully connected to the target machine.

<p align="center">
<br/>
<img src="https://i.imgur.com/igZBOgh.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

We will now look for the "user.txt" by using the find command.

- On terminal: `find / -name user.txt 2>/dev/null`

  - `find`: This is the command used for searching files and directories in the filesystem.

  - `/`: This is the starting directory or path where the search begins. In this case, it's the root directory, which means the search will start from the root of the filesystem and traverse through all directories.

  - `-name user.txt`: This is a search condition. It specifies that you are looking for files with the name "user.txt." The -name option is used to specify the name of the file you want to find.
 
  - `2>/dev/null`: This part of the command redirects standard error (file descriptor 2) to /dev/null, effectively discarding any error messages. This is useful to suppress permission denied or other error messages that might occur during the search.

<p align="center">
<br/>
<img src="https://i.imgur.com/S2BVqAG.png" height="90%" width="90%" alt=""/>
<br />

Found the directory to be `/var/www/user.txt`.

- Read the .txt file by using `cat` command.
- Found the flag.

Answer: `THM{y0u_g0t_a_sh3ll}`

<p align="center">
<br/>
<img src="https://i.imgur.com/Y6frJfQ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Task 4: Privilege escalation </h3>

Now that we have a shell, let's escalate our privileges to root.

First we will search for file with SUID permission that is werid.

- On terminal: `find / -user root -perm /4000 2>/dev/null`

  - `find`: This is the command used for searching files and directories in the filesystem.

  - `/`: This is the starting directory or path where the search begins. In this case, it's the root directory, which means the search will start from the root of the filesystem and traverse through all directories.

  - `-user root`: This is a search condition. It specifies that you are looking for files owned by the user "root." The -user option is used to filter files based on their owner.

  - `-perm /4000`: This is another search condition. It specifies that you are looking for files with specific permissions. The /4000 part of the command indicates that you are looking for files with the setuid (SUID) permission bit set. SUID is a special permission that allows a user to execute a file with the permissions of the file's owner (in this case, "root"). The / indicates that it's a symbolic operation.
 
  - `2>/dev/null`: This part of the command redirects standard error (file descriptor 2) to /dev/null, effectively discarding any error messages. This is useful to suppress permission denied or other error messages that might occur during the search.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/HZS5KT8.png" height="90%" width="90%" alt=""/>
<br />

Question 1: Search for files with SUID permission, which file is weird?

Answer: `/usr/bin/python`. The only file that I see is not suppose to be there is "/usr/bin/python".

<h2></h2>

We will use `Gtfobins` to find a form to escalate our privileges with the `/usr/bin/python` file.

- Search Gtfobins on Google.
  - Click on the first link `GTFOBins.github.io`.
 
<p align="center">
<br/>
<img src="https://i.imgur.com/lklEYKL.png" height="90%" width="90%" alt=""/>
<br />

- Type in "Python" on the search bar. Then, select "SUID".

<p align="center">
<br/>
<img src="https://i.imgur.com/h4gd1Kq.png" height="90%" width="90%" alt=""/>
<br />

- We will skip the first part of the command and copy the second part of the command.

<p align="center">
<br/>
<img src="https://i.imgur.com/FU53ToE.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

Now we will need to navigate into the `/usr/bin` directory and use that command that we got from Gtfobins.

- On terminal: `cd /usr/bin`
  - Paste the command from Gtfobins: `./python -c 'import os; os.execl("/bin/sh", "sh", "-p")'`
 
<p align="center">
<br/>
<img src="https://i.imgur.com/UsmZ7bB.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

We gain root access.

<p align="center">
<br/>
<img src="https://i.imgur.com/almmVj3.png" height="90%" width="90%" alt=""/>
<br />

We will need to find `root.txt`.

- On terminal: `find / -name root.txt 2>/dev/null`.
  - Found "root.txt" is in "/root/root.txt

<p align="center">
<br/>
<img src="https://i.imgur.com/uvCuorl.png" height="90%" width="90%" alt=""/>
<br />

- Use `cat` command to read the root.txt to obtain the flag.

Answer: `THM{pr1v1l3g3_3sc4l4t10n}`

<p align="center">
<br/>
<img src="https://i.imgur.com/d3TV1ca.png" height="90%" width="90%" alt=""/>
<br />
