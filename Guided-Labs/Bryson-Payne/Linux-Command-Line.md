# Kali Linux Command Line

<h2>Beginner Linux Terminal Commands:</h2>

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

<h2>Intermediate Linux Terminal Commands:</h2>

- Display output like a table (| column -t):
  - mount column -t
  - cat /etc/passwd | column -t -s :
- Go back to previous directory: cd -
- Turn on aliases in your .bashrc:
  -  alias Ll='ls -l'
  -  alias La='ls -a'
-  Run multiple commands:
  -  ; (in order)
  -  && (if successful)
-  Reuse last argument: ! $
-  Reuse last command: ! ! (e.g. sudo !!)
-  Reverse text (rev): echo hello | rev
-  Draw banner letters (figlet): figlet hello
-  clear [also ctrl+L]
-  cal [calendar] factor 24 [factors...] > filename [empty file]
-  head [top of file] tail [last few lines] grep [superfind]


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

- mkdir [name] = create a directory with the [name], basically create a folder
- rmdir [name] = remove a directory, basically delete a folder
- echo hello > file.txt = create a .txt name file and write "hello" in the .txt
- more file.txt = show the contents of the [file.txt], in this case, will only show "hello"
  - return: hello
- cp file.txt myfile.txt = copy "file.txt" and create another .txt call "myfile". Will have both .txt afterward
- mv myfile.txt textfile.txt = rename "myfile.txt" to "textfile.txt"
  - can also use this command to move a file into a folder; mv myfile.txt Folder1 = move myfile.txt to Folder1
- rm file.txt = remove "file.txt"
- nano textfile.txt = open up text editor
  - Ctrl + O to save, ctrl + X to exit

<h2></h2>

<h2>Helpful Linux Commands</h2>

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

<h2></h2>

<h2>Intermediate Commands</h2>
  
- mount = command that tells you all the devices that are connected
  - mount | column -t = do tab space for our column to make the mount command more readable
    - | = pipe; will take the output of one command and send it to another
    - column -t = tab space for column
- cat /etc/passwd = command that shows all of the users 
  - cat /etc/passwd | column -t -s : = do tab space for our column more readable and separate each column when it have :
- cd - = takes you back to one directory that you were at
- alias [name="command"] = you can rename a command so it will be more convenient to type in the command
  - alias ll='ls -l' = When you type ll, it will automatically do the command: ls -l
  - alias will only be stored in each session, if you close kali linux then the alias will not work next time
    - can use the command "nano .bashrc" to save alias for future use
      - nano .bashrc then scroll down to the aliases section and customize it
- ; = separate multiple commands
  - "command 1" ; "command 2" = will execute command 1 first then do command 2
  - sleep 5 ; echo "hello" = wait 5 seconds then write hello
- && = do the first command then do the second command only if the first command does not error out
- !$ = reuse last argument
  - column -t
    - use: column !$; will output; column -t
- !! = reuse last command
  - if a command needs sudo to use; "service network-manager restart"; it will not work
    - can use: sudo !!; this will make !! = last command, so it will become; "sudo service network-manager restart"
- echo hello | rev = write "hello" in reverse
  - return: olleh
- figlet hello = Draw banner for "hello"
- clear or ctrl+L = clear the whole command line
- cal = show this month's calendar
- factor 24 = quickly calculate the prime factor of 24
- "[command] > filename" = put a command in a file
  - "echo hello > filename" = write hello in the filename
- head = read the first 10 lines of a file
  - head file.txt
- tail = read the last 10 lines of a file
  - tail file.txt
- grep = super find, find one line in a file
  - grep "hello" file.txt
