# Task 21  [Severity 8] Insecure Deserialization

1. Who developed the Tomcat application?

- Google: Who developed the Tomcat application?

<p align="center">
<br/>
<img src="https://i.imgur.com/nIfYigx.png" height="90%" width="90%" alt=""/>
<br />

Answer: `The Apache Software Foundation`

<h2></h2>

2. What type of attack that crashes services can be performed with insecure deserialization?

<p align="center">
<br/>
<img src="https://i.imgur.com/HBQnXpd.png" height="90%" width="90%" alt=""/>
<br />

Answer: `Denial of Service`

<h2></h2>

# Task 22  [Severity 8] Insecure Deserialization - Objects

1. Select the correct term of the following statement:

- if a dog was sleeping, would this be:

Answer: `A Behaviour`

<h2></h2>

# Task 23  [Severity 8] Insecure Deserialization - Deserialization

1. What is the name of the base-2 formatting that data is sent across a network as?

<p align="center">
<br/>
<img src="https://i.imgur.com/4ikM7xH.png" height="90%" width="90%" alt=""/>
<br />

Answer: `Binary`

<h2></h2>

# Task 24  [Severity 8] Insecure Deserialization - Cookies

1. If a cookie had the path of webapp.com/login , what would the URL that the user has to visit be?

Answer: `webapp.com/login`

<h2></h2>

2. What is the acronym for the web technology that Secure cookies work over?

Answer: `HTTPS`

<h2></h2>

# Task 25  [Severity 8] Insecure Deserialization - Cookies Practical

Copy the IP from the of the active machine on Tryhackme and paste it into the attackbox browser.

<p align="center">
<br/>
<img src="https://i.imgur.com/GyA85uZ.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

1. 1st flag (cookie value)

- Click on "Join Us" and Create an account.

<p align="center">
<br/>
<img src="https://i.imgur.com/KuDo429.png" height="90%" width="90%" alt=""/>
<br />

- Right-Click and select "Inspect".

<p align="center">
<br/>
<img src="https://i.imgur.com/8106Bbj.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the "Storage". Username and Password is stored there.

<p align="center">
<br/>
<img src="https://i.imgur.com/voxnwqX.png" height="90%" width="90%" alt=""/>
<br />

- Go to https://www.base64decode.org. Paste in the value of "sessionId" into the base64decode.

<p align="center">
<br/>
<img src="https://i.imgur.com/rJQRkMR.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{good_old_base64_huh}`

<h2></h2>

2. 2nd flag (admin dashboard)

- Double click on the value of "userType" and change it to "admin".

<p align="center">
<br/>
<img src="https://i.imgur.com/lTdDaL1.png" height="90%" width="90%" alt=""/>
<br />

- Navigate to the /admin on URL.

<p align="center">
<br/>
<img src="https://i.imgur.com/gYnUuwx.png" height="90%" width="90%" alt=""/>
<br />

Answer: `THM{heres_the_admin_flag}`

<h2></h2>

# Task 26  [Severity 8] Insecure Deserialization - Code Execution

- Change back the "userType" cookie from "admin" to "user".

<p align="center">
<br/>
<img src="https://i.imgur.com/rJU5FSc.png" height="90%" width="90%" alt=""/>
<br />

- Click on "vim".

<p align="center">
<br/>
<img src="https://i.imgur.com/KjJtxEK.png" height="90%" width="90%" alt=""/>
<br />

- Click on "feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/hZ0375u.png" height="90%" width="90%" alt=""/>
<br />

- Open up the Terminal:
  - Type in: `nc -lvnp 4444`

<p align="center">
<br/>
<img src="https://i.imgur.com/FfzSH4Y.png" height="90%" width="90%" alt=""/>
<br />
 
- Download the picklelme.py then open another Terminal.
  - Type in: sudo gedit pickelme.py
  - New window will pop up.

<p align="center">
<br/>
<img src="https://i.imgur.com/qhlUKqR.png" height="90%" width="90%" alt=""/>
<br />

- Open another Terminal:
  - Type in: ifconfig to get tryhackme IP Address.

<p align="center">
<br/>
<img src="https://i.imgur.com/M5l30VC.png" height="90%" width="90%" alt=""/>
<br />
 
- Copy and paste the IP into:
  - save it
<p align="center">
<br/>
<img src="https://i.imgur.com/WItzBD7.png" height="90%" width="90%" alt=""/>
<br />

Answer: `4a69a7ff9fd68`
