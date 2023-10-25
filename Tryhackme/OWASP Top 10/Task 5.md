#  Task 5 [Severity 1] Command Injection Practical

What strange text file is in the website root directory?

- Command used: `ls`

- Answer: `drpepper.txt`

<p align="center">
<br/>
<img src="https://i.imgur.com/Zfpdfwo.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

How many non-root/non-service/non-daemon users are there?

- Command Used: `cat /etc/passwd`

- Answer: `0`

<p align="center">
<br/>
<img src="https://i.imgur.com/5BBXkxw.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>


What user is this app running as?

- Command Used: `whoami`

- Answer: `www-data`

<p align="center">
<br/>
<img src="https://i.imgur.com/NrH4Kxo.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

What is the user's shell set as?

- Commands Used: `id` > `cat /etc/passwd`
  - `id`: to find the use ID = 33.
  - `cat /etc/passwd`: to print all users information and look for 33.

- Answer: `/usr/sbin/nologin`

<p align="center">
<br/>
<img src="https://i.imgur.com/VnC70nT.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

What version of Ubuntu is running?

- Commands Used: `lsb_release -a`
  - `lsb_release -a`:  a Linux command that is used to display information about the Linux distribution and release on the system.

- Answer: `18.04.4`

<p align="center">
<br/>
<img src="https://i.imgur.com/2uKMOQM.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

Print out the MOTD.  What favorite beverage is shown?

- Commands Used: `ls /etc/*motd*` > `ls /etc/*motd*/00-header` > `cat /etc/update-motd.d/00-header`
  - Used `ls /etc/*motd*` to find out the list of files inside `ls /etc/*motd*`. Found out there is a `00-header` file in it.
  - Used `ls /etc/*motd*/00-header` to find out the full directory to be `/etc/update-motd.d/00-header`.
  - Used `cat /etc/update-motd.d/00-header` to look what is inside of the file. Found out at the end it said "**DR PEPPER** MAKES THE WORLD TASTE BETTER!"
 
- Answer: Dr Pepper

<p align="center">
<br/>
<img src="https://i.imgur.com/Tmqp0iu.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/S0akvzW.png" height="90%" width="90%" alt=""/>
<br />

<p align="center">
<br/>
<img src="https://i.imgur.com/Hn2GPRf.png" height="90%" width="90%" alt=""/>
<br />
