# Vulnhub-Jangow

<h2> Website Description</h2>

[JANGOW: 1.0.1](https://www.vulnhub.com/entry/jangow-101,754/)



<h3> <b> Download </b> </h3>

[jangow-01-1.0.1.ova (Size: 828 MB)](https://download.vulnhub.com/jangow/jangow-01-1.0.1.ova)



<h2>Environments Used </h2>

- <b>Format: Virtual Machine (Virtualbox - OVA)</b>
- <b>Operating System: Kali Linux VM</b>

<h2>How to get Access to the machine JANGOW 1.0.1:</h2>

<h3> Jangow machine</h3>

After Downloading and installing Jangow, we can see that there is an IP address 192.168.56.118


<p align="left">
Confirmed target IP address: <br/>
<img src="https://i.imgur.com/kVYff37.png" height="50%" width="50%" alt=""/>
<br />

<h3> Scan IP address of Jangow using Kali-Linux </h3>

1. Go into our Kali Linux machine and go to CLI and type in sudo su to have root access:

  <p align="left">
Kali-VM: <br/>
<img src="https://i.imgur.com/jPdxoLC.png" height="60%" width="60%" alt=""/>
<br />

2. Using nmap to scan the IP address (nmap -sV -p- [IP address])

- Flag (-sV): determines which services are running on the target.
- Flag (-p-): scan ports from 1 - 65535.
  
  <p align="left">
Scanning all ports on Jangow's IP address: <br/>
<img src="https://i.imgur.com/Ff2yTft.png" height="60%" width="60%" alt=""/>
<br />

Showing port 21 and 80 is open

  
<h3>Using the browser to look into the IP address</h3>

1. Open up a browser of your choice and type in Jangow's IP address.

<p align="left">
Jangow's IP address on Browser: <br/>
<img src="https://i.imgur.com/OAtnPPO.png" height="60%" width="60%" alt=""/>
<br />

2. Click on the [site/] button on the website

<p align="left">
Jangow's Browser site: <br/>
<img src="https://i.imgur.com/HDWmbcx.png" height="60%" width="60%" alt=""/>
<br />


3. On the site, when we click on the menu we can see [Buscar], we click Buscar

<p align="left">
Buscar on site: <br/>
<img src="https://i.imgur.com/RVnL8wi.png" height="60%" width="60%" alt=""/>
<br />

After clicking on Buscar we will get [192.168.56.118/site/busque.php?busar=] on the link bar and we can play around with it.


<h3>Playing around with the link</h3>

1. 192.168.56.118/site/busque.php?busar=ls -all

   ls: command to list computer files and directories.

<p align="left">
 <br/>
<img src="https://i.imgur.com/7fuuYU2.png" height="60%" width="60%" alt=""/>
<br />   

2. Right-click to "View Page Source"

<p align="left">
Put in a readable format: <br/>
<img src="https://i.imgur.com/sKaf5RQ.png" height="60%" width="60%" alt=""/>
<br />
  
3. Put in 192.168.56.118/site/busque.php?busar=pwd

  pwd to see the work directory, in order to get the password or any file that have sensitive information.

<p align="left">
Put in a readable format: <br/>
<img src="https://i.imgur.com/J3OIkMY.png" height="60%" width="60%" alt=""/>
<br />

shows /var/www/html/site directory has information

4. Put in 192.168.56.118/site/busque.php?busar=ls -all /var/www/html/ see what is in the directory.

<p align="left">
Look into /var/www/html/ directory: <br/>
<img src="https://i.imgur.com/lvKXMUh.png" height="60%" width="60%" alt=""/>
<br />

5.  Put in 192.168.56.118/site/busque.php?busar=cat /var/www/html/.backup, Using cat command to see what is in the backup file.

<p align="left">
Got the username and password of the server <br/>
<img src="https://i.imgur.com/XomlFxf.png" height="60%" width="60%" alt=""/>
<br />


<h3>Trying to access the link with the username ad password with CLI</h3>

1. On the CLI put in [ftp 192.168.56.118]
 
2. type in the username and password on the site 

<p align="left">
Got the username and password of the server <br/>
<img src="https://i.imgur.com/PERvGqs.png" height="60%" width="60%" alt=""/>
<br />

3. type in ls -all and cd /home and then cd jangow01 to change directory.


<h3>Using Exploits on exploit-db.com</h3>

1. Type in the browser: (exploit-db.com/exploits/45010)[exploit-db.com/exploits/45010]
   
2. Copy the whole exploit and paste it on a mousepad document and save it.

3. type in CLI "put [document name]", I named Dirty1.C
 
<p align="left">
Sccessfully put in the exploit file <br/>
<img src="https://i.imgur.com/9PlSobT.png" height="60%" width="60%" alt=""/>
<br />

<p align="left">
 <br/>
<img src="https://i.imgur.com/YCnUb1T.png" height="60%" width="60%" alt=""/>
<br />

4. Go to Jangow Virtual machine, enter in the username and password

5. Enter in "cd ." and check the directory by entering "ls - all"

<p align="left">
Check if your file is in Jangow virtual machine <br/>
<img src="https://i.imgur.com/LAe6rEO.png" height="60%" width="60%" alt=""/>
<br />

6. Enter in gcc -pthread Dirty.c -o dirty -lcrypt"

<p align="left">
Using the gcc compiler to compile the exploit <br/>
<img src="https://i.imgur.com/Lgqxfaw.png" height="60%" width="60%" alt=""/>
<br />
  
7. Run the bypass file by entering ./bypass
   
<p align="left">
Gain Root privilege <br/>
<img src="https://i.imgur.com/hdAbWXX.png" height="60%" width="60%" alt=""/>
<br />

8. Change directory to root by entering cd /root

<p align="left">
See proof.txt <br/>
<img src="https://i.imgur.com/bqeavfs.png" height="60%" width="60%" alt=""/>
<br />
  
9. Enter in cat proof.txt

<p align="left">
Proof of finishing Project <br/>
<img src="https://i.imgur.com/aKAkNnH.png" height="60%" width="60%" alt=""/>
<br />

    
