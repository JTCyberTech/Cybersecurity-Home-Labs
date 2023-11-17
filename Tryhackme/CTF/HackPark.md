# HackPark

Room [HackPark](https://tryhackme.com/room/hackpark)

#

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "HackPark".

`mkdir HackPark`

- Change directory into HackPark.

`cd HackPark/`

<p align="center"> <img src="https://i.imgur.com/LcGUjmv.png" height="90%" width="90%" alt=""/>

<h2></h2>

<h3>Deploy the Machine</h3>

Deploy the machine by connecting to TryHackMe network. 

Temporary IP Address: [10.10.251.165]

Introduction: 
This room will cover brute-forcing an accounts credentials, handling public exploits, using the Metasploit framework and privilege escalation on Windows.

Whats the name of the clown displayed on the homepage?

`Pennywise`

<p align="center"> <img src="https://i.imgur.com/6zPepbG.png" height="90%" width="90%" alt=""/>

#

# Reconnaissance

Gather the Information from the Target Machine with `Nmap` Command. Find the open ports on the machine.

On Terminal: `nmap -sC -sV -oN nmap_initial.txt 10.10.251.165`

- `nmap`: This is the command used to run the Nmap tool.
- `-sC`: To perform script scanning.
- `-sV`: To detect the version of services.
- `-oN nmap_initial.txt`: To save the scan results in a file named "nmap_initial.txt."
- The target IP address is `10.10.251.165`.

<p align="center"> <img src="https://i.imgur.com/s5HluDR.png" height="90%" width="90%" alt=""/>

#

# Using Hydra to brute-force a login Question

Question 1: What request type is the Windows website login form using?

Question 2: Guess a username, choose a password wordlist and gain credentials to a user account!

#

# Question 1

We want to locate a login page to investigate and figure out the kind of communication it has with the web server. Normally, web servers have two types of communication: a GET request, which is for asking the server for information, and a POST request, which is for sending data to the server.

To find out what type of request a form is using, you can right-click on the login form, choose "Inspect," and then look for the value in the "method" field. Alternatively, if you're using BurpSuite to intercept the traffic, you can also discover this information there (you can find other HTTP methods there too).

Open up Burp Suite > Go to "Proxy" Tab > Open Browser.

<p align="center"> <img src="https://i.imgur.com/EW2Vrrh.png" height="90%" width="90%" alt=""/>

Navigate to the webpage > Click on the three lines on Upper right corner > Select "LOG IN".

<p align="center"> <img src="https://i.imgur.com/svMJeJO.png" height="90%" width="90%" alt=""/>

On the log in page, type in random stuff for username and password > Turn ON "interception" on Burp Suite > Click on "LOG IN" on Webpage.

<p align="center"> <img src="https://i.imgur.com/Eo0BZnp.png" height="90%" width="90%" alt=""/>

We got the request type is using POST request for the Windows website login form.

<p align="center"> <img src="https://i.imgur.com/gUXUBLo.png" height="90%" width="90%" alt=""/>

Question 1: What request type is the Windows website login form using?

`POST`

#

# Question 2


Now we know the request type and have a URL for the login form, we can get started brute-forcing an account.

But First we will highlight what we need for the hydra command.
- The first line between "POST" and "HTTP/1.1".
- The whole section of "VIEWSTATE" and "EVENTVALIDATION".
- The Login failed message.

<p align="center"> <img src="https://i.imgur.com/RoXeBLS.png" height="90%" width="90%" alt=""/>

To obtain the login fail message > Click on Forward on Burp Suite.
- Failed login message: "Login failed".

<p align="center"> <img src="https://i.imgur.com/1PW5az2.png" height="90%" width="90%" alt=""/>

Now we will bruteforce the webpage with "admin" as username to gain admin privileges.

On terminal we will run the following command: 

`hydra -l admin -P ../../wordlists/rockyou.txt 10.10.251.165 http-post-form "/Account/login.aspx?ReturnURL=/admin:__VIEWSTATE=UqdXYcNqgKHpn2%2BpdCIS3gYnqlac%2BKkIxoetD53FHHWChj8DB%2B4imTd8kwTha5WfDrtnKbjHCmkSqPlh3eIfc5DiqyhR5hjO%2BawjD3VznS7A0z4z19Fx0ahHdfYZGz6PTlRSsbkilSS0EUCBxA0%2BRZkdnf2x9zBwZA6G9Rh%2FrnXLK8WtC9%2FQKeFg0tb0EK9UDMwliypjbrq8Uh1%2BndI%2BAMxJbcyD5eZtNgKnV4P%2FN3%2Bc5XccnNy%2FtFDR0rpd6DxBFI0A1zL2EiWg540RIPGv9IvgDP9FayCb6Rm8Os75p3bD7yrYb4w3dVqLfjc%2FTaSV597%2BiZ%2BDRiaGILoVaUP7cwVBLNFl76F18NM9vNhpmUDRcWvj&__EVENTVALIDATION=y5nRmLKKmybfVqMpVqlCjWjWLKwuxTmpxmJH8gzayJTJTbOIDNXGTOYBOFRaeuRrCp%2FUSW7%2F9JCcXJlCNzxTq9IGJKrC29fTnMYo4XHdoyj6B4Bq88xKa0Dpez4zxsBbIzHGsLQFW3%2BolDEi5vGQGd5W1Od7DQ7u55Jx8iLJEKApamOE&ctl00%24MainContent%24LoginUser%24UserName=^USER^&ctl00%24MainContent%24LoginUser%24Password=^PASS^&ctl00%24MainContent%24LoginUser%24LoginButton=Log+in:Login Failed" -vv`

- `hydra`: The command itself, invoking the Hydra tool.

- `-l admin`: Specifies the login username to be "admin."

- `-P ../../wordlists/rockyou.txt`: Specifies the path to a file containing a list of passwords (../../wordlists/rockyou.txt in this case).

- `10.10.251.165`: The IP address of the target system.

- `http-post-form`: Indicates the type of attack, in this case, it's an HTTP POST form-based attack.

- `"/Account/login.aspx?ReturnURL=/admin: ... : Login Failed"`:
  - Specifies the login form details:
    - `/Account/login.aspx?ReturnURL=/admin`: The URL of the login page.
    - `The long string after the colon (:)` represents various parameters that are part of the POST request, including ViewState, EventValidation, and the login form fields.
    - `^USER^` and `^PASS^`: are placeholders that Hydra will replace with the actual username and password during the brute-force attack.
    - `Login Failed`: The failure message indicating an unsuccessful login attempt.
- `-vv`: (verbose) option is used to increase the verbosity of the output. 

We changed:

- `/Account/login.aspx?ReturnURL=%2fadmin%2f` into: `/Account/login.aspx?ReturnURL=/admin`
- `UserName=a` into `UserName=^USER^`
- `Password=a` into `Password=^PASS^`

Added in:

- `:Login Failed` for login message.


Question 2: Guess a username, choose a password wordlist and gain credentials to a user account!

