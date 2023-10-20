# Lab 2 - Blind OS command injection with time delays

<h2>Lab 2: Setup</h2>

<h3>Burp Suite Startup</h3>

- Open up Burp Suite by clicking on the Kali Linux icon on the left upper corner to expand the menu.
  - Type in: "Burp Suite" on the search bar.

<p align="center">
<br/>
<img src="https://i.imgur.com/GBtG9zI.png" height="90%" width="90%" alt=""/>
<br />

- Click on "OK".

<p align="center">
<br/>
<img src="https://i.imgur.com/930R9vx.png" height="60%" width="60%" alt=""/>
<br />

- Click on "I Accept".

<p align="center">
<br/>
<img src="https://i.imgur.com/sI08aew.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Next".

<p align="center">
<br/>
<img src="https://i.imgur.com/mi2gE49.png" height="60%" width="60%" alt=""/>
<br />

- Click on "Start Burp".

<p align="center">
<br/>
<img src="https://i.imgur.com/u28bHJy.png" height="60%" width="60%" alt=""/>
<br />

<h2></h2>

<h3>Intercept Requests Using Burp Proxy</h3>

- Once Burp Suite finished loading, click on "Proxy".

<p align="center">
<br/>
<img src="https://i.imgur.com/TSszN7l.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Open browser".

<h2></h2>

<h3>Navigate to Command Injection Labs in Portswigger On Burp Suite Browser</h3>

- Log in to [PortSwigger](https://portswigger.net/) Website.

- Click on the three line under "MY ACCOUNT" on PortSwigger Website. Then, click on "Academy".

<p align="center">
<br/>
<img src="https://i.imgur.com/bx2sfy8.png" height="90%" width="90%" alt=""/>
<br />

- Click on the expand button. Then, click on "Latest topics" and "View all topics".

<p align="center">
<br/>
<img src="https://i.imgur.com/QhgwDsX.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down and click on "Command Injection".

<p align="center">
<br/>
<img src="https://i.imgur.com/SjhFwI3.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down and click on the lab "Blind OS command injection with time delays".

<p align="center">
<br/>
<img src="https://i.imgur.com/ux1qnsl.png" height="90%" width="90%" alt=""/>
<br />

- Click on "ACCESS THE LAB".

<p align="center">
<br/>
<img src="https://i.imgur.com/Sa088XR.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Visual Studio Code Downloads</h3>

- Open up Visual Studio Code. Import the file below to Visual Studio Code.
  - Click on "Download raw file".
      - [command-injection-lab-02.py](https://github.com/rkhal101/Web-Security-Academy-Series/blob/main/command-injection/lab-02/command-injection-lab-02.py)
   
<p align="center">
<br/>
<img src="https://i.imgur.com/kvE9jA0.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h2>Lab Solution</h2>


- Navigate to Burp Suite turn Intercept On by clicking on "Intercept is off".

<p align="center">
<br/>
<img src="https://i.imgur.com/YzGDBNL.png" height="90%" width="90%" alt=""/>
<br />


- Navigate to the Intercept Browser, click on "Submit feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/Guu4sL6.png" height="90%" width="90%" alt=""/>
<br />


- Navigate back to Burp Suite turn Intercept On by clicking on "Intercept is on".

<p align="center">
<br/>
<img src="https://i.imgur.com/ysjlWSa.png" height="90%" width="90%" alt=""/>
<br />

- Navigate back to the Intercept Browser, fill in the "Submit feedback".
  - Name: "test".
  - Email: "test@test.ca".
  - Subject: "test".
  - Message: "test".
- Click on "Submit feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/NC4g5Og.png" height="90%" width="90%" alt=""/>
<br />

- The response from the form is just "Thank you for submitting feedback!
  - Doesn't give you the response of the request that you performed.
  - If any of the field is vulnerable to command injection, it could be "Blind command injection" instead of "In-band command injection".

<p align="center">
<br/>
<img src="https://i.imgur.com/ku8AmLI.png" height="90%" width="90%" alt=""/>
<br />
 
- Notice a "post request" for "feedback/submit" have generated on Burp Suite on the HTTP history tab.

<p align="center">
<br/>
<img src="https://i.imgur.com/8Xvx7xY.png" height="90%" width="90%" alt=""/>
<br />
 
- Click on the post request. Right-click on the request on the bottom and select "Send to Repeater". 

<p align="center">
<br/>
<img src="https://i.imgur.com/923w5PN.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Repeater".
  - From the repeater, we can see it takes parameters in CSF, name, email, subject, and email.

<p align="center">
<br/>
<img src="https://i.imgur.com/tP15upe.png" height="90%" width="90%" alt=""/>
<br />
 
<h2></h2>

<h2>Testing for Potential Injection Vulnerabilities</h2>

We are going to test each parameter for potential injection vulnerabilities.