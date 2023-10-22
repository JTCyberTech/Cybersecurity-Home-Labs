# 25 Basic Bash Commands Hands-On Tasks

<h3>Task 1: </h3>

Verify your current working directory.

- Command used: ```pwd```.

- Decription:
  - ```pwd``` will print the current working directory. [Command]

<p align="center">
<br/>
<img src="https://i.imgur.com/YOzyLZc.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 2: </h3>

List "/etc" directory files and directories.

- Command used: ```ls /etc```.

- Description:
  - ```ls```: "list command", will list files and directories under given directory. [Command]
  - ```/etc```: the directory used for the list command. [Directory]
 
<p align="center">
<br/>
<img src="https://i.imgur.com/u4Yftfs.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 3: </h3>

List ".conf" files only under "/etc" directory.

- Command: ```ls -l /etc/*.conf```.

- Description:
  - ```ls```: "list command", will list files and directories under given directory. [Command]
  - ```-l```: provide a "long listing". [Argument for ls]
  - ```/etc```: the directory used for the list command. [Directory]
  - ```/*.conf```: * = wildcard, look for all the files having matching string at the end of every file name. [Directory with wildcard]

<p align="center">
<br/>
<img src="https://i.imgur.com/LOb4niu.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 4: </h3>

Print total number of ".conf" files only under "/etc" directory.
 
- Command: ```ls -l /etc/*.conf | wc -l```.

- Description:
  - ```|```: combining two or more commands and output them as one command. [Pipe]
  - ```wc```: command for "word count". [Command]
  - ```-l```: count lines. [Argument for wc]

<p align="center">
<br/>
<img src="https://i.imgur.com/oiEDRpp.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 5: </h3>

Create an empty directory with name "autopilot" under "/tmp" directory.

- Command: ```mkdir /tmp/autopilot```.

- Description:
  - ```mkdir```: command for make directory, to create new directory only. [Command]
  - ```/tmp```: parent directory where you want to create "autopilot". [Directory]
  - ```/autopilot```: name of the directory you are creating in the "/tmp" directory. [Directory]
 
<p align="center">
<br/>
<img src="https://i.imgur.com/leSWAek.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 6: </h3>

Create an empty file with name "devops.txt" under "/tmp/autopilot/" directory.

- Command: ```touch /tmp/autopilot/devops.txt```.

- Description:
  - ```touch```: command for creating new file. [Command]
  - ```/tmp/autopilot```: parent directory where you want to create "devops.txt". [Directory]
  - ```/devops.txt```: name of the file you are creating in the "/tmp/autopilot" directory. [File]

<p align="center">
<br/>
<img src="https://i.imgur.com/fdoSc1B.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 7: </h3>

Change (Switch) your directory to "/tmp/autopilot/".
 
- Command: ```cd /tmp/autopilot```.

- Description:
  - ```cd```: command for change directory. [Command]
  - ```/tmp/autopilot```: directory that you want to change into. [Directory]
 
<p align="center">
<br/>
<img src="https://i.imgur.com/uX22mFI.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 8: </h3>

Switch your directory to /tmp/autopilot and then print "Hello Devops" into the "devops.txt" file in the "/tmp/autopilot" directory.

- Command: ```cd /tmp/autopilot | echo "Hello Devops" > devops.txt```.

- Description:
  - ```echo```: command for writing something in a text file. [Command]
  - ```"Hello Devops"```: message you want to write to the file. [Text]
  - ```>```: redirection operator, redirect the output to a file. [Redirection Operator]
  - ```devops.txt```: filename that you want to create or overwrite. [File]
 
<p align="center">
<br/>
<img src="https://i.imgur.com/yiKMw6D.png" height="60%" width="60%" alt=""/>
<br />


<h2></h2>

<h3>Task 9: </h3>

Display the content of "/tmp/autopilot/devops.txt" file on screen.

- Command: ```cat devops.txt```.

- Description:
  - ```cat```: concatenate command for displaying content of a file. [Command]
  - ```devops.txt```: file that you want to display the content of. [File]

<p align="center">
<br/>
<img src="https://i.imgur.com/5ZfiuNt.png" height="60%" width="60%" alt=""/>
<br />
 

<h2></h2>

<h3>Task 10: </h3>

Switch your directory to /tmp/autopilot then Create a copy of "devops.txt" file and name the copy as "pilot.txt".
