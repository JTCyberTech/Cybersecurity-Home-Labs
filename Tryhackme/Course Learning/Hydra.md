# What is Hydra?

Functionality:

- Hydra is a quick system login password "hacking" tool.
- It performs brute force attacks to crack passwords for various authentication services.

Authentication Services:

- Hydra can be used to brute force passwords for services like SSH, Web Application Forms, FTP, and SNMP.
- Speeds up the process of determining the correct password by running through a password list.

Supported Protocols:

- Hydra supports a wide range of protocols for brute force attacks.
- Protocols include Asterisk, AFP, Cisco AAA, Cisco auth, Cisco enable, CVS, Firebird, and many others.

Protocols Covered:

- HTTP and HTTPS protocols, both form-based and through GET and POST requests.
- Various database-related protocols like MySQL, MS-SQL, MONGODB, Oracle, and POSTGRES.
- Communication protocols such as IMAP, IRC, LDAP, SNMP, SIP, SMB, and SMTP.
- Remote access protocols like RDP, Rexec, Rlogin, and VNC.
- Miscellaneous protocols like SOCKS5, Telnet, and XMPP.

Wide Range of Services:

- Covers services used in networking, databases, remote access, and communication.

Versatility:

- Provides a versatile solution for penetration testing and security assessments.
- Can be used to identify vulnerabilities in systems by testing password strength across different services.

SSH Support:

- Supports both SSH versions 1 and 2, as well as SSHKEY authentication.

Use in Security Assessments:

- Often utilized in ethical hacking and security assessments to identify weak passwords and enhance system security.

Repository Information:

- Information sourced from Hydra's official repository.

Comprehensive Coverage:

- Encompasses a broad spectrum of protocols and services, making it a comprehensive tool for password testing and penetration testing.

#

It's crucial to have a strong password. If your password is simple, lacks special characters, and is less than eight characters, it's easier to guess. There's a list of a hundred million common passwords, so if an application uses an easy password by default, change it! Default logins like `admin:password`, often used by CCTV cameras and web frameworks, are not secure enough and should be updated.

# 

# Installing Hydra

Hydra Installation on AttackBox:

- Hydra is already installed on the AttackBox.
- Accessible by clicking the "Start AttackBox" button.

In-Browser Kali Machine:

- Hydra is pre-installed on the in-browser Kali machine.
- Accessible by selecting "Use Kali Linux" and clicking "Start Kali Linux."

Hydra on Other Linux Distributions:

- Check official repositories for other Linux distributions if not using AttackBox or Kali.
- Example installations:
  - On Ubuntu: `apt install hydra`
  - On Fedora: `dnf install hydra`
- Download available from the official THC-Hydra repository.

#

# Deploy Machine

Temporary IP Address: [10.10.212.196]

Deploy the machine attached to this task, then navigate to http://10.10.212.196

# 

# Hydra Commands

Hydra Commands for FTP Brute Force:

- Dependent on the service (protocol) being attacked.
- Example: Brute forcing FTP with username `user` and password list `passlist.txt`.
- Command: `hydra -l user -P passlist.txt ftp://10.10.212.196`

Commands for Deployed Machine (SSH and Web Form - POST Method):

- Specifies the use of Hydra on SSH and a web form with the POST method.
- Actual commands for SSH and web form attacks are not provided in the given text.

Service-Specific Configuration:

- Emphasizes that the options passed into Hydra depend on the service or protocol under attack.
- Indicates the need for tailoring Hydra commands based on the target service and its requirements.

Example for FTP Brute Force:

- Illustrates the FTP brute force example with the specified username and password list.
- Provides a clear command format using Hydra for the FTP attack scenario.

# 

# SSH

Command: `hydra -l <username> -P <full path to pass> 10.10.212.196 -t 4 ssh`

Options and Descriptions:

- `-l`: Specifies the (SSH) username for login.
- `-P`: Indicates a list of passwords. You need to provide the full path to the file containing the passwords.
- `-t`: Sets the number of threads to spawn for parallel processing.

