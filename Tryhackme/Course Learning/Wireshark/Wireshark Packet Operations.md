# Introduction

In this session, we'll go over the basics of analyzing data packets using Wireshark and delve into a specific event by looking at individual packets. Keep in mind, this is the second part of a series of three rooms about Wireshark. We learned the basics of Wireshark, understanding how it works, and using it to examine captured traffic. Now, in this session, we'll explore more advanced features, zooming in on specific packet details with Wireshark statistics, filters, operators, and functions.

#

# Statistics | Summary

<h3>Statistics</h3>

This menu offers various statistical options that users can explore to understand the overall traffic scope, available protocols, endpoints, and conversations. It also includes specific details about protocols like DHCP, DNS, and HTTP/2. For security analysts, it's important to know how to use this statistical information effectively.

In simpler terms, this section gives a quick summary of the processed pcap (packet capture) file, helping analysts form hypotheses for their investigations. To access these statistics, you can use the "Statistics" menu, where all available options are listed. To begin, start the provided virtual machine (VM), open Wireshark, load the "Exercise.pcapng" file, and follow the provided walkthrough.

<h3>Resolved Addresses</h3>

This tool assists analysts in finding IP addresses and DNS names present in the capture file. It gives a list of the confirmed addresses and their corresponding hostnames, extracted from DNS responses in the capture file. By using this menu, analysts can easily pinpoint the resources that were accessed, allowing them to evaluate them in relation to the specific event of interest. To view all the resolved addresses in Wireshark, you can navigate to "Statistics" and then select "Resolved Addresses."

<p align="center"> <img src="https://i.imgur.com/ILt4Ag8.png" height="90%" width="90%" alt=""/>
