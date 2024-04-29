# Getting Started with Wireshark: The Ultimate Hands-On Course

## Assignment 2: Lab 2 - Configuring the Wireshark Interface

- Name of the file downloaded from Udemy: udemy-wiresharkintro.pcapng
  - Uploaded both files to GitHub
 
Questions for this assignment

1. Add a coloring rule that will make your tcp FIN packets blue. What filter will you use to do that?

- Filter: tcp.flags.fin==1

<p align="center"> <img src="https://i.imgur.com/O5PTYz4.png" height="90%" width="90%" alt=""/>

2. Select packet number 1. Can you find the TCP segment length? Add this value as a column. Enter "done" in the answer field below when finished.

- Expand Transmission Control Protocol > Right click [TCP Segment Len:0] > Apply as Column

<p align="center"> <img src="https://i.imgur.com/lIpqEsf.png" height="90%" width="90%" alt=""/>


3. It would be nice to have a button that quickly filters for all TCP Errors. See if you can find the TCP Retransmission we were looking at earlier. How can you filter for all TCP errors in the trace file? What is this filter?

- Filter: tcp.analysis.flags

<p align="center"> <img src="https://i.imgur.com/3K62JPL.png" height="90%" width="90%" alt=""/>


4. Add the TCP Errors filter as a button in this profile. Enter "done" below when finished.

<p align="center"> <img src="https://i.imgur.com/cw00IYE.png" height="90%" width="90%" alt=""/>

5. It can be a little overkill to see timestamps all the way to the nanosecond. Using the View | Time Display Format menu option, can you see how to configure Wireshark to only display to the microsecond? Make this change in this profile and type "done" below.

- View > Time Display Format > Microseconds

<p align="center"> <img src="https://i.imgur.com/Loqkv1O.png" height="90%" width="90%" alt=""/>
