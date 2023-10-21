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
  - ```ls```: list command, will list files and directories under given directory. [Command]
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
  - ```ls```: list command, will list files and directories under given directory. [Command]
  - ```-l```: provide a long listing. [Argument for ls]
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
  - ```wc```: command for word count. [Command]
  - ```-l```: count lines. [Argument for wc]

<p align="center">
<br/>
<img src="https://i.imgur.com/oiEDRpp.png" height="60%" width="60%" alt=""/>
<br />
 
- 
