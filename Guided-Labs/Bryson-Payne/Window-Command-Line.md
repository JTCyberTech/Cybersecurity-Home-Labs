# Window-Command-Line

<h2>Beginner Windows Commands</h2>

- dir [list files in directory]
- cd [chang dir, cd ..]
- ver [OS info]
- doskey /h [also up arrow]
- **NO** sudo [run cmd as administrator]
- mkdir/rmdir [also md/rd]
- copy/move/del [copy files]
- help [help or cmd /?]
- cd [print current dir]
- echo [print to screen, > to file]
- notepad [text editor]
- more [show contents of file]
- **NO** find [no exact equivalent]
- ping [ping an address/host]
- ipconfig [network info]
- set [show all environment vars]

<h2></h2>

<h2>Basic Windows Commands</h2>

- dir = command to list files in the directory
  - similar to the ls -l command on Kali Linux
- dir /w = command to list files in the directory in the default listing of Kali Linux
  - similar to the ls command on Kali Linux
- cd = change directory, same as Kali Linux
  - cd Desktop
- cls = command for clear
  - similar to clear or Ctrl + L on Kali Linux
- cd .. = back up into one layer of the directory
- cd / = takes to the root of the directory
- ver = command to check the version of the Virtual Machine
- hostname = command to check the hostname
- doskey /h = command to show all the history commands since you log in this session
  - similar to the history command in Kali Linux

<h2></h2>

<h2>File Window Commands</h2>

- echo hello > textfile.txt = create a .txt name [textfile] and write "hello" in the .txt
- notepad textfile.txt = text editor for textfile, brings up notepad
- more textfile.txt = show the contents of the [textfile.txt]
- mkdir [name] = create a directory with the [name], basically create a folder
  - can also use md for the command; "mkdir myFiles" or "md myFiles"
- rmdir [name] = remove a directory, basically delete a folder
  - can also use rd for the command; "rmdir myFiles" or "rd myFiles"
- move textfile.txt myFiles/ = move textfile.txt to myFiles directory
  - can use the move command to rename; move textfiles.txt silly.txt = rename textfiles.txt to silly.txt
  - similar to the mv command in Kali Linux
- copy silly.txt mytext.txt = copy silly.txt into another .txt [mytext.txt] and have 2 files with different names
  -  similar to the cp command in Kali Linux
- del silly.txt = delete the silly.txt
  -  similar to the rm command in Kali Linux
 
<h2></h2>

<h2>Helpful Windows Commands + Network Commands</h2>

- help [command] = show the manual of the command; help copy
  - [command] /? = the same; copy /?
- ping [website] = network command, see if you have connectivity to the internet for the website
  - ping www.google.com = check if you can connect to google.com
- ipconfig = interface config
  - similar to the ifconfig command in Kali Linux
- ipconfig /renew = reconnect network adapter
- set = command to list all your environment variables
  - similar to the env command in Kali Linux
  - can use cd [environment variables] to change directory
    - cd %USERPROFILE% = change directory to user
    - echo %USERPROFILE% = return what directory is %USERPROFILE%
