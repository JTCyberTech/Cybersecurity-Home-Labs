# Introduction

In this session, we'll go over the basics of analyzing data packets using Wireshark and delve into a specific event by looking at individual packets. Keep in mind, this is the second part of a series of three rooms about Wireshark. We learned the basics of Wireshark, understanding how it works, and using it to examine captured traffic. Now, in this session, we'll explore more advanced features, zooming in on specific packet details with Wireshark statistics, filters, operators, and functions.

#

# Statistics | Summary

<h3>Statistics</h3>

This menu offers various statistical options that users can explore to understand the overall traffic scope, available protocols, endpoints, and conversations. It also includes specific details about protocols like DHCP, DNS, and HTTP/2. For security analysts, it's important to know how to use this statistical information effectively.

In simpler terms, this section gives a quick summary of the processed pcap (packet capture) file, helping analysts form hypotheses for their investigations. To access these statistics, you can use the "Statistics" menu, where all available options are listed. To begin, start the provided virtual machine (VM), open Wireshark, load the "Exercise.pcapng" file, and follow the provided walkthrough.

<h3>Resolved Addresses</h3>

This tool assists analysts in finding IP addresses and DNS names present in the capture file. It gives a list of the confirmed addresses and their corresponding hostnames, extracted from DNS responses in the capture file. By using this menu, analysts can easily pinpoint the resources that were accessed, allowing them to evaluate them in relation to the specific event of interest. To view all the resolved addresses in Wireshark, you can navigate to "Statistics" and then select "Resolved Addresses."

<p align="center"> <img src="https://i.imgur.com/KDHJ6aC.png" height="90%" width="90%" alt=""/>

<h3>Protocol Hierarchy</h3>

This feature breaks down the protocols found in the captured file, allowing analysts to see them in a tree view with packet counters and percentages. This helps analysts get an overall picture of how ports and services are being used, making it easier to focus on specific events. Remember the golden rule from before: you can right-click to filter events you're interested in. To access this information, go to "Statistics" and choose "Protocol Hierarchy" from the menu.

<p align="center"> <img src="https://i.imgur.com/4syBR5F.png" height="90%" width="90%" alt=""/>

<h3>Converstaions</h3>

A conversation is like a chat between two points. In simple terms, you can see a list of these chats in five main formats: ethernet, IPv4, IPv6, TCP, and UDP. This helps analysts figure out all the chats and who's talking in the situation they're looking into. Just go to the "Statistic --> Conversations" menu to check out this information.

<p align="center"> <img src="https://i.imgur.com/vGfO7fk.png" height="90%" width="90%" alt=""/>

<h3>Endpoints</h3>

The endpoints option is like the conversations option, but it gives specific details for individual information fields (Ethernet, IPv4, IPv6, TCP, and UDP). This helps analysts find unique endpoints in the capture file for a particular event. To see this information, go to "Statistics --> Endpoints."

Wireshark can also turn MAC addresses into a human-readable format by using the manufacturer name assigned by IEEE. Keep in mind that this conversion applies only to the first three bytes of the MAC address and works only for recognized manufacturers. When checking Ethernet endpoints, you can enable this option using the "Name resolution" button at the bottom left of the endpoints window.

<p align="center"> <img src="https://i.imgur.com/cpDvcou.png" height="90%" width="90%" alt=""/>

Name resolution is not limited only to MAC addresses. You can also find names for IP addresses and ports, but these features are turned off when you first use the program. To make them work, go to "Edit," then "Preferences," and choose "Name Resolution." Once you activate IP and port name resolution, you'll see the names of IP addresses and ports in the packet list. You can also check out resolved names in the "Conversations" and "Endpoints" menus.

<p align="center"> <img src="https://i.imgur.com/FsTgqmL.png" height="90%" width="90%" alt=""/>

Endpoint menu view with name resolution:

<p align="center"> <img src="https://i.imgur.com/mLpnKVh.png" height="90%" width="90%" alt=""/>

Besides name resolution, Wireshark also provides an IP geolocation mapping that helps analysts identify the map's source and destination addresses. But this feature is not activated by default and needs supplementary data like the GeoIP database. Currently, Wireshark supports MaxMind databases, and the latest versions of the Wireshark come configured MaxMind DB resolver. However, you still need MaxMind DB files and provide the database path to Wireshark by using the "Edit --> Preferences --> Name Resolution --> MaxMind database directories" menu. Once you download and indicate the path, Wireshark will automatically provide GeoIP information under the IP protocol details for the matched IP addresses.

