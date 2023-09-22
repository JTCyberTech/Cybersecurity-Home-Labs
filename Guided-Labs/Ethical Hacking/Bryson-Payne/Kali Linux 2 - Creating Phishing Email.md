#Creating a Phishing using Kali Linux

<h2>Description:</h2>

- Using Kali Linux and Windows VM creating a Phishing Email by using the Social Engineering Toolkit.


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
    - The website will be a clone of facebook login page



8. Enter in the email and password

9. Terminal will capture the possible username and password

<p align="left">
Terminal Username and Password <br/>
<img src="https://i.imgur.com/A4wyhyV.png" height="35%" width="35%" alt=""/>
<br />
