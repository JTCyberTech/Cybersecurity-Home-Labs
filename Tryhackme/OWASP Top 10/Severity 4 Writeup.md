# Task 13  [Severity 4] XML External Entity - eXtensible Markup Language

1. Full form of XML

<p align="center">
<br/>
<img src="https://i.imgur.com/H7uorOp.png" height="90%" width="90%" alt=""/>
<br />

Answer: `eXtensible Markup Language`

<h2></h2>

2. Is it compulsory to have XML prolog in XML documents?

<p align="center">
<br/>
<img src="https://i.imgur.com/PHnLebL.png" height="90%" width="90%" alt=""/>
<br />

Answer: `No`

<h2></h2>

3. Can we validate XML documents against a schema?

<p align="center">
<br/>
<img src="https://i.imgur.com/105fmIi.png" height="90%" width="90%" alt=""/>
<br />

Answer: `Yes`

<h2></h2>

4. How can we specify XML version and encoding in XML document?

<p align="center">
<br/>
<img src="https://i.imgur.com/TYoPu3M.png" height="90%" width="90%" alt=""/>
<br />

Answer: `XML Prolog"

<h2></h2>

# Task 14  [Severity 4] XML External Entity - DTD

1. How do you define a new ELEMENT?

<p align="center">
<br/>
<img src="https://i.imgur.com/emyUUKD.png" height="90%" width="90%" alt=""/>
<br />

Answer: `!ELEMENT`

<h2></h2>

2. How do you define a ROOT element?

<p align="center">
<br/>
<img src="https://i.imgur.com/oO9reyq.png" height="90%" width="90%" alt=""/>
<br />

Answer: `!DOCTYPE`

<h2></h2>

3. How do you define a new ENTITY?

Answer: `!ENTITY`


<h2></h2>

# Task 16  [Severity 4] XML External Entity - Exploiting

Copy the IP from the of the active machine on Tryhackme and paste it into the attackbox browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/kby1a9z.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. Try to display your own name using any payload.

<p align="center">
<br/>
<img src="https://i.imgur.com/kb5C5yh.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

2. See if you can read the /etc/passwd

- Google: "XXE /etc/passwd".
- Click on "Classic XXE - etc passwd.xml

<p align="center">
<br/>
<img src="https://i.imgur.com/kAT3VSZ.png" height="90%" width="90%" alt=""/>
<br />

- Copy the whole code.

<p align="center">
<br/>
<img src="https://i.imgur.com/hDA5TLr.png" height="90%" width="90%" alt=""/>
<br />

- Paste it in the payload page.

<p align="center">
<br/>
<img src="https://i.imgur.com/YJdpf8q.png" height="90%" width="90%" alt=""/>
<br />

- Dumped the XXE password.

<p align="center">
<br/>
<img src="https://i.imgur.com/wcSseUN.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

3. What is the name of the user in /etc/passwd

<p align="center">
<br/>
<img src="https://i.imgur.com/RIlgquq.png" height="90%" width="90%" alt=""/>
<br />

Answer: `falcon`

<h2></h2>

4. Where is falcon's SSH key located?

- SSH Key location is usually stored: "/home/[yourusername]/.ssh/id_rsa"

Answer: `/home/falcon/.ssh/id_rsa`

<h2></h2>

5. What are the first 18 characters for falcon's private key

- Enter: "/home/falcon/.ssh/id_rsa" in the payload.

<p align="center">
<br/>
<img src="https://i.imgur.com/7IMCKbI.png" height="90%" width="90%" alt=""/>
<br />

Answer: `MIIEogIBAAKCAQEA7b`
