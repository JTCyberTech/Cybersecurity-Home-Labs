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

#

Question 2: What is the max service request-response time of the DNS packets?

On wireshark, click on "Statistics" > "DNS". Then scroll to find "Service Stats: Request-response time(secs)".

`0.467897`

<p align="center"> <img src="https://i.imgur.com/ftKwFB2.png" height="90%" width="90%" alt=""/>

#

Question 3: What is the number of HTTP Requests accomplished by "rad[.]msn[.]com?

On wireshark, click on "Statistics" > "HTTP" > "Requests". Then scroll to find "rad.msn.com".

`39`

<p align="center"> <img src="https://i.imgur.com/I1sNXOE.png" height="90%" width="90%" alt=""/>

#

# Packet Filtering | Principles

<h3>Packet Filtering</h3>

In the previous room (Wireshark | The Basics), we covered packet filtering and how to filter packets without using queries. In this room, we will use queries to filter packets. As mentioned earlier, there are two types of filters in Wireshark. While both use similar syntax, they are used for different purposes. Let's remember the difference between these two categories.

<p align="center"> <img src="https://i.imgur.com/V3jNGF9.png" height="90%" width="90%" alt=""/>

<h3>Capture Filter Syntax</h3>

These filters use byte offsets hex values and masks with boolean operators, and it is not easy to understand/predict the filter's purpose at first glance. The base syntax is explained below:

- Scope: host, net, port and portrange.
- Direction: src, dst, src or dst, src and dst,
- Protocol: ether, wlan, ip, ip6, arp, rarp, tcp and udp.
- Sample filter to capture port 80 traffic: tcp port 80

You can read more on capture filter syntax from here and here. A quick reference is available under the "Capture --> Capture Filters" menu.

<p align="center"> <img src="https://i.imgur.com/RIJyw3T.png" height="90%" width="90%" alt=""/>

<h3>Display Filter Syntax</h3>

This is Wireshark's most powerful feature. It supports 3000 protocols and allows conducting packet-level searches under the protocol breakdown. The official "Display Filter Reference" provides all supported protocols breakdown for filtering.

- Sample filter to capture port 80 traffic: `tcp.port == 80`

Wireshark has a built-in option (Display Filter Expression) that stores all supported protocol structures to help analysts create display filters. We will cover the "Display Filter Expression" menu later. Now let's understand the fundamentals of the display filter operations. A quick reference is available under the "Analyse --> Display Filters" menu.

<p align="center"> <img src="https://i.imgur.com/VGkLWpz.png" height="90%" width="90%" alt=""/>

<h3>Comparison Operators</h3>

<p align="center"> <img src="https://i.imgur.com/tmQGOOn.png" height="90%" width="90%" alt=""/>

<h3>Logical Expressions</h3>

<p align="center"> <img src="https://i.imgur.com/UAGpkCh.png" height="90%" width="90%" alt=""/>

<h3>Packet Filter Toolbar</h3>

The filter toolbar is where you create and apply your display filters. It is a smart toolbar that helps you create valid display filters with ease. Before starting to filter packets, here are a few tips:

- Packet filters are defined in lowercase.
- Packet filters have an autocomplete feature to break down protocol details, and each detail is represented by a "dot".
- Packet filters have a three-colour representation explained below.

<p align="center"> <img src="https://i.imgur.com/swE9aIG.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/swE9aIG.png" height="90%" width="90%" alt=""/>

#

# Packet Filtering | Protocol Filters

<h3>Protocol Filters</h3>

As mentioned in the previous task, Wireshark supports 3000 protocols and allows packet-level investigation by filtering the protocol fields. This task shows the creation and usage of filters against different protocol fields. 

<h3>IP Filters</h3>

IP filters help analysts filter the traffic according to the IP level information from the packets (Network layer of the OSI model). This is one of the most commonly used filters in Wireshark. These filters filter network-level information like IP addresses, version, time to live, type of service, flags, and checksum values.

<p align="center"> <img src="https://i.imgur.com/MckIlxy.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/Ft3RV1Q.png" height="90%" width="90%" alt=""/>

<h3>TCP and UDP Filters</h3>

TCP filters help analysts filter the traffic according to protocol-level information from the packets (Transport layer of the OSI model). These filters filter transport protocol level information like source and destination ports, sequence number, acknowledgement number, windows size, timestamps, flags, length and protocol errors.

<p align="center"> <img src="https://i.imgur.com/4U64kw6.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/BsIypP0.png" height="90%" width="90%" alt=""/>

<h3>Application Level Protocol Filters | HTTP and DNS</h3>

Application-level protocol filters help analysts filter the traffic according to application protocol level information from the packets (Application layer of the OSI model ). These filters filter application-specific information, like payload and linked data, depending on the protocol type.

<p align="center"> <img src="https://i.imgur.com/BsIypP0.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/DQ834kK.png" height="90%" width="90%" alt=""/>

<h3>Display Filter Expressions</h3>

As mentioned earlier, Wireshark has a built-in option (Display Filter Expression) that stores all supported protocol structures to help analysts create display filters. When an analyst can't recall the required filter for a specific protocol or is unsure about the assignable values for a filter, the Display Filter Expressions menu provides an easy-to-use display filter builder guide. It is available under the "Analyse --> Display Filter Expression" menu.

