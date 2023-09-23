#Creating a Phishing using Kali Linux

<h2>Description:</h2>

- Using Kali Linux and Windows VM to create a Phishing Email by using the Social Engineering Toolkit.


<h2>Environment Used</h2>

Navigate to [VM Network Configuration](https://github.com/jefftsui1/Cybersecurity-Home-Labs/blob/main/Guided-Labs/Ethical%20Hacking/Bryson-Payne/VM%20Networking%20Configuration.md) to set up the Networks
- Kali Linux VM and Windows VM: 
  - Network Attached to: NAT Network
  - Name: PublicNAT
  - IP Address = 10.0.9 Network; 10.0.9.4
 
<h2></h2>

<h2>Launching Social Engineer's Toolkit</h2>

1. Open up Kali Linux on the Oracle VM Application

2. Click on the top left corner of the VM for application > Scroll down to Social Engineering Tools > SET: social engineering toolkit (root)

<p align="left">
Social Engineering Toolkit Navigation <br/>
<img src="https://i.imgur.com/nULIHzq.png" height="35%" width="35%" alt=""/>
<br />

3. Terminal will open:
    - Type in your password and enter
    - Type in: y and enter to accept the term of service

<h2></h2>

<h2>Cloning Facebook and Harvesting User Passwords</h2>

1. Select from menu 1) Social-Engineering Attacks

2. Select from menu 2) Website Attack Vectors

3. Select from menu 3) Credential Harvester Attack Method

4. Select from menu 2) Site cloner

5. Check if your Kali Linux can get a connection to the internet
    - Using the ping command; ping www.google.com

6. Enter the URL to clone:
    - Type in: www.facebook.com

7. Go on the Firefox Browser
    - On the URL type in: localhost or 10.0.9.4
    - The website will be a clone of Facebook login page

8. Enter the email and password

9. Terminal will capture the possible username and password

<p align="left">
Terminal Username and Password <br/>
<img src="https://i.imgur.com/A4wyhyV.png" height="35%" width="35%" alt=""/>
<br />

<h2></h2>

<h2>Using Website Template to Steal Username and Password</h2>

1. Select from menu 1) Social-Engineering Attacks

2. Select from menu 2) Website Attack Vectors

3. Select from menu 3) Credential Harvester Attack Method

4. Select from menu 1) Web Template

5. Check if the IP address is accessible to the internet

6. Select 3) Twitter

7. Go on the Firefox Browser
    - On the URL type in: localhost or 10.0.9.4
    - The website will be a clone of the Twitter login page
  
8. Enter the email and password

9. The terminal will capture the possible username and possible password

<p align="left">
Terminal Username and Password <br/>
<img src="https://i.imgur.com/8aMefdb.png" height="35%" width="35%" alt=""/>
<br />
   
   
<h2></h2>

<h2>Using legit email to create a phishing email</h2>

1. For this example: I used my LinkedIn email but altered their names and titles

<p align="left">
My Legit LinkedIn Email With Name Altered<br/>
<img src="https://i.imgur.com/3uqApDw.png" height="35%" width="35%" alt=""/>
<br />

2.  I altered each of the hyperlinks to be my Setoolkit's site cloner link
    - In this case my IP Address: http://10.0.9.4/

<p align="left">
Altering the Hyperlink<br/>
<img src="https://i.imgur.com/NWvfMTE.png" height="35%" width="35%" alt=""/>
<br />

3.  I have altered all of the hyperlinks to http://10.0.9.4/ or the trap.
    - Every red rectangle are clickable hyperlink that can be altered 

<p align="left">
All Alternated Hyperlink<br/>
<img src="https://i.imgur.com/GicARqm.png" height="35%" width="35%" alt=""/>
<br />

4.  The phishing email is ready to be sent
    - Once the victim clicks on the link will take them to the cloned site of LinkedIn

<p align="left">
Cloned Login page of LinkedIn<br/>
<img src="https://i.imgur.com/DqVUNXM.png" height="35%" width="35%" alt=""/>
<br />

5.  Once the victim enters their Email and Password, the Setoolkit will pick up the login credentials
    - Login Credential Example:
      - Email: Johnsmith@gmail.com
      - Password: NotApassword

<p align="left">
Setoolkit Hacked Login Credentials<br/>
<img src="https://i.imgur.com/wVy1P76.png" height="35%" width="35%" alt=""/>
<br />   

    


