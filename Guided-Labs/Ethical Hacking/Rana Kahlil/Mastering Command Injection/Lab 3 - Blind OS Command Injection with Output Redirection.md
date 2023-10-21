# Lab 3 - Blind OS Command Injection with Output Redirection

<h2>Lab 3: Setup</h2>

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

- Scroll down and click on the lab "Blind OS command injection with output redirection".

<p align="center">
<br/>
<img src="https://i.imgur.com/jfTj40b.png" height="90%" width="90%" alt=""/>
<br />

- Click on "ACCESS THE LAB".

<p align="center">
<br/>
<img src="https://i.imgur.com/4QxKsVD.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Visual Studio Code Downloads</h3>

- Open up Visual Studio Code. Import the file below to Visual Studio Code.
  - Click on "Download raw file".
      - [command-injection-lab-03.py](https://github.com/rkhal101/Web-Security-Academy-Series/blob/main/command-injection/lab-03/command-injection-lab-03.py)
   
<p align="center">
<br/>
<img src="https://i.imgur.com/ulfaHrl.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h2>Lab Solution</h2>

The target goal: Exploit the blind command injection and redirect the output from the "whoami" command to the "/var/www/images" folder.

Steps:

1. Confirm blind command injection

2. Check where images are store

3. Redirect output to file

4. Check if file was created

<h2></h2>

<h2>Confirm Blind Command Injection:</h2>

- Navigate to Burp Suite turn Intercept On by clicking on "Intercept is off".

<p align="center">
<br/>
<img src="https://i.imgur.com/YzGDBNL.png" height="90%" width="90%" alt=""/>
<br />


- Navigate to the Intercept Browser, click on "Submit feedback".

<p align="center">
<br/>
<img src="https://i.imgur.com/UtNu6mG.png" height="90%" width="90%" alt=""/>
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
<img src="https://i.imgur.com/t23Mf8B.png" height="90%" width="90%" alt=""/>
<br />

- The response from the form is just "Thank you for submitting feedback!
  - Doesn't give you the response of the request that you performed.
  - If any of the field is vulnerable to command injection, it could be "Blind command injection" instead of "In-band command injection".

<p align="center">
<br/>
<img src="https://i.imgur.com/7kBxYN4.png" height="90%" width="90%" alt=""/>
<br />
 
- Notice a "post request" for "feedback/submit" have generated on Burp Suite on the HTTP history tab.

<p align="center">
<br/>
<img src="https://i.imgur.com/W3fzeUh.png" height="90%" width="90%" alt=""/>
<br />
 
- Click on the post request. Right-click on the request on the bottom and select "Send to Repeater". 

<p align="center">
<br/>
<img src="https://i.imgur.com/yI22mva.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Repeater".
  - From the repeater, we can see it takes parameters in csrf, name, email, subject, and email.

<p align="center">
<br/>
<img src="https://i.imgur.com/65WBtRs.png" height="90%" width="90%" alt=""/>
<br />
 
<h2></h2>

<h3>Testing for Potential Injection Vulnerabilities</h3>

We are going to test each parameter that is visable on the website for potential injection vulnerabilities with the "sleep" command. (Excluding csrf)

<h3>Name Field:</h3> 

- Adding "&" for chainning command. Then "sleep 10" to run "sleep" command. Then add "#" for making the rest of the command a comment.
  - Add in: "csrf=W7KsRxyQSmSzYXrHORkztKR6e68lW2YB&name=test``` & sleep 10 #```&email=test%40test.ca&subject=test&message=test".
  - Highlight ``` & sleep 10 #```. Then, press "Ctrl + U" to encode it.
  - The command turns into: "```csrf=W7KsRxyQSmSzYXrHORkztKR6e68lW2YB&name=test+%26+sleep+10+%23&email=test%40test.ca&subject=test&message=test```".
- Click on "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/WaQ0UFo.png" height="90%" width="90%" alt=""/>
<br />

We got the result back right away, so the name field not vulnerable to the "sleep" command.

<p align="center">
<br/>
<img src="https://i.imgur.com/IoPXg7Q.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Email Field:</h3>

- Delete: ```+%26+sleep+10+%23```. Then Repeat the same thing for email field on the command.
  - The command turns into: "```csrf=Ay1VbxDEsOHvNQi1pi9fLLFpmFdwJGmd&name=test&email=test%40test.ca+%26+sleep+10+%23&subject=test&message=test```".
- Click on "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/3BZBAfY.png" height="90%" width="90%" alt=""/>
<br />

We got the result back in 10 seconds, so the email field is vulnerable to the "sleep" command.

<h2></h2>

<h2>Check Where Images Are Store</h2>

- Click on "Proxy" tab on Burp Suite. Then click on "HTTP history".

<p align="center">
<br/>
<img src="https://i.imgur.com/G8poyCf.png" height="90%" width="90%" alt=""/>
<br />

- Click on the "Filter Bar".

<p align="center">
<br/>
<img src="https://i.imgur.com/404nNak.png" height="90%" width="90%" alt=""/>
<br />

- Check the box for "Images". Then, click on "Apply".

<p align="center">
<br/>
<img src="https://i.imgur.com/alAxhmj.png" height="90%" width="90%" alt=""/>
<br />

- Navigate back to the Intercept Browser", click on "Home".

<p align="center">
<br/>
<img src="https://i.imgur.com/hTulYG0.png" height="90%" width="90%" alt=""/>
<br />

- Go back to Burp Suite, we can see there is a lot of images generated on the "HTTP history".

<p align="center">
<br/>
<img src="https://i.imgur.com/RF2lglS.png" height="90%" width="90%" alt=""/>
<br />

- Click on a random GET request with URL that has "/image?filename".

<p align="center">
<br/>
<img src="https://i.imgur.com/HNlH6km.png" height="90%" width="90%" alt=""/>
<br />

- Right-click on the request on the bottom and select "Send to Repeater".

<p align="center">
<br/>
<img src="https://i.imgur.com/fIxEN6J.png" height="90%" width="90%" alt=""/>
<br />

- Click on "Send" will give you the content of the image.

<p align="center">
<br/>
<img src="https://i.imgur.com/8CXKLQA.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Redirect Output to File</h2>

- Go back to the Repeater with the ```csrf=``` command.
  - Instead of asking to sleep, run "whoami" command but redirect the output of the "whoami" command into a file in "/var/www/images/output.txt".
  - Add in: "csrf=MQ7FaDJ140t92gTvPUwztnBH5F6pL1AE&name=test&email=test%40test.ca``` & whoami > /var/www/images/output.txt #```&subject=test&message=test".
  - Highlight ``` & whoami > /var/www/images/output.txt #```. Then, press "Ctrl + U" to encode it.
  - The command turns into: "```csrf=MQ7FaDJ140t92gTvPUwztnBH5F6pL1AE&name=test&email=test%40test.ca+%26+whoami+>+/var/www/images/output.txt+%23&subject=test&message=test```".
- Click on "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/ufbGAyj.png" height="90%" width="90%" alt=""/>
<br />

- The response doesn't tell us if it works.

<p align="center">
<br/>
<img src="https://i.imgur.com/Vj0zsVL.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Check If File was Created</h2>

- Navigate back to the image repeater.
  - change: "Get /image?filename=```36.jpg```" into "Get /image?filename=```output.txt```".
- Click on "Send".

<p align="center">
<br/>
<img src="https://i.imgur.com/rXAkqyh.png" height="90%" width="90%" alt=""/>
<br />

- The response worked, the output shows the "whoami" command and it displays the user of the system: "peter-rmFf07".

<p align="center">
<br/>
<img src="https://i.imgur.com/q4PwJUX.png" height="90%" width="90%" alt=""/>
<br />

<h2>Congratulations: Lab Solved<</h2>

On the top of the page on the intercept browser will say: "Congratulations, you solved the lab!"

<p align="center">
<br/>
<img src="https://i.imgur.com/JREJHpz.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h2>Command Injection with Script</h2>

- Open up Visual Studio Code

- Import the command-injection-lab-03.py into Visual Studio Code.
  - Click on "Terminal". Then, "New Terminal".

<p align="center">
<br/>
<img src="https://i.imgur.com/ohuFT4b.png" height="90%" width="90%" alt=""/>
<br />

- Change Directory to the folder that have command-injection-lab-02.py .
  - Type in: ```cd Lab\ 3```

- Run command on the lab website URL.
  - Type in: ```command-injection-lab-03.py "https://0a75006003508c5782895b1800c600c7.web-security-academy.net/" ```
  - Result:

<p align="center">
<br/>
<img src="https://i.imgur.com/4OitwAF.png" height="90%" width="90%" alt=""/>
<br />
