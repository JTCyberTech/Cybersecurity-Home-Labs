# Simple measures to enhance your cybersecurity posture

<h2>Part 1: Creating a Honeypot using StationX Canary Token </h2> 

Description: A honeypot is a purposefully deployed network or system designed to mimic valuable assets and attract cyber attackers. The primary objective of this task is to create a honeypot Microsoft Word and send myself fake emails that contain fake personal information to see if there is any hacker already in our system or email trying to intercept the information. It is best practice to try and sprinkle as much of the honeypot and fake emails to monitor, analyze, and study malicious activities and tactics employed by threat actors.

- Creating a hidden hacker trap with a CanaryToken on [Stationx](https://www.stationx.net/canarytokens/) site.
- Creating a Word Document trap to check if your system is hacked
   
  - Put in your email address that you monitor to have the alert sent to you.
  - Enter a comment that reminds you what type of trap you are setting.
  - Choose DNS/HTTP Then Generate Token
  - Scroll down and click on MS Word and download the unique Word Document.
  - After downloading, open and customize the Word document.
  - Check your email if you are notified by the Word document.
<p align="left">
MS Word Trap  <br/>
<img src="https://i.imgur.com/3UY046S.png" height="30%" width="30%" alt=""/>
<br />
   
<p align="left">
MS Word Trap Notification by email   <br/>
<img src="https://i.imgur.com/5bm7q7g.png" height="30%" width="30%" alt=""/>
<br />

<p align="left">
Detail of the notification from email showing the IP Address of the hacker <br/>
<img src="https://i.imgur.com/Y59b1jh.png" height="30%" width="30%" alt=""/>
<br />

- Creating a fake email of passwords to check if your email is hacked
  - Put in your email address that you monitor to have the alert sent to you.
  - Enter a comment that reminds you what type of trap you are setting
  - Choose Browser Scanner Then Generate Token
  - Scroll down and click on Web bugs
    - If hackers click on that URL link, you will be notified.
   
<p align="left">
Email Trap working   <br/>
<img src="https://i.imgur.com/2HYx5mh.png" height="30%" width="30%" alt=""/>
<br/>

<h2></h2>
   
<h2>Part 2: Disable Windows 10 Tracking </h2>

Description: Disabling tracking can help prevent the sharing of sensitive information with Microsoft and other third parties, reduce the risk of data breaches, and provide users with more control over their digital privacy. Additionally, it can help protect against potential vulnerabilities and exploits associated with data collection mechanisms. We will be using [10se1ucgo/DisableWinTracking](https://github.com/bitlog2/DisableWinTracking) to complete this task.

- Scroll down on the GitHub page and download the EXE file or click [Download EXE File](https://github.com/bitlog2/DisableWinTracking/releases/)
- Best practice to create a backup before navigating the program
- Menu of the Disable Windows 10 Tracking:
   - Use **Privacy** for Mode and user **Disable** for Service Method instead of Delete
      - Check the box: Services lets you disable or delete the diagnostic tracking service and the WHAP push message routing service.
      - Check the box: Clear DiagTrack log, this clears and disables right to the log located in the program data MS Diagnostics ETL logs auto logger.
      - Check the box: Telemetry and Block tracking domain, this adds IP addresses to the host file.
      - Check the box: Block even more tracking domains, this blocks the tracking domains that you absolutely do not want.
      - Check the box: Block tracking IP addresses, this is blocking using the Windows firewall and firewall rules will be created using checking this box.
      - Check the box: Stop Defender/Wifisense Data Collection, this stops Defender is changing the automatic sample submission along with the delivery optimization and Wifi sense a way of sending the WiFi password of the networks that you have access to to the people that you know (potential privacy issue), stopping this will change the credential share and the openness settings.
      - Check the box: Uninstall OneDrive, this option is for personal preference.
   - Click: Go

<p align="left">
Disable Windows 10 Tracking Interface <br/>
<img src="https://i.imgur.com/BuNpYNM.png" height="30%" width="30%" alt=""/>
<br />

<h2></h2>
