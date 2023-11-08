# OhSINT

Room [OhSINT](https://tryhackme.com/room/ohsint) on TryHackMe

<h2></h2>

<h3>Make a Directory with the Room Name in the TryHackMe Folder</h3>

- Change directory to /Desktop/Tryhackme.

`cd Desktop/Tryhackme`

- Change a new directory call "OhSINT".

`mkdir OhSINT`

- Change directory into OhSINT.

`cd OhSINT/`

<p align="center">
<img src="https://i.imgur.com/YfVLqeW.png" height="90%" width="90%" alt=""/>


<h2></h2>

<h3>Download the Task File On TryHackMe</h3>

Click on the Download Task Files. Move the file into our directory using the `mv` command.

On Terminal: `mv ../../../Downloads/WindowsXP.jpg .`

<p align="center">
<br/>
<img src="https://i.imgur.com/6gbzIjP.png" height="90%" width="90%" alt=""/>
<br />

<h2></h2>

<h3>Quetion 1: What is this user's avatar of?</h3>

We will check the metadata of the JPG file by using `exiftool` command.

On terminal: `exiftool WindowsXP.jpg`

<p align="center">
<br/>
<img src="https://i.imgur.com/NDRJf3U.png" height="90%" width="90%" alt=""/>
<br />

We found interesting information with the metadata. Like the copyright to be: `OWoodflint`. We can search it on Google for any information.

<p align="center">
<br/>
<img src="https://imgur.com/JPPQLYb" height="90%" width="90%" alt=""/>
<br />

We can click on the first link of the google search.

<p align="center">
<img src="https://i.imgur.com/o2ENTa2.png" height="90%" width="90%" alt=""/>

We can answer the first question:

Answer: `cat`

<h2></h2>

<h3>Question 2: What city is this person in?</h3>

We can check out other webpage, for example: GitHub one. 

<p align="center">
<img src="https://i.imgur.com/Ka2qzWW.png" height="90%" width="90%" alt=""/>

We can see that the author said he is from "London" on the Github README.md.

<p align="center">
<img src="https://i.imgur.com/36kTv1d.png" height="90%" width="90%" alt=""/>

We can answer the second question:

Answer: `London`

<h2></h2>

<h3>What is the SSID of the WAP he connected to?</h3>

We can go to Wigle.net for the searching for this question. WiGLE is known for its crowd-sourced database of wireless network information and its ability to map the locations of these networks.

<p align="center">
<img src="https://i.imgur.com/jBqFFzs.png" height="90%" width="90%" alt=""/>

We got the BSSID from the twitter page. (Bssid: B4:5D:50:AA:86:41)

<p align="center">
<img src="https://i.imgur.com/KyeVpuw.png" height="90%" width="90%" alt=""/>

Fill into the Wigle.net and click on "Filter".

<p align="center">
<img src="https://i.imgur.com/xfa2ftd.png" height="90%" width="90%" alt=""/>

Then location London and zoom in. We found that the SSID is "UnileverWiFi".

<p align="center">
<img src="https://i.imgur.com/1jfT0pn.png" height="90%" width="90%" alt=""/>

We can answer the third question:

Answer: `UnileverWiFi`

<h2></h2>

<h3>Question 4: What is his personal email address?</h3>

We can go to the Github page and see the email address to be: 

<p align="center">
<img src="https://i.imgur.com/8xooE6u.png" height="90%" width="90%" alt=""/>

Answer: `OWoodflint@gmail.com`

<h3>Question 5: What site did you find his email address on?</h3>

Answer: `Github`

<h2></h2>

<h3>Question 6: Where has he gone on holiday?</h3>

We can check out the second website, the blog.

<p align="center">
<img src="https://i.imgur.com/8ItXO60.png" height="90%" width="90%" alt=""/>

We can see that the author is in "New York" right now.

<p align="center">
<img src="https://i.imgur.com/kzM1H7O.png" height="90%" width="90%" alt=""/>

Answer: `New York`

<h2></h2>

<h3>Question 7: What is the person's password?</h3>

We can highlight the blog webpage and we can see the password to be "pennYDr0pper.!"

<p align="center">
<img src="https://i.imgur.com/ZB5vUew.png" height="90%" width="90%" alt=""/>

Answer: `pennYDr0pper.!`
