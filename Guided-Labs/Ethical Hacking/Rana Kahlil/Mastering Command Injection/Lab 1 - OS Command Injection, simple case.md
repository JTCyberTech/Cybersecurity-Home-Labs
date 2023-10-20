# Lab 1 - OS Command Injection, simple case

<h2>Lab 1: Setup</h2>

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

- Scroll down and click on the lab "OS command injection, simple case".

<p align="center">
<br/>
<img src="https://i.imgur.com/GfkvP20.png" height="90%" width="90%" alt=""/>
<br />

- Click on "ACCESS THE LAB".

<p align="center">
<br/>
<img src="https://i.imgur.com/Sa088XR.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Visual Studio Code Downloads</h3>

- Open up Visual Studio Code. Import the 2 files below to Visual Studio Code.
  - Click on "Download raw file".
    - [notes.txt](https://github.com/rkhal101/Web-Security-Academy-Series/blob/main/command-injection/lab-01/notes.txt)
    - [command-injection-lab-01.py](https://github.com/rkhal101/Web-Security-Academy-Series/blob/main/command-injection/lab-01/command-injection-lab-01.py)
   
<p align="center">
<br/>
<img src="https://i.imgur.com/2PeJimo.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>




<H2></H2>

<h2>Lab Solution</h2>

- Turn Intercept on clicking on "Intercept is off".

<p align="center">
<br/>
<img src="https://i.imgur.com/3tkeGZY.png" height="90%" width="90%" alt=""/>
<br />

- After turning on Intercept. Click on "View details" on the first item.

<p align="center">
<br/>
<img src="https://i.imgur.com/DwAVaXJ.png" height="90%" width="90%" alt=""/>
<br />

- Set "Intercept" off. Navigate to HTTP history.

<p align="center">
<br/>
<img src="https://i.imgur.com/aIermKp.png" height="90%" width="90%" alt=""/>
<br />

- Scroll down on the browser, and click on "Check stock".

<p align="center">
<br/>
<img src="https://i.imgur.com/yBUdpeu.png" height="90%" width="90%" alt=""/>
<br />

- Notice a "post request" have generated on Burp Suite.

<p align="center">
<br/>
<img src="https://i.imgur.com/G2PcVo8.png" height="90%" width="90%" alt=""/>
<br />

- Click on the post request. Right-click on the request on the bottom and select "Send to Repeater".

<p align="center">
<br/>
<img src="https://i.imgur.com/5iN0fu8.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Repeater".
  - From the repeater, we can see it takes two parameters in the "product ID" and "store ID".

<p align="center">
<br/>
<img src="https://i.imgur.com/za4PZiC.png" height="90%" width="90%" alt=""/>
<br />

<h2>Testing for Potential Injection Vulnerabilities</h2>

We are going to test each parameter for potential injection vulnerabilities.

ProductID:

- Adding "&" for chainning command. Then "whoami" to run Who Am I command.
  - Add in: productId=1``` & whoami```&storeI=1

<p align="center">
<br/>
<img src="https://i.imgur.com/LfHO8Pk.png" height="90%" width="90%" alt=""/>
<br />

- Since we don't have the source code for this application, we are going to tweak our command injection based on the response of the application.
  - Highlight ``` & whoami``` and press "Ctrl + U" on keyboard to encoded it. Then, Click "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/eAtUcMq.png" height="90%" width="90%" alt=""/>
<br />

- 
