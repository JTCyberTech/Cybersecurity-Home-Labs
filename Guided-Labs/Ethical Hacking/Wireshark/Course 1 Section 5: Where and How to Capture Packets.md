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





- 