<p align="center"> <img src="https://i.imgur.com/N3hbVTr.png" height="90%" width="90%" alt=""/>

Endpoints and GeoIP view.

<p align="center"> <img src="https://i.imgur.com/IR2kgKU.png" height="90%" width="90%" alt=""/>

#

<h3>Questions:</h3>

Question 1: Investigate the resolved addresses. What is the IP address of the hostname starts with "bbc"?

On Wireshark, click on "Statistics" > "Resolved Addresses". Then search `bbc`.

`199.232.24.81`

<p align="center"> <img src="https://i.imgur.com/ypo26aI.png" height="90%" width="90%" alt=""/>

# 

Question 2: What is the number of IPv4 conversations?

On Wireshark, click on "Statistics" > "Conversations". Then we can see the number of each conversation on different ports.

`435`

<p align="center"> <img src="https://i.imgur.com/3JMZCLs.png" height="90%" width="90%" alt=""/>

#

Question 3: How many bytes (k) were transferred from the "Micro-St" MAC address?

On Wireshark, click on "Statistics" > "Endpoints". Then we can see the Bytes of "Micro-St".

`7474`

<p align="center"> <img src="https://i.imgur.com/0pnxm2U.png" height="90%" width="90%" alt=""/>

#

Question 4: What is the number of IP addresses linked with "Kansas City"?

Inside "Endpoints" we can see only 4 connection linked with Kansas City.

`4`

<p align="center"> <img src="https://i.imgur.com/fHBon4I.png" height="90%" width="90%" alt=""/>

#

Question 5: Which IP address is linked with "Blicnet" AS Organisation?

Inside "Endpoints" we found there is an Address linked to "Blicnet" AS Organiation.

<p align="center"> <img src="https://i.imgur.com/YRHQGRW.png" height="90%" width="90%" alt=""/>

We will Right-click on it > "Apply as Filter" > "Selected".

Navigate back to Wireshark. Found the IP Address. 

`188.246.82.7`

<p align="center"> <img src="https://i.imgur.com/camFIit.png" height="90%" width="90%" alt=""/>

#

# Statistics | Protocol Details

<h3>IPv4 and IPv6</h3>

Up to here, almost all options provided information that contained both versions of the IP addresses. The statistics menu has two options for narrowing the statistics on packets containing a specific IP version. Thus, analysts can identify and list all events linked to specific IP versions in a single window and use it for the event of interest. You can use the "Statistics --> IPvX Statistics" menu to view this info.

<p align="center"> <img src="https://i.imgur.com/3y2sNKZ.png" height="90%" width="90%" alt=""/>

<h3>DNS</h3>

This option breaks down all DNS packets from the capture file and helps analysts view the findings in a tree view based on packet counters and percentages of the DNS protocol. Thus analysts can view the DNS service's overall usage, including rcode, opcode, class, query type, service and query stats and use it for the event of interest. You can use the "Statistics --> DNS" menu to view this info.

<p align="center"> <img src="https://i.imgur.com/JudYqHd.png" height="90%" width="90%" alt=""/>

<h3>HTTP</h3>

This option breaks down all HTTP packets from the capture file and helps analysts view the findings in a tree view based on packet counters and percentages of the HTTP protocol. Thus analysts can view the HTTP service's overall usage, including request and response codes and the original requests. You can use the "Statistics --> HTTP" menu to view this info.

<p align="center"> <img src="https://i.imgur.com/tI4K3p8.png" height="90%" width="90%" alt=""/>

#

<h3>Questions:</h3>

Question 1: What is the most used IPv4 destination address?

On wireshark, click on "Statistics" > "IPv4 Statistics" > "Destinations and Ports". Then order it by Count.

`10.100.1.33`

<p align="center"> <img src="https://i.imgur.com/92Uc8ss.png" height="90%" width="90%" alt=""/>

Question 2: What is the max service request-response time of the DNS packets?

On wireshark, click on "Statistics" > "DNS". Then scroll to find "Service Stats: Request-response time(secs)".

`0.467897`

<p align="center"> <img src="https://i.imgur.com/ftKwFB2.png" height="90%" width="90%" alt=""/>

Question 3: What is the number of HTTP Requests accomplished by "rad[.]msn[.]com?

On wireshark, click on "Statistics" > "HTTP" > "Requests". Then scroll to find "rad.msn.com".

`39`

<p align="center"> <img src="https://i.imgur.com/I1sNXOE.png" height="90%" width="90%" alt=""/>


