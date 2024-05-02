# Where and How to Capture Packets

## Think BEFORE You Capture!

- Who is impacted?:
  - One person or group of people?
  - Located in specific area of encironment?
- Experience this problem all the time?
  - Persistent and ongoing? Come and go?
- What application are impacted?
  - Only email/ customer relationship database or does it effect everything?
- What servers are they interacting with?
- What network path?

#

## How To Capture In a Switched Environment - Local Capture vs SPAN vs TAP


- Local Capture: install wireshark directly in the infected machine and capture data with it.
- SPAN/Mirror: Tell switch to forward packet over to a monitor port.
- Network Tap: Somewhere between client and server, we come in and physically break the connection and put in a box that acts as a hardware tap. The tap has ports on it that we use as analysis ports.

#

## Should We Use a Capture Filter?

- Capture filter is when we collect traffic off the wire, but only traffic that we denote.
  - Can miss any backend conversations that server has with any databases.
- Better to capture everything then filter later using display filters.

#

## How to Capture on Command Line with Dumpcap

- Open Command Prompt > Get to the directory that Wireshark is installed on

<p align="center"> <img src="https://i.imgur.com/MdWUzRN.png" height="90%" width="90%" alt=""/>

- type in "dir" > dumpcap.exe is installed in this directory.

<p align="center"> <img src="https://i.imgur.com/ivjLefr.png" height="90%" width="90%" alt=""/>

- dumpcap -D: show all the interface that dumpcap can capture traffic with.
- dumpcap -i (#): capture the  interface # that you want dumpcap to capture.
- dumpcap -i (#) -w ("filename.pcapng") -b filesize: 500000 -b files: 100:
  - Save in "filename.pcapng" with filesize of 500 MB and ring buffer of 100 files.
  - Ring-buffer = after 100 files, will go back and override the first file with 101,102,103.
 
#

## Quiz

<p align="center"> <img src="https://i.imgur.com/1rlgx6K.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/8uMuSqJ.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/t1IYEye.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/x0o14JF.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/3OY1HSz.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/DnrWQ4k.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/u2kRiOK.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/Oyt9eGg.png" height="90%" width="90%" alt=""/>
