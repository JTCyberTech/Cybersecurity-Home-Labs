# Introduction-Bash-Shell-Lab

<h2>Objectives Description</h2>

- Efficiently navigate through the file directory structure
- Utilize command line and text editing tools to perform various file operations such as viewing, editing, creating, deleting, and renaming
- Locate relevant information pertaining to files, logs, command history, and file paths
- Customize your environment by editing the user alias file
- Develop a script for backing up your user directory
- Streamline processes by automating a script using a cron job



<h2>Environments Used </h2>

- <b>Ubuntu VM</b>
- <b>Bash Shell Commmand Line</b>

<h2>How to navigate through the file directory using Bash Shell Command Line</h2>

1. Open Terminal on Ubuntu VM
2. In order to confirm what shell is running on Ubuntu. Type on command line: 

        $ echo $SHELL

<p align="left">
Returning the path of the shell <br/>
<img src="https://i.imgur.com/81eTTAS.png" height="70%" width="70%" alt=""/>
<br />
The terminal is running Bash shell.
  
3. In order to see what visible files is available. Type on command line: 
  
       $ ls
  
<p align="left">
Available files: <br/>
<img src="https://i.imgur.com/dgMdNJ4.png" height="70%" width="70%" alt=""/>
<br />
ls stands for list  
  
4. Using option on command to view how that command function. Type on command line:
  
      $ ls -al
  
  
  
<p align="left">
Using Option with command: <br/>
<img src="https://i.imgur.com/LmBJzdi.png" height="70%" width="70%" alt=""/>
<br />
ls = command and -al = the option.
  
- stands for starting an option, a = all, also viewing the hidden files, l = long listing format
  
  
  First column tells the permissions
  
  
  - Starting with a d is a directory
  - Starting with a - is a file
  
  - the next three letters are the user's permissions. r = read, w = write, x = execute
  - the next three letters are the group's permissions.
  - the next three letters are the other's permissions.
  
5. Using Change Directory to navigate thru the directory. Type in Command Line: 
  
      $ cd
  
- we can use cd .. to go up one directory.
- we can use cd ~ to go back to the home directory.
 
<h2> How to utilize command line and text editing tools</h2>
  
<h3>Creating a new file</h3>  

Type on command line: 

        $ touch newBashScript
        
touch command creates a new file
        
<h3>Checking if the new file is created</h3>      

Type on command line: 

        $ ls -l newBashScript
  
       
<h3>To remove a file</h3>

Type on command line: 

        $ rm newBashScript
        
 <h3>To overwrite a file</h3>

Type on command line: 

        $ rm newBashScript       
