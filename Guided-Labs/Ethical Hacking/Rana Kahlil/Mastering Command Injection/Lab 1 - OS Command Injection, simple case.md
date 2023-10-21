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

<h2>Lab Solution</h2>

- Turn Intercept by clicking on "Intercept is off".

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

<h2></h2>

<h2>Testing for Potential Injection Vulnerabilities</h2>

We are going to test each parameter for potential injection vulnerabilities.

<h3>ProductID:</h3>

- Adding "&" for chainning command. Then "whoami" to run Who Am I command.
  - Add in: productId=1``` & whoami```&storeI=1 .

<p align="center">
<br/>
<img src="https://i.imgur.com/LfHO8Pk.png" height="90%" width="90%" alt=""/>
<br />

- Since we don't have the source code for this application, we are going to tweak our command injection based on the response of the application.
  - Highlight ``` & whoami``` and press "Ctrl + U" on keyboard to encode it. Then, Click on "Send".
  - The command turns into: ```productId=1+%26+whoami&storeId=1```.

<p align="center">
<br/>
<img src="https://i.imgur.com/eAtUcMq.png" height="90%" width="90%" alt=""/>
<br />

- Ran into an error while running the "Whoami" Command.
  - On line 5, it says it's unbound variable.

<p align="center">
<br/>
<img src="https://i.imgur.com/k9SoXnf.png" height="90%" width="90%" alt=""/>
<br />

- Add a "#" to comment out the rest of the command.
  - Add in: productId=1+%26+whoami``` #```&storeId=1 .
  - highlight ``` #``` and press "Ctrl + U" on keyboard to encode it. Then, Click on "Send".
  - The command turns into: ```productId=1+%26+whoami+%23&storeId=1```.

<p align="center">
<br/>
<img src="https://i.imgur.com/Bqb9wgu.png" height="90%" width="90%" alt=""/>
<br />
 
- We no longer got an error.
  - Got the value of: "peter-noZB5X".

<p align="center">
<br/>
<img src="https://i.imgur.com/xplQKTe.png" height="90%" width="90%" alt=""/>
<br />

<h3>StoreID: </h3>

- We can also do it for StoreID side:
  - Adding "&" for chainning command. Then "whoami" to run Who Am I command.
  - Add in: productId=1&storeI=1 ``` & whoami```.
  - Highlight ``` & whoami``` and press "Ctrl + U" on keyboard to encode it. Then, Click on "Send".
  - The command turns into: ```productId=1&storeId=1 %26+whoami```.
- Output also is "peter-noZB5X" and "62".

<p align="center">
<br/>
<img src="https://i.imgur.com/wF76Z3x.png" height="90%" width="90%" alt=""/>
<br />

- On the top of the page on the browser will say: "Congratulations, you solved the lab!"

<p align="center">
<br/>
<img src="https://i.imgur.com/6VjWy3G.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Command Injection with Script</h2>

- Open up Visual Studio Code

- Import the command-injection-lab-01.py into Visual Studio Code.
  - Click on "Terminal". Then, "New Terminal".

<p align="center">
<br/>
<img src="https://i.imgur.com/nOsaolk.png" height="90%" width="90%" alt=""/>
<br />

- Change Directory to the folder that have command-injection-lab-01.py .
  - Type in: ```cd Lab \ 1```

- Run the "Whoami" command on the lab website URL.
  - Type in: ```python3 Command-Injection-Lab1.py "https://0afe00a2031cccb983a360ce00f200a8.web-security-academy.net" whoami ```
  - Result:

<p align="center">
<br/>
<img src="https://i.imgur.com/mBopduE.png" height="90%" width="90%" alt=""/>
<br />