It is impossible to memorise all details of the display filters for each protocol. Each protocol can have different fields and can accept various types of values. The Display Filter Expressions menu shows all protocol fields, accepted value types (integer or string) and predefined values (if any). Note that it will take time and require practice to master creating filters and learning the protocol filter fields.

<p align="center"> <img src="https://i.imgur.com/8UOrBpI.png" height="90%" width="90%" alt=""/>

#

<h3>Questions</h3>

Question 1: What is the number of IP packets?

`81420`

<p align="center"> <img src="https://i.imgur.com/W2aEpLt.png" height="90%" width="90%" alt=""/>

#

Question 2: What is the number of packets with a "TTL value less than 10"?

`66`

<p align="center"> <img src="https://i.imgur.com/PD2zBGE.png" height="90%" width="90%" alt=""/>

#

Question 3: What is the number of packets which uses "TCP port 4444"?

`632`

<p align="center"> <img src="https://i.imgur.com/RERTxi1.png" height="90%" width="90%" alt=""/>

#

Question 4: What is the number of "HTTP GET" requests sent to port "80"?

`527`

<p align="center"> <img src="https://i.imgur.com/T0UMvOP.png" height="90%" width="90%" alt=""/>

#

Question 5: What is the number of "type A DNS Queries"?

`51`

<p align="center"> <img src="https://i.imgur.com/UVMr3LY.png" height="90%" width="90%" alt=""/>

#

# Advanced Filtering

<h3>Advanced Filtering</h3>

So far, you have learned the basics of packet filtering operations. Now it is time to focus on specific packet details for the event of interest. Besides the operators and expressions covered in the previous room, Wireshark has advanced operators and functions. These advanced filtering options help the analyst conduct an in-depth analysis of an event of interest.

<p align="center"> <img src="https://i.imgur.com/bhGttcw.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/xNWqYzT.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/Xq6o22Z.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/lPba4BI.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/2xyWROi.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/e6NHZSJ.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/4gvsymQ.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/hJs1N5Z.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/hJs1N5Z.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/zIsgQvu.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/cehKZKm.png" height="90%" width="90%" alt=""/>

<p align="center"> <img src="https://i.imgur.com/OUzJJzN.png" height="90%" width="90%" alt=""/>

<h3>Bookmarks and Filtering Buttons</h3>

We've covered different types of filtering options, operators and functions. It is time to create filters and save them as bookmarks and buttons for later usage. As mentioned in the previous task, the filter toolbar has a filter bookmark section to save user-created filters, which helps analysts re-use favourite/complex filters with a couple of clicks. Similar to bookmarks, you can create filter buttons ready to apply with a single click. 

Creating and using bookmarks.

<p align="center"> <img src="https://i.imgur.com/IgtJQW5.png" height="90%" width="90%" alt=""/>

Creating and using display filter buttons.

<p align="center"> <img src="https://i.imgur.com/nzHuPBg.png" height="90%" width="90%" alt=""/>

<h3>Profiles</h3>

Wireshark is a multifunctional tool that helps analysts to accomplish in-depth packet analysis. As we covered during the room, multiple preferences need to be configured to analyse a specific event of interest. It is cumbersome to re-change the configuration for each investigation case, which requires a different set of colouring rules and filtering buttons. This is where Wireshark profiles come into play. You can create multiple profiles for different investigation cases and use them accordingly. You can use the "Edit --> Configuration Profiles" menu or the "lower right bottom of the status bar --> Profile" section to create, modify and change the profile configuration.

<p align="center"> <img src="https://i.imgur.com/y00BA1R.png" height="90%" width="90%" alt=""/>

#

<h3>Questions</h3>

Question 1: Find all Microsoft IIS servers. What is the number of packets that did not originate from "port 80"?

`21`

<p align="center"> <img src="https://i.imgur.com/Z4RuMIP.png" height="90%" width="90%" alt=""/>

#

Question 2: Find all Microsoft IIS servers. What is the number of packets that have "version 7.5"?

`71`

<p align="center"> <img src="https://i.imgur.com/5v24T8V.png" height="90%" width="90%" alt=""/>

#

Question 3: What is the total number of packets that use ports 3333, 4444 or 9999?

`2235`

<p align="center"> <img src="https://i.imgur.com/zuYLiEz.png" height="90%" width="90%" alt=""/>

#

Question 4: What is the number of packets with "even TTL numbers"?

`77289`

<p align="center"> <img src="https://i.imgur.com/IpCh7oc.png" height="90%" width="90%" alt=""/>

#

Question 5: Change the profile to "Checksum Control". What is the number of "Bad TCP Checksum" packets?

Click bottom right corner > Change to "Checksum Control. Then Click on the red circle bottom left corner.

<p align="center"> <img src="https://i.imgur.com/Mib8dPn.png" height="90%" width="90%" alt=""/>

`34185`

<p align="center"> <img src="https://i.imgur.com/5wiP3FR.png" height="90%" width="90%" alt=""/>

#

Question 6: Use the existing filtering button to filter the traffic. What is the number of displayed packets?

`261`

<p align="center"> <img src="https://i.imgur.com/CTlGavP.png" height="90%" width="90%" alt=""/>
