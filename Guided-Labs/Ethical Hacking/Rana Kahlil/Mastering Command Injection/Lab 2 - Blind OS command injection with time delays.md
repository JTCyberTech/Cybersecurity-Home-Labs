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

- Turn Intercept on clicking on "Intercept is off".
