# What is DNS?

- DNS stands for Domain Name System.

- DNS simplifies internet communication by replacing complex IP addresses with human-readable domain names.

- IP addresses are like unique addresses for computers on the internet (e.g., 104.26.10.229).

- DNS allows you to use easy-to-remember domain names (e.g., tryhackme.com) instead of IP addresses.

- DNS serves as an address book for the internet, translating domain names into IP addresses.

<h2></h2>

<h2>Questions</h2>

1: What does DNS stand for?

`Domain Name System`


<h2></h2>

# Domain Hierarchy

<h3>Top Level Domain (TLD)</h3>

- The TLD is the rightmost part of a domain name (e.g., `.com` in tryhackme.com).

- There are two types of TLDs:
  - gTLD (Generic Top Level)
  - ccTLD (Country Code Top Level Domain)
 
- gTLDs indicated the purpose of a domain, like .com for commercial, .org for organizations, .edu for education, and .gov for government.

- ccTLDs were used for geographical purposes, such as .ca for Canada and .co.uk for the United Kingdom.

- New gTLDs have been introduced, including .online, .club, .website, .biz, and more, creating a wide variety of options.

<h2></h2>

<h3>Second-Level Domain</h3>

- The second-level domain is the part to the left of the TLD (e.g., `tryhackme` in tryhackme.com).

- It is limited to `63 characters` and can only use lowercase letters, numbers, and hyphens (-).

- It cannot start or end with hyphens or have consecutive hyphens in its name.

<h2></h2>

<h3>Subdomain:</h3>

- A subdomain is a part of the domain name that sits on the left side of the second-level domain and is separated by periods (e.g., `admin` in admin.tryhackme.com).

- Subdomain names follow the same character and hyphen restrictions as second-level domains.

- Multiple subdomains can be used to create longer domain names, but the total length must not exceed `253 characters`. (e.g., jupiter.servers.tryhackme.com)

- There is no limit to the number of subdomains you can create for your domain name.

<h2></h2>

<h2>Questions</h2>

1. What is the maximum length of a subdomain?

`63`

2. Which of the following characters cannot be used in a subdomain ( 3 b _ - )?

`_`

3. What is the maximum length of a domain name?

`253`

4. What type of TLD is .co.uk?

`ccTLD`


<h2></h2>

# Record Types

DNS isn't just for websites, DNS supports various record types for different purposes.

- A Record: resolve to `IPv4 addresses`. (For example 104.26.10.229)

- AAAA Record: resolve to `IPv6 addresses`. (For example 2606:4700:20::681a:be5)

- CNAME Records: point to another domain name, enabling redirection. `Relabeling` (For example, TryHackMe's online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.)

- MX Records: specify `email server` addresses and their priority for a domain.(For example, an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com.)

- TXT Records: `store free text data` and can be used for email server authorization and domain ownership verification.


<h2></h2>

<h2>Questions</h2>

1. What type of record would be used to advise where to send email?

`MX`

2. What type of record handles IPv6 addresses?

`AAAA`

<h2></h2>

# Making A Request

What happens when you make a DNS Request:

Step 1:

- Domain name requests start with a local cache check on your computer.
- If the domain isn't found in the local cache, a request is sent to the Recursive DNS Server.

Step 2:

- `Recursive DNS Servers` are typically provided by ISPs or can be chosen independently.
- They maintain a local cache of recently requested domain names.
- If a requested domain is in the local cache, the response is delivered immediately.
- For less common or uncached domains, the server starts a journey to find the correct answer.
- The journey begins with root DNS servers on the internet.

Step 3:

- `Root servers` are essential for the functioning of the internet's DNS system.
- They redirect DNS requests to the appropriate Top Level Domain (TLD) server based on the requested domain.
- For example, if you request www.tryhackme.com, the root server identifies the .com TLD and directs you to the relevant .com TLD server.

Step 4:

- `TLD server` stores records for locating authoritative DNS servers.
- Authoritative server is also called the nameserver for a domain.
- Example: tryhackme.com's nameservers are kip.ns.cloudflare.com and uma.ns.cloudflare.com.
- Multiple nameservers provide redundancy in case of server failure.

Step 5:

- `Authoritative DNS server` stores DNS records for a domain.
- Updates to DNS records for a domain are made on the authoritative server.
- DNS records are sent to Recursive DNS Server, which caches them.
- `TTL (Time To Live)` value determines how long DNS records are cached.
- Caching reduces the need for frequent DNS requests when communicating with a server.

<p align="center">
<br/>
<img src="https://i.imgur.com/dj59szQ.png" height="90%" width="90%" alt=""/>
<br />


<h2></h2>

<h2>Questions</h2>

1. What field specifies how long a DNS record should be cached for?

`TTL`

2. What type of DNS Server is usually provided by your ISP?

`Recursive`

3. What type of server holds all the records for a domain?

`Authoritative`
