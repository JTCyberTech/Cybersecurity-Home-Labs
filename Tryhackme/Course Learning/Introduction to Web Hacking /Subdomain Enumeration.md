# Brief

- Subdomain enumeration aims to identify valid subdomains for a domain.

- The primary goal is to expand the attack surface and discover potential points of vulnerability.

- Three common subdomain enumeration methods include `Brute Force`, `OSINT (Open-Source Intelligence)`, and `Virtual Host`.

<h2></h2>

<h2>Questions</h2>

Question 1: What is a subdomain enumeration method beginning with B?

Answer: `Brute Force`

Question 2: What is a subdomain enumeration method beginning with O?

Answer: `OSINT`

Question 2: What is a subdomain enumeration method beginning with V?

Answer: `Virtual Host`

<h2></h2>

# OSINT - SSL/TLS Certificates

<h3>SSL/TLS Certificates</h3>

- SSL/TLS certificates are created for domains by Certificate Authorities (CAs).
- CAs participate in Certificate Transparency (CT) logs.
- CT logs are publicly accessible records of SSL/TLS certificates for domain names.
- The purpose of CT logs is to prevent the misuse of certificates, both malicious and accidental.
- We can use CT logs to discover subdomains of a domain.
- Services like https://crt.sh and https://ui.ctsearch.entrust.com/ui/ctsearchui provide searchable databases of certificates, showing current and historical data.

<h2></h2>

<h2>Questions</h2>

<h3>Question: What domain was logged on crt.sh at 2020-12-26? [tryhackme.com] </h3>

- Navigate to the website: `crt.sh` and search for `tryhackme.com`. Then scroll down and find the log for 2020-12-26.

<p align="center">
<br/>
<img src="https://i.imgur.com/Z2juwxh.png" height="90%" width="90%" alt=""/>
<br />

Answer: `store.tryhackme.com`

<h2></h2>

# OSINT - Search Engines

<h3>Search Engines</h3>

- Search engines host trillions of links to over a billion websites, making them a valuable source for discovering subdomains.
- Utilize advanced search techniques, like Google's site: filter, to refine your search results.
- To find subdomains for a specific domain, use filters like "-site:www.domain.com site:*.domain.com" to exclude links to www.domain.com and focus on subdomains of domain.com.

<h2></h2>

<h2>Questions</h2>

<h3>Question: What is the TryHackMe subdomain beginning with B discovered using the above Google search? </h3>

- Navigate to Google. Use the search term `site:*.tryhackme.com`

<p align="center">
<br/>
<img src="https://i.imgur.com/ADjAmY8.png" height="90%" width="90%" alt=""/>
<br />

Answer: `blog.tryhackme.com`


<h2></h2>

# OSINT - DNS Bruteforce

- Bruteforce DNS enumeration involves trying many possible subdomains from a predefined list.
- Automation tools like dnsrecon are used to speed up the process.
  - `dnsrecon -t brt -d acmeitsupport.thm`
 
<h2></h2>

<h2>Questions</h2>

<h3>Question: What is the first subdomain found with the dnsrecon tool?</h3>

<p align="center">
<br/>
<img src="https://i.imgur.com/UwR5sbr.png" height="90%" width="90%" alt=""/>
<br />

Answer: `api.acmeitsupport.thm`


<h2></h2>

# OSINT - Sublist3r

<h3>Automation Using Sublist3r</h3>

To speed up the process of OSINT subdomain discovery, we can automate the above methods with the help of tools like `Sublist3r`.

<h2></h2>

<h2>Questions</h2>

<h3>Question: What is the first subdomain discovered by sublist3r?</h3>

<p align="center">
<br/>
<img src="https://i.imgur.com/FNlj8BM.png" height="90%" width="90%" alt=""/>
<br />

Answer: `web55.acmeitsupport.thm`


<h2></h2>

# Virtual Hosts

- Subdomains may not always be publicly accessible in DNS results.
- Some subdomains may be hosted on private DNS servers or developer machines.
- They can be recorded in the /etc/hosts file (Linux) or c:\windows\system32\drivers\etc\hosts file (Windows) to map domain names to IP addresses.

<h2></h2>

- Web servers can host multiple websites on a single server and determine the client's requested website through the Host header.
- The Host header can be manipulated and monitored to identify new websites on the server.
- Automated discovery of subdomains can be achieved using wordlists, similar to DNS brute-force attacks.
- Consider using an AttackBox and executing specific commands against the Acme IT Support machine to find new subdomains.
  - `ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.54.109`
    - Use the '-w' switch to specify the wordlist.
    - Utilize the '-H' switch to add/edit a header, such as the Host header.
    - Replace a subdomain with the 'FUZZ' keyword to test all wordlist options in that space.
  - `ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.54.109 -fs {size}`
    - This command has a similar syntax to the first apart from the -fs switch, which tells ffuf to ignore any results that are of the specified size.
    - To filter the output, use the page size result with the "-fs" switch.




<h2></h2>

<h2>Questions</h2>

<h3>Question 1: What is the first subdomain discovered?</h3>

- On Terminal ues the ffuf command and Fuzz the Acme website.
  - `ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.54.109`
  - Found out that size: `2395` is the side that occurs the most.

<p align="center">
<br/>
<img src="https://i.imgur.com/4TXRjRY.png" height="90%" width="90%" alt=""/>
<br />

- Replace "{size}" in the command with the most frequently occurring size value from the previous result.
  - `ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.54.109 -fs 2395`
 
<p align="center">
<br/>
<img src="https://i.imgur.com/SZ1u5NJ.png" height="90%" width="90%" alt=""/>
<br />

Answer: `delta`

<h3>Question 2: What is the second subdomain discovered?</h3>

Answer: `yellow`
