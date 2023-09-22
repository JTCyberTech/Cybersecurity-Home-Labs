# Kali Linux Command Line

<h2>Helpful Linux Terminal Commands:</h2>

- ls [list, ls -al ]
- cd [chang dir, cd..]
- uname -a [OS info]
- history [also up arrow]
- sudo [super user do]
- mkdir/rmdir [create dir]
- cp/mv/rm [copy/move/del files]
- man [help or cmd --help]
- pwd [print working dir]
- echo [print to screen, > to file]
- nano [text editor, CTRL-X]
- more [show contents of file]
- find -name [find file by name]
- locate [locate after updatedb]
- ping/ifconfig [network]
- env [show all environment vars]

<h2></h2>

<h2>Basic Linux Commands</h2>

- ls = listing of all files
- ls -a = list all the files including the hidden ones
- ls -l = long listing for all in terms of directory
- ls -la = long listing for all files including hidden ones
- cd [name of the directory] = change directory
- cd .. = return back one directory
- cd = return back to the home directory
- uname -a = return what OS is running
- pwd = present working directory
- history = all command that was run in the history

<h2></h2>

<h2>File Linux Commands</h2>

- mkdir [name] = create a directory with the [name]
- rmdir [name] = remove a directory
- echo hello > file.txt = create a .txt name file and write hello in the .txt
- more file.txt = show the contents of the "file.txt", in this case, will only show "hello"
  - return: hello
- cp file.txt myfile.txt = copy "file.txt" and create another .txt call "myfile". Will have both .txt afterward
- mv myfile.txt textfile.txt = rename "myfile.txt" to "textfile.txt"
- rm file.txt = remove "file.txt"
- nano textfile.txt = open up text editor
  - Ctrl + O to save, ctrl + x to exit

<h2></h2>

<h2>Helpful Commands</h2>

- sudo = super user do command that allows you to do only super can do
  - sudo apt-get install python3 = install python3, only superuser can install
  - sudo service network-manager restart = restart networking services
- cd / = go to root directory
- find -name [name] = find command, find all folders containing [name] in the current directory
  - find -name Desktop = find all the user's [Desktop] folders in your current directory
- locate [name] = locate command, locate all folders containing [name] in your computer
  - locate command is an index search for files in the database. 
  - locate Desktop = locate all folders that contain [Desktop]
    - If you create a new file, you have to use **"updatedb"** command to update the database before you can do the locate command in order for the new file to show up.
- man [command] = manual of the command
  - man locate = show the manual of locate
  - can also do [command] --help. locate --help
- env = command to list all your environment variables
  - can use echo $[variable from "env] to check stuff
    - echo $USER = check what user you log in to
    - echo $HOME = check what home directly is

<h2>Network Commands</h2>

- ping [website] = network command, see if you have connectivity to the internet for the website
  - ping www.google.com = check if you can connect to google.com
  - Ctrl + c to quit
- ifconfig = interface config,
  - tells that the network is set up with the display internet address and always has a loopback address
    - eth0; inet = internet address, lo; inet = loopback address or localhost address


  
