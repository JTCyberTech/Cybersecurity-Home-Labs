# Key Takeaways

<h2>Useful Commands for Nmap</h2> 

- ```nmap [Scan Type(s)] [Options] {target specification}```, this is the basic structure of what a scan command looks like.
- ```nmap -h```, this is the help command, it shows different instruction and different options that nmap have for types of scans.
- ```nmap -sS [IP]```, this is a stealth scan command.
- ```nmap -p [IP]```, this is the port ranges, only scan specified ports.
- ```nmap -sU [IP]```, this scan for UDP.
- ```nmap -F [IP]```, this scan for the common ports. (Top 100 ports)

<h3>Top 5 Nmap Commands</h3>

- ```nmap -sn [IP]```, this is ping scan. (Identify all of the IP addresses that are current;y online without sending any packets to the hosts.
- ```nmap --top-ports 20 [IP]```, this scan for the top 20 ports.
- ```nmap -O [IP]```, this scan for the operating system version for the IP Address. (target for TCP stack, different OS have different TCP stack)
- ```nmap -A [IP]```, this is almost like - all, run port scan, OS fingerprint, version, traceroute to the device. (Super noisy)
- ```nmap -p [IP]```, this is the port ranges, only scan specified ports.


<h2></h2>

<h2>How To Do Range Scan</h2>

Target IP: 10.211.55.4
- ```nmap 10.211.55.0/24```, this will scan the whole range of 10.211.55.0 - 10.211.55.65535 for the open ports.
- ```nmap 10.211.55.0/24 192.168.4.0/24```, this will scan the whole range of 10.211.55 and 192.168.4 for the open ports.
- ```nmap 192.168.4.1-10```, this will scan the range of "192.168.4.1" - "192.168.4.10".

<h2></h2>

<h2>Using "nmap -p" </h2>

- ```nmap -p80,443 192.168.4.1```, this only scan for port 80 and 443 on IP "192.168.4.1".
- ```nmap -p1-100 192.168.4.1```, this will scan port 1 to port 100 on IP "192.168.4.1".
- ```nmap -p- 192.168.4.1```, this will scan all the ports on IP "192.168.4.1". (all 1 - 65535)
- ```nmap -p80,443 -sU 192.168.4.1```, this will scan port 80 and 443 on "192.168.4.1" but will scan over UDP.