Example: `hydra -l root -P passwords.txt 10.10.212.196 -t 4 ssh`

- Hydra will use "root" as the username for SSH.
- It will try the passwords listed in the "passwords.txt" file.
- The attack will run with four threads in parallel, as indicated by -t 4.

Explanation:

- This command is attempting to perform a brute-force attack on an SSH server with the IP address 10.10.212.196.
- It uses the username "root" and a list of passwords provided in the "passwords.txt" file.
- The -t 4 option indicates that Hydra will use four threads for parallel processing, potentially speeding up the attack.
- Please note that brute-force attacks are generally considered unethical and are likely against the terms of service of most systems. Always ensure you have proper authorization before attempting such actions.

#

# Post Web Form

SSH Brute Force: `hydra -l <username> -P <full path to pass> 10.10.212.196 -t 4 ssh`

- `-l`: Specifies the username for the SSH login.
- `-P`: Specifies the full path to the password list.
- `10.10.212.196`: Target IP address.
- `-t 4:` Specifies the number of parallel tasks (threads) to perform the attack.
- `ssh`: Specifies the service to attack (in this case, SSH).

HTTP POST Form Brute Force: `sudo hydra <username> <wordlist> 10.10.212.196 http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V`

- `<username>`: Placeholder for the username.
- `<wordlist>`: Placeholder for the wordlist containing passwords.
- `10.10.212.196`: Target IP address.
- http-post-form: Specifies the type of form attack (POST method).
- "`/:username=^USER^&password=^PASS^:F=incorrect"`: Specifies the login page URL, login credentials, and the string indicating failed login.
  - `/`: The login page URL is the main IP address.
  - `username=^USER^&password=^PASS^`: Form fields for username and password.
  - `F=incorrect`: String indicating an incorrect login response.
- `-V`: Enables verbose output for every attempt.

Explanation:

- These commands are designed for password brute-forcing on an SSH service and an HTTP POST login form.
- The provided information explains the placeholders and the structure of the command, guiding users on how to customize the commands for their specific target.

Note:

- Brute-forcing is typically illegal and unethical unless performed on systems you own or have explicit permission to test. Unauthorized access attempts can result in serious consequences. Always ensure you have the legal right and authorization to perform such actions.

#

# Use Hydra to bruteforce in molly's web password

In order to bruteforce we will first check out the webpage. I will be using burp suite's browser for interception.

Navigate to the IP Address [10.10.212.196].

<p align="center"> <img src="https://i.imgur.com/Peqbglg.png" height="90%" width="90%" alt=""/>

Put in random things for username and password to login on the webpage > Turn Intercept on > Click on "Login".

<p align="center"> <img src="https://i.imgur.com/ccTCCTl.png" height="90%" width="90%" alt=""/>

We got the interception. We got the <login_credentials>: `username=a&password=a` which is `username=^USER^&password=^PASS^`.

<p align="center"> <img src="https://i.imgur.com/moBTpY7.png" height="90%" width="90%" alt=""/>

We will now click on the "Forward" button to see the <invalid_response>: `Your username or password is incorrect.`

<p align="center"> <img src="https://i.imgur.com/JWJjzuP.png" height="90%" width="90%" alt=""/>

We came up with the full command to bruteforce: hydra -l molly -P rockyou.txt  10.10.212.196 http-post-form "/login:username=^USER^&password=^PASS^:Your username or password is incorrect." -V

- `hydra`: The command itself, invoking the Hydra tool.

- `-l molly`: Specifies the login username to be "molly."

- `-P rockyou.txt`: Specifies the path to a file containing a list of passwords (rockyou.txt in this case).

- `10.10.212.196`: The IP address of the target system.

- `http-post-form`: Indicates the type of attack, in this case, it's an HTTP POST form-based attack.

- `"/login:username=^USER^&password=^PASS^:Your username or password is incorrect."`:

  -Specifies the login form details:
    - `/login`: The URL of the login page.
    - `username=^USER^&password=^PASS^`: The form data to be sent, where ^USER^ and ^PASS^ will be replaced by Hydra during the brute-force attack.
    - `Your username or password is incorrect`.: The failure message indicating an unsuccessful login attempt.
- `-V`: Enables verbose mode. It provides more detailed output during the attack, showing the progress and results.

In summary, this command uses Hydra to perform a brute-force attack on an HTTP login form located at /login on the target IP address (10.10.212.196). The attack uses the username "molly" and a list of passwords from rockyou.txt. The results of the attack are displayed with additional details due to the -V flag. Always ensure you have proper authorization before attempting any form of password brute-force or penetration testing, as unauthorized access attempts may be illegal.

Successfully got molly's password to be `sunshine`.

<p align="center"> <img src="https://i.imgur.com/WV2RQLI.png" height="90%" width="90%" alt=""/>

Put in the username and password on the webpage > Click on "login".

<p align="center"> <img src="https://i.imgur.com/j2DUlhE.png" height="90%" width="90%" alt=""/>

Successfully captured the flag for flag1.

<p align="center"> <img src="https://i.imgur.com/3zO1Azy.png" height="90%" width="90%" alt=""/>

`THM{2673a7dd116de68e85c48ec0b1f2612e}`

#

# Use Hydra to bruteforce molly's SSH password

We will just use this command:

`hydra -l molly -P rockyou.txt 10.10.212.196 -t 4 ssh`

- `hydra`: The command itself, invoking the Hydra tool.

- `-l molly`: Specifies the login username to be "molly."

- `-P rockyou.txt`: Specifies the path to a file containing a list of passwords (rockyou.txt in this case).

- `10.10.212.196`: The IP address of the target system.

- `-t 4`: Specifies the number of parallel tasks or threads to use during the attack. In this case, it's set to 4 threads.

- `ssh`: Specifies the target service as SSH. Hydra supports various protocols, and in this case, it's attempting to perform a brute-force attack on an SSH service.

When you run this command, Hydra will use the provided username "molly" and passwords from the "rockyou.txt" wordlist to attempt to log in to the SSH service on the target system (IP address 10.10.212.196). The -t 4 option allows Hydra to perform the attack using multiple threads, making the process more efficient.

Please note that attempting to gain unauthorized access to systems is unethical and likely illegal. Always ensure you have proper authorization before conducting any security testing.

- Successfully capture molly's password for ssh

<p align="center"> <img src="https://i.imgur.com/sBf3wz2.png" height="90%" width="90%" alt=""/>

Login to molly's ssh:

`ssh molly@10.10.212.196`

- `ssh`: This is the command-line tool used to establish a secure shell connection to a remote server.

- `molly`: This is the username used to log in to the remote server. Replace it with the appropriate username for your situation.

- `@`: The "@" symbol is used to separate the username from the host IP address.

- `10.10.212.196`: This is the IP address of the remote server. Replace it with the actual IP address or hostname of the server you want to connect to.

When you run this command, it prompts you for the password associated with the specified username on the remote server. If the password is correct and the user has the necessary permissions, an SSH session is established, allowing you to interact with the remote server's command-line interface.

Keep in mind that for security reasons, using SSH keys for authentication is recommended over password-based authentication. Also, ensure that you have the proper authorization to access the remote server. Unauthorized access attempts are unethical and may be illegal.

<p align="center"> <img src="https://i.imgur.com/yKX6QEv.png" height="90%" width="90%" alt=""/>

Type in: `yes` > Put in the password: `butterfly`.

- Successfully login to molly's ssh.

<p align="center"> <img src="https://i.imgur.com/AziJ1hq.png" height="90%" width="90%" alt=""/>

Use `ls` command to list all files in the current directory > Use `cat` command to read the flag2.txt.

- Successfully capture the flag for flag2.

<p align="center"> <img src="https://i.imgur.com/JzVrrmj.png" height="90%" width="90%" alt=""/>

`THM{c8eeb0468febbadea859baeb33b2541b}`
